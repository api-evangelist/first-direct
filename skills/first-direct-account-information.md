---
name: Retrieve account information (AIS)
description: As an AISP, obtain PSU consent and read first direct account, balance and transaction data via the OBIE Account & Transaction API.
api: openapi/obie-account-info-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccounts, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Retrieve account information (AIS)

Read-only access to a PSU's first direct accounts through the OBIE Account &
Transaction Information API (delivered by HSBC UK). Requires FCA/TPP authorisation,
OBIE/eIDAS certificates and FAPI security.

## Prerequisites
- OAuth2 client credentials token with the `accounts` scope (TPPOAuth2Security).
- Mutual-TLS transport certificate; sign requests where required (`x-jws-signature`).
- Send `x-fapi-interaction-id` (RFC 4122 UUID) on every call for correlation.

## Steps
1. **Create an account-access consent** — `CreateAccountAccessConsents`. Declare the
   `Permissions` (e.g. ReadAccountsDetail, ReadBalances, ReadTransactionsDetail) and
   optional expiry. Returns a `ConsentId` in status `AwaitingAuthorisation`.
2. **Redirect the PSU for authorisation** — the customer completes strong customer
   authentication (SCA) via the PSU authorization-code flow (PSUOAuth2Security). The
   consent moves to `Authorised`.
3. **List accounts** — `GetAccounts` with the PSU access token to enumerate authorised
   accounts and their `AccountId`s.
4. **Read balances** — `GetAccountsAccountIdBalances` for a given `AccountId`.
5. **Read transactions** — `GetAccountsAccountIdTransactions`; page with the `Links.Next`
   URL and `Meta.TotalPages`; filter with `fromBookingDateTime`/`toBookingDateTime`.

## Conventions & errors
- Pagination: `Links` (Self/Next/…) + `Meta`. See `conventions/first-direct-conventions.yml`.
- Errors: `OBErrorResponse1` envelope with `UK.OBIE.*` codes. See `errors/first-direct-problem-types.yml`.
- A `403` means the token/consent lacks the permission; a `401` means re-authenticate.
