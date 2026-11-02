# Inherent Risk Score — Bitwarden (Password Manager)

Scored with the program's six-factor [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md), before controls are considered.

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 3 | Every shared admin credential the company has |
| System access | 2 | No direct access to company systems, but holds the means of access to all of them |
| Operational dependency | 2 | Admin work and incident response slow down without it; trading doesn't |
| Internet exposure | 3 | Public cloud web vault and apps |
| Regulatory impact | 1 | No cardholder or personal data beyond two member emails |
| Subcontractor usage | 2 | Cloud hosting provider |
| **Total** | **13** | |

---

## Result

| Total score | Tier |
|---|---|
| 6–8 | Low |
| **9–13** | **Moderate** ← 13 |
| 14–18 | High |

**Overall Inherent Risk: Moderate**, at the top of the band, so a full due diligence review is done before onboarding ([P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) §3).

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only.*
