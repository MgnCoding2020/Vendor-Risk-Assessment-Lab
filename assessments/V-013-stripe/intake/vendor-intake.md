# Vendor Intake — Stripe (Card Payments, Test Mode)

Captured 2026-11-10, **one day after the service went into use**. The Owner decided on 2026-11-09 that Stripe would be assessed before the website's card payments went live (CR-002 step 5). The build went first:

- the Stripe set-up ran on 2026-11-09;
- card payments at the counter went live the same evening;
- card refunds went live that night.

Under [P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) step 5, a vendor in use but never assessed is assessed as soon as it's found; the decision is continue, continue with conditions, or exit.

**The lab runs in Stripe's test mode only:** no real money and no real card data, ever. The assessment is of the service as the company would rely on it.

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Stripe, Inc. |
| **Vendor ID** | V-013 |
| **Service** | Card payments: **Stripe Terminal** (server-driven, simulated reader) at the counter, **Checkout** online (website Phase 5), the Refunds API, webhooks. Standard self-serve account, **test mode (sandbox) only** |
| **System** | SYS-020, the online ordering website and counter register ([CR-002](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-002-online-ordering-website.md)); replaces Toast's payments under [CR-005](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-005-toast-pos-replacement.md) |
| **Internal business owner** | Olivia Carter (Owner) |
| **Requested by** | Owner, via CR-002 and CR-005 |
| **In use since** | 2026-11-09: set-up at 21:29 UTC, card payments live that evening, card refunds that night |
| **Intake date** | 2026-11-10 |

---

## Data Handled by the Vendor

| Data | Where | Classification |
|---|---|---|
| Card data (number, expiry): in the lab, only Stripe's published **test** cards | Stripe's card data vault; the site never sees a card number | Cardholder data (Restricted), by design; none real in the lab |
| Payment amounts, a fixed description, the site's own payment ID in metadata | PaymentIntents | Internal |
| Refund amounts and reasons ("requested by customer") | Refunds | Internal |
| The store's Terminal location (a fictional address) and one simulated reader | Terminal | Internal |
| Webhook events about payments and refunds, sent to the website | Webhook endpoint (production URL) | Internal |
| The account owner's identity, and the account's security history | Stripe account | Confidential |

**What the site keeps:** Stripe's IDs, amounts, statuses and decline codes, never card details (website ADR-0036, ADR-0037).

---

## System Access

Stripe has **no access to the company's systems**. Its only inward path is signed webhooks, which the website verifies before it acts on them (website ADR-0035). The company's access to Stripe is through:

- a **restricted API key** with custom permissions: payments, Terminal readers, refunds, Checkout; nothing else;
- the Owner's Dashboard sign-in, with two-factor authentication. Stripe asked for it when the key was created, 2026-11-09.

A one-time set-up key was created and deleted the same day.

---

## Business Criticality

**Moderate today:** card payments at the counter, with cash as a working fallback. **High** when the register replaces Toast (CR-005) and online ordering starts (CR-002 step 6), because the shop then depends on Stripe to take card payments at all.

---

## Initial Risk Indicators

- **Payment provider:** in PCI DSS scope as the company's third-party service provider (Requirement 12.8) for both channels.
- **The company's PCI scope document** (website `docs/pci-scope.md`) and SAQ type aren't written yet.
- **A test-mode secret key was pasted into an AI chat on 2026-11-09.** It was expired the same day; the site uses a restricted key.
- **Standard self-serve terms:** no negotiated contract.

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only.*
