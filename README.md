# first direct (first-direct)

first direct is a telephone- and internet-based retail bank and a division of HSBC UK Bank plc, headquartered in Leeds, England and launched in 1989. It offers personal current accounts, savings, credit cards, loans, mortgages and insurance to UK consumers, operating with no physical branches of its own. As an HSBC brand it participates in the UK Open Banking regime under HSBC UK — one of the nine CMA9 banks mandated by the Competition and Markets Authority — and is regulated by the FCA and PRA.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/first-direct/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/first-direct/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- United Kingdom
- Payments
- Account Information
- Open Data
- HSBC
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## Open Banking posture

first direct does not run a stand-alone developer portal. Its UK Open Banking APIs are published under HSBC, conformant to the Open Banking Implementation Entity (OBIE) standards:

- A **public, unauthenticated Open Data API** on the shared HSBC host `https://api.hsbc.com/open-banking/v2.2` — confirmed live (HTTP 200), with "first direct" appearing as a distinct brand in the Personal Current Accounts reference data.
- The **FAPI-secured OBIE Read/Write APIs** — Account & Transaction Information (AIS), Payment Initiation (PIS) and Confirmation of Funds (CBPII) — onboarded and documented at HSBC's developer portal `https://develop.hsbc.com/`, which serves the HSBC UK, first direct and M&S Bank brands. These require OAuth2/OIDC, mutual-TLS, PSD2 strong customer authentication and OBIE/eIDAS certificates.

## APIs

### first direct Open Data API

Public, unauthenticated OBIE Open Data API exposing first direct personal current account product reference data on the shared HSBC Open Data host. Confirmed live (HTTP 200).

- **Human URL:** [https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)
- **Base URL:** `https://api.hsbc.com/open-banking/v2.2`

#### Properties

- [OpenAPI](openapi/obie-opendata-openapi.json) — shared OBIE Open Data standard (Swagger 2.0, v1.3)
- [Documentation](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)
- [API Reference](https://api.hsbc.com/open-banking/v2.2/personal-current-accounts)

### first direct Account and Transaction Information API (AIS)

OBIE Read/Write AIS API for first direct accounts, documented via HSBC's developer platform. FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://develop.hsbc.com/](https://develop.hsbc.com/)

#### Properties

- [OpenAPI](openapi/obie-account-info-openapi.yaml) — shared OBIE Read/Write standard (OpenAPI 3.0.0, v4.0.1)
- [Documentation](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)

### first direct Payment Initiation API (PIS)

OBIE Read/Write PIS API for first direct accounts, documented via HSBC's developer platform. FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://develop.hsbc.com/](https://develop.hsbc.com/)

#### Properties

- [OpenAPI](openapi/obie-payment-initiation-openapi.yaml) — shared OBIE Read/Write standard (OpenAPI 3.0.0, v4.0.1)
- [Documentation](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)

### first direct Confirmation of Funds API (CBPII)

OBIE Read/Write CBPII API for first direct accounts, documented via HSBC's developer platform. FAPI-secured (OAuth2/OIDC + mTLS + PSD2 SCA).

- **Human URL:** [https://develop.hsbc.com/](https://develop.hsbc.com/)

#### Properties

- [OpenAPI](openapi/obie-confirmation-funds-openapi.yaml) — shared OBIE Read/Write standard (OpenAPI 3.0.0, v4.0.1)
- [Documentation](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)

## Common Properties

- [Website](https://www.firstdirect.com/)
- [Developer Portal](https://develop.hsbc.com/)
- [Documentation](https://develop.hsbc.com/knowledge-article/get-started-open-banking-apis)
- [Open Banking](https://www.firstdirect.com/ways-to-bank/open-banking/)
- [GitHub Organization](https://github.com/hsbc)
- [LinkedIn](https://www.linkedin.com/company/first-direct)
- [Support](https://www.firstdirect.com/help/)
- [Terms of Service](https://www.firstdirect.com/legals/terms-and-conditions/)
- [Privacy Policy](https://www.firstdirect.com/privacy/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
