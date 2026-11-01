# Inherent Risk Score — Espresso Machine Service Company

Inherent risk is the risk a vendor introduces **before** its security controls are considered. This score uses the six-factor numeric method in the GRC program's [Inherent Risk Scoring Worksheet](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/inherent-risk-scoring-worksheet.md).

---

## Scoring Factors

| Factor | Score (1–3) | Rationale |
|---|---|---|
| Data sensitivity | 1 | Machine telemetry and business contact details only |
| System access | 3 | Remote control of a device on the store network, currently the same network as the POS. Drops to 2 once the device is on the isolated Devices segment |
| Operational dependency | 3 | Most of the menu depends on the machine |
| Internet exposure | 2 | Vendor cloud with a public portal login; the machine makes outbound connections only |
| Regulatory impact | 1 | No cardholder or personal data held |
| Subcontractor usage | 2 | Cloud hosting provider; some field visits by subcontracted technicians |
| **Total** | **12** | |

---

## Result

| Total score | Tier |
|---|---|
| 6–8 | Low |
| **9–13** | **Moderate** ← 12 |
| 14–18 | High |

**Overall Inherent Risk: Moderate.** The low data sensitivity is outweighed by the remote access path into the store network, so a full due diligence review is still required.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
