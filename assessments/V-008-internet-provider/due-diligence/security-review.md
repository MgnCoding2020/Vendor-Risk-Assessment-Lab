# Security Due Diligence Review — Internet Service Provider

Based on the service contract, the provider's small-business terms and the router's settings, reviewed 2026-11-02 (simulated: the vendor is fictional).

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Router management | Who controls the router | The provider manages it remotely and **holds the admin password**; the shop can't turn remote management off | F-01 |
| Router mode | Is the router a security boundary? | It's in full router mode, with its own Wi-Fi network **still broadcasting**, against the device baseline (PR-015 §7) | F-02 |
| Outage support | Restoration commitment | Small-business plan: "best effort", **no restoration time** in the contract | F-03 |
| Breach notification | Contract terms | No incident-notification commitment for customer account data | F-04 |
| Encryption | Protection of traffic | The provider doesn't need to be trusted with content: payments are encrypted end to end by the POS provider and cloud services use TLS | Adequate |
| Firmware | Updates | Pushed by the provider | Adequate (the provider's responsibility) |

## Summary

The provider can't read the shop's important traffic, so the confidentiality risk is low. The real issues are **control and availability**: the shop doesn't control a device at the edge of its own network, and there's no commitment on how fast the internet comes back. The answer is to treat the router as **outside** the shop's network (the firewall is the boundary) and to plan for outages rather than rely on the provider.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
