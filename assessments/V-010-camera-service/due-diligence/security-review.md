# Security Due Diligence Review — Cloud Camera Service

Based on the vendor's answers to the program's [vendor intake questionnaire](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-intake-questionnaire.md), its terms of service and the camera settings, reviewed 2026-11-02 (simulated: the vendor is fictional).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Account access | Who can view footage, and how they sign in | **One account shared** by the Owner and the Store Manager; MFA available but off. The platform supports separate users with their own logins | F-01 |
| Retention | How long footage is kept | Default is **60 days**; the program's rule is 30 days (PR-011 §5, P-010) | F-02 |
| Vendor access to footage | Support staff viewing video | Support can view footage only after the customer grants a time-limited permission in the app, which is logged. **The permission setting is "always allow"**, left by the installer | F-03 |
| Local video stream | Direct access on the store network | **Local streaming (RTSP) is enabled** with the camera's default password, so anyone on the same network could watch | F-04 |
| Independent assurance | Audits | SOC 2 Type II report provided under NDA (summary reviewed: no exceptions affecting customer data) | Adequate |
| Breach notification | Terms of service | **Customers are notified within 72 hours** of a confirmed incident affecting their data | Adequate |
| Firmware | Update method | Signed firmware updated automatically by the vendor | Adequate |
| Encryption | Video in transit and at rest | Encrypted in transit and at rest in the vendor's cloud | Adequate |
| Camera placement | Keypad visibility | Not yet checked (POAM-027) | Covered by PR-011 §5 |

---

## Summary

The vendor's platform is mature (independent audit, 72-hour notice, encryption, signed updates), but it was set up with convenience defaults: a shared login, long retention, standing support access and an open local stream. All four are settings the shop can change itself.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
