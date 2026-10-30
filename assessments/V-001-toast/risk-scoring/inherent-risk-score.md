# Inherent Risk Score — Toast, Inc.

Scored with the six-factor method in the GRC program's [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md), before considering Toast's controls.

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 3 | Cardholder data and every sales record |
| System access | 3 | Supplies and manages the POS software and terminals inside the store |
| Operational dependency | 3 | No card sales without it |
| Internet exposure | 3 | Cloud payment platform connected to the card networks |
| Regulatory impact | 3 | Directly in PCI DSS scope |
| Subcontractor usage | 3 | Payment processing involves processors and card networks; additional encryption providers for some products |
| **Total** | **18** | |

---

## Result

**18 of 18: High**, the highest score of any vendor in the program. A full due diligence review is required.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only.*
