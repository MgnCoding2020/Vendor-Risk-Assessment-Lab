# Vendor Risk Findings — Temperature Monitoring Service

Cited outside this repository as `VRA-V012:F-01` to `VRA-V012:F-04`.

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | Dashboard account in the Store Manager's personal email, MFA off | Account ownership | Medium | Move to a company-owned account with MFA; login in the password manager (PR-011 §3) | Open |
| F-02 | Alerts go only to the Store Manager's personal phone | Continuity | Medium | Add the Shift Leaders and the Owner as alert contacts; document who responds out of hours (PR-011 §6) | Open |
| F-03 | The food-safety log has never been exported | Records (SI-12, CP-9) | Low | Monthly CSV export to the offline backup (PR-012); kept 2 years (P-010) | Open |
| F-04 | No breach-notification timeline | Contractual | Low | Ask for a 72-hour commitment at renewal (P-008 §4); low data sensitivity, so accepted until then | Open |

The findings roll up to the program's POA&M under **POAM-026** (connected devices). Residual risk is **Low** once F-01 and F-02 are fixed.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
