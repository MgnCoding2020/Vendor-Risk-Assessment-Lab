# Inherent Risk Score — Stripe (Card Payments, Test Mode)

Scored with the program's six-factor [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md), before controls are considered. It's scored as the service the company relies on, not as the lab's test mode, which would make every factor look lower than it really is.

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 3 | Stripe processes and stores cardholder data on the company's behalf, for both channels. The lab uses only Stripe's test cards, but the service is designed for real card data |
| System access | 2 | No access into the company's systems. Its signed webhooks decide which orders are paid and refunded, and the company's key can take payments and refund money |
| Operational dependency | 2 | Card payments stop if it's down; cash still works at the counter. **3** once the register replaces Toast and online ordering starts |
| Internet exposure | 3 | Internet-facing API, Dashboard, webhooks and (from Phase 5) hosted Checkout pages |
| Regulatory impact | 3 | PCI DSS: Stripe is the company's third-party service provider for card payments (Requirement 12.8); the company's own SAQ depends on how Stripe is used |
| Subcontractor usage | 3 | Stripe's published service-provider list names several cloud and data platforms hosting business-user and end-customer data, including Amazon Web Services, Microsoft Azure, Google, Snowflake and Databricks ([list](https://stripe.com/legal/service-providers), updated 2026-09-27) |
| **Total** | **16** | |

---

## Result

| Total score | Tier |
|---|---|
| 6–8 | Low |
| 9–13 | Moderate |
| **14–18** | **High** ← 16 |

**Overall Inherent Risk: High**, matching the tier recorded in the hub's vendor inventory. A full assessment is required, with yearly reassessment ([P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) §3). **Re-score at the CR-005 cutover:** operational dependency rises to 3, giving 17.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only.*
