# Inherent Risk Score — Microsoft (Microsoft 365)

Inherent risk is the risk a vendor introduces **before** its security controls are considered. This score uses the six-factor numeric method in the GRC program's [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md).

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 3 | Employee personal data, sign-in records, financial records, payroll export |
| System access | 3 | Hosts the identity provider and every admin role: the deepest access of any vendor |
| Operational dependency | 2 | Administration depends on it, but store sales run on Toast POS and continue during an outage |
| Internet exposure | 3 | Public cloud service, reachable from anywhere |
| Regulatory impact | 2 | Employee privacy; no cardholder data |
| Subcontractor usage | 3 | Multiple subprocessors, published by Microsoft |
| **Total** | **16** | |

---

## Result

| Total score | Tier |
|---|---|
| 6–8 | Low |
| 9–13 | Moderate |
| **14–18** | **High** ← 16 |

**Overall Inherent Risk: High.** A full due diligence review is required before the risk decision.

*Method note:* the earlier Northwind (V-002) assessment rated four factors qualitatively; this assessment uses the program's six-factor worksheet as written.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only.*
