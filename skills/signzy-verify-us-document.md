---
name: Verify a US identity document
description: OCR and authenticate a US ID document image with Signzy.
api: openapi/signzy-openapi.yml
operations: [login, usDocumentIntelligenceAdvance]
---

# Verify a US identity document

## Steps

1. **Authenticate** — get an access token via `login`; set it as the raw
   `Authorization` header.
2. **Host the images** — Signzy reads the document from image URLs. Provide a
   `frontUrl` (and `backUrl` where applicable) pointing to a TIFF, JPEG, PNG or
   single-page PDF.
3. **Run document intelligence** — call `usDocumentIntelligenceAdvance`
   (`POST /api/v3/us/document-intelligence-advance`) with
   `{ "country": "US", "idType": "driving license", "frontUrl": "...", "backUrl": "..." }`.
4. **Read the result** — the response returns `completeStatus`, `imageQuality`,
   `authenticityCheck`, `extractedFields`, predicted ID types and `graphicFields`.
   Gate onboarding on `completeStatus` + `authenticityCheck`, not OCR alone.

## Rules

- `400` = malformed request (check image URLs, `country`, `idType`); `409` =
  conflict/duplicate; `401` = re-authenticate. See `errors/signzy-problem-types.yml`.
- Document images contain PII/biometric data — handle per data-residency rules.
- No idempotency key; avoid blind retries (`conventions/signzy-conventions.yml`).
