# Inherent Risk Score — Cloudflare (Website Hosting and Database)

Scored with the program's six-factor [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md), before controls are considered.

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 2 | Staff names, directory IDs, roles, hashed sessions and the audit log; secrets including the staff app's certificate. No cardholder data, no customer accounts yet |
| System access | 2 | Runs the company's code and holds its secrets; a takeover of the account could deploy code and use the certificate to start sign-ins as the staff app (limited to `openid` and `profile`) |
| Operational dependency | 2 | The website and staff portal stop if it's down; trading doesn't, until the register replaces Toast (then 3) |
| Internet exposure | 3 | Public website and API on the internet |
| Regulatory impact | 2 | Serves the pages that send customers to Stripe Checkout, so it's part of the PCI DSS scope of the online channel (website `docs/pci-scope.md`, to be written); no card data itself |
| Subcontractor usage | 2 | Cloudflare's published sub-processor list names third-party cloud infrastructure providers (including Google, Oracle and AWS) supporting its Developer Platform, plus support tools ([list](https://www.cloudflare.com/gdpr/subprocessors/cloudflare-services/)) |
| **Total** | **13** | |

---

## Result

| Total score | Tier |
|---|---|
| 6–8 | Low |
| **9–13** | **Moderate** ← 13 |
| 14–18 | High |

**Overall Inherent Risk: Moderate**, at the top of the band, matching the tier recorded in the hub's vendor inventory. A full assessment is required ([P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) §3). **Re-score when the register replaces Toast** (CR-005): operational dependency rises to 3, giving **14, High**, which means a yearly reassessment from then on.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only.*
