---
name: Initiate a domestic payment (PIS)
description: As a PISP, create a domestic payment consent, obtain PSU authorisation, then initiate and track a domestic payment via the OBIE Payment Initiation API.
api: openapi/obie-payment-initiation-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a domestic payment (PIS)

Initiate a single immediate domestic (UK Faster Payments) payment from a PSU's first
direct account through the OBIE Payment Initiation API. Requires FCA/TPP authorisation,
OBIE/eIDAS certificates and FAPI security.

## Prerequisites
- OAuth2 client credentials token with the `payments` scope (TPPOAuth2Security).
- Mutual-TLS transport certificate and request signing (`x-jws-signature`).
- **Idempotency**: send a unique `x-idempotency-key` on every write (valid 24 hours;
  the request is processed only once per key).

## Steps
1. **Create the payment consent** — `CreateDomesticPaymentConsents` with the
   `Initiation` (debtor/creditor accounts, `InstructedAmount`, reference). Returns a
   `ConsentId` in `AwaitingAuthorisation`.
2. **PSU authorisation (SCA)** — redirect the customer to authorise via the
   authorization-code flow (PSUOAuth2Security); consent becomes `Authorised`.
3. **(Optional) Confirm funds** — `GetDomesticPaymentConsentsConsentIdFundsConfirmation`
   to check the account can cover the amount before initiating.
4. **Initiate the payment** — `CreateDomesticPayments` referencing the authorised
   `ConsentId` and the identical `Initiation` block. Returns a `DomesticPaymentId`.
5. **Track status** — `GetDomesticPaymentsDomesticPaymentId` to poll the payment
   `Status` (e.g. `AcceptedSettlementInProcess` → `AcceptedSettlementCompleted`).

## Conventions & errors
- Reuse the same `x-idempotency-key` on retries of step 4 to avoid duplicate payments.
- Errors: `OBErrorResponse1` / `UK.OBIE.*`. A `409` typically signals an idempotency or
  consent-state conflict. See `errors/first-direct-problem-types.yml`.
