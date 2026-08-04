# first direct (first-direct)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
