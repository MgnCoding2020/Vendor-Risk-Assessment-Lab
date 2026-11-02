# Vendor Risk Findings — Internet Service Provider

Cited outside this repository as `VRA-V008:F-01` to `VRA-V008:F-04`.

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | The provider manages the router remotely and holds its admin password; the shop can't disable that access | Third-party access | Medium | Treat the router as **untrusted**: ask the provider to put it in bridge (modem-only) mode where offered, so the shop's firewall (FW-01) is the only boundary; record the provider's management as a vendor dependency | Open |
| F-02 | The router's own Wi-Fi is still broadcasting | Device configuration (CM-6) | Medium | Turn the router's Wi-Fi off (or have the provider do it); all Wi-Fi comes from the shop's access points (PR-015 §7) | Open |
| F-03 | No restoration time for outages on the small-business plan | Availability (CP-2) | Medium | Decide on cellular failover (PR-005 §5, Owner decision); keep Toast Offline Mode and cash as the fallback; consider a business plan with a restoration commitment at renewal | Open |
| F-04 | No incident-notification commitment for customer account data | Contractual | Low | Ask at renewal (P-008 §4); low data sensitivity, accepted until then | Open |

Findings roll up to the program's POA&M under **POAM-015** (network segmentation and boundary) and **POAM-005** (contingency). Residual risk is **Low** once the router sits outside the boundary and the Owner has decided on failover.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
