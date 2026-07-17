---
name: Verify an Indian identity (Aadhaar / PAN)
description: Run consent-based Aadhaar and PAN verification against Signzy.
api: openapi/signzy-openapi.yml
operations: [login, verifyAadhaar, verifyPan]
---

# Verify an Indian identity (Aadhaar / PAN)

## Steps

1. **Authenticate** — get an access token via `login` and set it as the raw
   `Authorization` header (see the Authenticate skill).
2. **Capture consent** — Aadhaar and PAN checks require explicit end-user
   consent. Collect it and pass `consent: "Y"` in the request body. Do not
   proceed without recorded consent — this is regulated PII.
3. **Verify Aadhaar** — call `verifyAadhaar` (`POST /api/v3/aadhaar/verify`)
   with `{ "aadhaarNumber": "<12 digits>", "consent": "Y" }`. The response
   returns the masked demographic details on record.
4. **Verify PAN** — call `verifyPan` (`POST /api/v3/pan/simple`) with
   `{ "panNumber": "<10 chars>", "consent": "Y" }`. The response returns the
   name and status from the income-tax database.

## Rules

- `422` = a required field is missing/malformed (bad Aadhaar/PAN format or
  missing consent). `401` = re-authenticate. See `errors/signzy-problem-types.yml`.
- Aadhaar/PAN numbers and returned demographics are sensitive PII — log and
  store per data-localization requirements (`conventions/signzy-conventions.yml`).
- India-region product; use test inputs from `sandbox/signzy-sandbox.yml` in
  preproduction (`https://api-preproduction.signzy.app`).
