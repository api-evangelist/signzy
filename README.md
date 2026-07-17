# Signzy (signzy)

Signzy is a global identity verification, KYC, KYB and AML compliance platform founded in Bengaluru, India in 2015. Its API marketplace exposes 240+ bespoke verification building blocks - document OCR, liveness and face match, deepfake detection, Aadhaar/PAN and other India checks, US ID and business verification, AML/sanctions/PEP screening, bank verification, Video KYC and Aadhaar eSign - behind a single token-authenticated REST API across India, the US, the Middle East and APAC.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/signzy/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/signzy/refs/heads/main/apis.yml)

## Tags

- Identity Verification
- KYC
- KYB
- AML
- Onboarding
- Compliance
- RegTech

## Timestamps

- **Created:** 2026-07-17
- **Modified:** 2026-07-17

## Authentication

Signzy uses a LoopBack-style token flow. `POST /api/customers/login` with a `username` and API key (`password`) returns an access token in the `id` field. That token is then sent as the **raw value** of the `Authorization` header (no `Bearer` prefix) on every subsequent call. See [authentication/signzy-authentication.yml](authentication/signzy-authentication.yml).

- **Production host:** `https://api.signzy.app`
- **Preproduction host:** `https://api-preproduction.signzy.app`

## APIs

### Signzy Identity Verification API

Global document OCR, liveness detection, face match and deepfake / synthetic-fraud checks that auto-read identity documents (driver's license, passport, national IDs) and verify the presented person in real time.

- **Human URL:** [https://www.signzy.com/use-cases/identity-verification-api/](https://www.signzy.com/use-cases/identity-verification-api/)
- **Base URL:** `https://api.signzy.app`

#### Tags

- Identity Verification
- OCR
- Liveness
- Face Match
- Deepfake

#### Properties

- [Documentation](https://docs.signzy.com)
- [API Reference](https://www.signzy.com/us/use-cases/identity-verification-api/)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/signzy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Signzy Aadhaar Verification API

Verifies an Indian Aadhaar (national ID) number with explicit consent and returns the masked demographic details on record via `POST /api/v3/aadhaar/verify`.

- **Human URL:** [https://docs.signzy.com/api-marketplace/aadhaar-verification](https://docs.signzy.com/api-marketplace/aadhaar-verification)
- **Base URL:** `https://api.signzy.app`

#### Tags

- Aadhaar
- India
- Identity
- KYC

#### Properties

- [Documentation](https://docs.signzy.com/api-marketplace/aadhaar-verification)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/signzy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Signzy PAN Verification API

Validates an Indian PAN (Permanent Account Number) against the income-tax database and returns name and status via `POST /api/v3/pan/simple`.

- **Human URL:** [https://docs.signzy.com/api-marketplace/pan-verification](https://docs.signzy.com/api-marketplace/pan-verification)
- **Base URL:** `https://api.signzy.app`

#### Tags

- PAN
- India
- Tax Identity
- KYC

#### Properties

- [Documentation](https://docs.signzy.com)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/signzy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Signzy US Document Intelligence API

Reads and authenticates US identity documents (driver's license, passport) from an image URL, returning OCR-extracted fields, image quality and authenticity checks via `POST /api/v3/us/document-intelligence-advance`.

- **Human URL:** [https://docs.signzy.com/us-apis/id-intelligence-advance](https://docs.signzy.com/us-apis/id-intelligence-advance)
- **Base URL:** `https://api.signzy.app`

#### Tags

- US
- Document OCR
- Authenticity
- Identity

#### Properties

- [Documentation](https://docs.signzy.com/us-apis/id-intelligence-advance)
- [API Reference](https://www.signzy.com/us/verification-api-marketplace/)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/signzy.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)

### Signzy Business Verification (KYB) API

Know-Your-Business verification - EIN / SOS business lookups, UBO checks, bankruptcy and credit-underwriting reports across US states and Indian entities.

- **Human URL:** [https://www.signzy.com/us/verification-api-marketplace/](https://www.signzy.com/us/verification-api-marketplace/)
- **Base URL:** `https://api.signzy.app`

#### Tags

- KYB
- Business Verification
- EIN
- UBO

#### Properties

- [Documentation](https://docs.signzy.com)
- [API Reference](https://www.signzy.com/us/verification-api-marketplace/)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Signzy AML & Sanctions Screening API

Sanction-list, Politically Exposed Person (PEP) and adverse-media screening plus transaction monitoring, expanded through the 2024 Difenz acquisition.

- **Human URL:** [https://www.signzy.com/use-cases/kyc-aml-screening](https://www.signzy.com/use-cases/kyc-aml-screening)
- **Base URL:** `https://api.signzy.app`

#### Tags

- AML
- Sanctions
- PEP
- Adverse Media

#### Properties

- [Documentation](https://www.signzy.com/use-cases/kyc-aml-screening)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Signzy Bank Verification & Account Aggregator API

Bank account verification, name match, balance and transaction checks, and India Account Aggregator consent-based data pulls, including passbook OTP flows via `POST /api/v3/underwriting/get-passbook-otp`.

- **Human URL:** [https://www.signzy.com/fintech-apis/account-aggregator-api](https://www.signzy.com/fintech-apis/account-aggregator-api)
- **Base URL:** `https://api.signzy.app`

#### Tags

- Bank Verification
- Account Aggregator
- Penny Drop
- India

#### Properties

- [Documentation](https://www.signzy.com/fintech-apis/account-aggregator-api)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Signzy Video KYC API

RBI-compliant assisted Video KYC onboarding with agent-led liveness, document capture and audit trails for regulated customer onboarding.

- **Human URL:** [https://docs.signzy.com/vkyc/login-api](https://docs.signzy.com/vkyc/login-api)
- **Base URL:** `https://api.signzy.app`

#### Tags

- Video KYC
- Onboarding
- RBI

#### Properties

- [Documentation](https://docs.signzy.com/vkyc/login-api)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Signzy eSign & Digital Contracting API

Paperless Aadhaar eSign, eStamping and Contract360 lifecycle management for legally binding digital agreements.

- **Human URL:** [https://docs.signzy.com/contract360](https://docs.signzy.com/contract360)
- **Base URL:** `https://api.signzy.app`

#### Tags

- eSign
- Aadhaar eSign
- eStamping
- Contracts

#### Properties

- [Documentation](https://docs.signzy.com/contract360)
- [OpenAPI](openapi/signzy-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [GitHub Organization](https://github.com/signzy)
- [LinkedIn](https://www.linkedin.com/company/signzy)
- [Website](https://www.signzy.com/)
- [Documentation](https://docs.signzy.com)
- [Plans](plans/signzy-plans-pricing.yml)
- [Rate Limits](rate-limits/signzy-rate-limits.yml)
- [Fin Ops](finops/signzy-finops.yml)

## Company Notes

- **Founded:** 2015, Bengaluru, India (founders Ankit Ratan, Arpit Ratan, Ankur Pandey).
- **Funding:** ~$38.7M raised; $26M Series B in 2022. Investors include Kalaari Capital, SAP and Mastercard (strategic partner/investor, not an acquirer).
- **Acquisition (by Signzy):** Acquired Difenz in early 2024 to expand AML and transaction-monitoring capability.
- **Compliance:** ISO 27001 certified, SOC 2, GDPR, FATF-aligned, with data-localization/residency options.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
