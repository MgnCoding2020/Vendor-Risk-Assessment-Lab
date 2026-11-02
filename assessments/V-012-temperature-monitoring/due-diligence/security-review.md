# Security Due Diligence Review — Temperature Monitoring Service

Based on the vendor's questionnaire answers, terms and the account settings, reviewed 2026-11-02 (simulated: the vendor is fictional).

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Account ownership | Who owns the dashboard account | Created by the vendor's installer in the **Store Manager's personal email**; MFA available but off | F-01 |
| Alerts | Who is told when a fridge warms up | Only the **Store Manager's personal phone**; nobody else is alerted out of hours or on days off | F-02 |
| Record keeping | Access to the food-safety log | Kept in the cloud for the subscription; exportable as CSV, but **not exported** by the shop | F-03 |
| Breach notification | Terms | "Prompt" notification; **no timeline** | F-04 |
| Device security | Sensor firmware and connections | Outbound-only connections; firmware updated by the vendor over the air | Adequate |
| Assurance | Audits | No SOC 2 or ISO 27001; a security overview is provided. Proportionate for a vendor holding only temperature data | Adequate (low data sensitivity) |

## Summary

A low-exposure vendor whose risks are about **ownership and continuity**, not security breaches: the account and the alerts depend on one person's personal email and phone, and the food-safety record has never been exported.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
