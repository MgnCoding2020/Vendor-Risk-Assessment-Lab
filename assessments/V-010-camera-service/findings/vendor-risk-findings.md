# Vendor Risk Findings — Cloud Camera Service

Cited outside this repository as `VRA-V010:F-01` to `VRA-V010:F-04`.

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | One camera account shared by the Owner and the Store Manager, MFA off | Access control | Medium | Separate accounts for the Owner and the Store Manager, MFA on both, logins in each person's own password manager or authenticator (PR-011 §5) | Open |
| F-02 | Footage kept 60 days; the program's rule is 30 | Retention (SI-12) | Low | Set retention to 30 days (P-010) | Open |
| F-03 | Vendor support permission left on "always allow" | Third-party access | Medium | Set support access to "ask each time"; grant only for a specific ticket; record grants in the maintenance log | Open |
| F-04 | Local video streaming enabled with the default password: anyone on the store network can watch | Device configuration (CM-6) | High | Turn off local streaming (the shop uses the cloud viewer only); move the cameras to the Devices segment (POAM-015) | Open |

The findings roll up to the program's POA&M under **POAM-027** (cameras, PE-6) and **POAM-026** (connected devices, network). Residual risk falls to **Low** once all four settings are changed.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
