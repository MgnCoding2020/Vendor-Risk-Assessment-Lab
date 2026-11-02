# Inherent Risk Score — Temperature Monitoring Service

Scored with the program's six-factor [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md).

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 1 | Temperature readings and alert contacts |
| System access | 1 | Sensors send data out only; no control of anything |
| Operational dependency | 2 | Food-safety alerts and the inspection record depend on it |
| Internet exposure | 2 | Cloud dashboard with a public login |
| Regulatory impact | 2 | The log is a food-safety record |
| Subcontractor usage | 1 | One cloud hosting provider |
| **Total** | **9** | |

| Total score | Tier |
|---|---|
| 6–8 | Low |
| **9–13** | **Moderate** ← 9 |
| 14–18 | High |

**Overall Inherent Risk: Moderate**, at the bottom of the band, driven by the food-safety record rather than security exposure. P-008 still requires a full review for Moderate, kept proportionate.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
