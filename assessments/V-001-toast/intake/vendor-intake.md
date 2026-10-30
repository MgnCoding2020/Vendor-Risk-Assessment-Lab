# Vendor Intake — Toast, Inc. (Toast POS and xtraCHEF)

Captured on 2026-10-30. Toast has been in use since the security program began (2026-02-01) but had **never been formally assessed**; the program's POA&M tracks that gap as POAM-006 (SA-9).

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Toast, Inc. |
| **Vendor ID** | V-001 |
| **Service** | Toast POS (in-store order taking and card-present payment processing) and xtraCHEF (inventory and invoices) |
| **Internal business owner** | Olivia Carter (Owner) |
| **Day-to-day owner** | Daniel Lopez (Store Manager) |
| **In use since** | 2026-02-01 (program start); exact contract date not recorded |
| **Intake date** | 2026-10-30 |

---

## Service Description

Every sale goes through Toast: terminals in the store take orders and card payments, and Toast's cloud processes the transactions and passes them to the card networks. xtraCHEF, part of Toast, holds inventory and supplier invoices. Staff sign in to the terminals with personal PINs (see the program's [roles.md](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/00-company-profile/org/roles.md)).

---

## Data Handled by the Vendor

| Data | Classification |
|---|---|
| Cardholder data (card-present transactions) | Restricted |
| Sales and transaction records | Restricted |
| Staff POS accounts and roles | Confidential |
| Inventory and supplier invoices (xtraCHEF) | Internal |

The company does not store card numbers itself (Payment Card Data Protection Policy, P-004).

---

## System Access

Toast supplies and manages the POS software and terminals in the store and runs the payment-processing cloud. The company administers its own POS users and roles.

---

## Business Criticality

**Critical.** If Toast is unavailable, the store can't take card payments.

---

## Regulatory & Compliance Considerations

- **PCI DSS applies directly**: Toast is the company's payment service provider, so PCI DSS Requirement 12.8 (managing third-party service providers) applies in full
- The company must also validate its own PCI DSS compliance (a Self-Assessment Questionnaire, SAQ)

---

## Initial Risk Indicators

- Highest data sensitivity in the program (cardholder data)
- In use for eight months without an assessment
- No record of Toast's PCI compliance evidence or of who is responsible for which PCI requirements

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only.*
