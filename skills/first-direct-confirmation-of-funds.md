---
name: Confirm availability of funds (CBPII)
description: As a CBPII, create a funds-confirmation consent, obtain PSU authorisation, then run a yes/no funds-availability check via the OBIE Confirmation of Funds API.
api: openapi/obie-confirmation-funds-openapi.yaml
operations: [CreateFundsConfirmationConsents, GetFundsConfirmationConsentsConsentId, CreateFundsConfirmations]
---

# Confirm availability of funds (CBPII)

Perform a card-based confirmation-of-funds check against a PSU's first direct account
through the OBIE Confirmation of Funds API. Returns a boolean — never a balance.

## Prerequisites
- OAuth2 client credentials token with the `fundsconfirmations` scope (TPPOAuth2Security).
- Mutual-TLS transport certificate and request signing.
- Unique `x-idempotency-key` on write operations (valid 24 hours).

## Steps
1. **Create the funds-confirmation consent** — `CreateFundsConfirmationConsents` with
   the `DebtorAccount` to be checked. Returns a `ConsentId` in `AwaitingAuthorisation`.
2. **PSU authorisation (SCA)** — the customer authorises the long-lived consent; it
   moves to `Authorised`. (Optionally re-read state with
   `GetFundsConfirmationConsentsConsentId`.)
3. **Confirm funds** — `CreateFundsConfirmations` referencing the authorised `ConsentId`
   plus the `InstructedAmount`. Response `Data.FundsAvailableResult.FundsAvailable`
   is `true`/`false`.

## Conventions & errors
- Errors use the `OBErrorResponse1` envelope with `UK.OBIE.*` codes. A
  `UK.OBIE.Resource.InvalidConsentStatus` means the consent is not `Authorised`.
- See `conventions/first-direct-conventions.yml` and `errors/first-direct-problem-types.yml`.
