# Security Due Diligence Review — Espresso Machine Service Company

This review uses the vendor's answers to the program's [vendor intake questionnaire](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-intake-questionnaire.md) and its service contract, received 2026-11-01 (simulated: the vendor is fictional), checked against the [due diligence checklist](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-due-diligence-checklist.md). Each gap is carried into the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Remote access control | Who can connect to the machine, when, and with what approval | Any vendor technician can connect at any time through the cloud. The platform offers a **"require customer approval"** setting for remote sessions, **off by default** and off on this machine. Sessions are logged by the vendor but the shop has never seen the log | F-01 |
| Technician accounts | Individual vs shared accounts | Technicians use individual accounts on the vendor's service platform (adequate). On site, the machine's **local service menu uses a vendor-wide PIN**, the same on every machine of this model | F-02 |
| Independent assurance | SOC 2, ISO/IEC 27001 or similar | None. The vendor provided a two-page security overview (encrypted connections, signed firmware, staff background checks) | F-03 |
| Breach notification | Contract terms | The contract says the vendor will notify "without undue delay"; **no timeline** is defined | F-04 |
| Portal account | Ownership and authentication | The shop's portal account was created by the vendor in the Store Manager's personal email; MFA is available but off | F-05 |
| Firmware | How updates are delivered | Signed firmware pushed automatically by the vendor; release notes available on request | Adequate |
| Network requirements | What the machine needs | Outbound HTTPS to the vendor's cloud only; no inbound connections or port forwarding. This fits the planned Devices segment (P-005 §3) | Adequate |
| Data retention | Telemetry retention and deletion | Kept for the contract term plus one year; deleted on written request | Adequate |

---

## Summary

The vendor's platform has the right building blocks (individual technician accounts, signed firmware, outbound-only connections, an approval setting), but the shop hasn't used them, and the vendor offers no independent assurance. The biggest risk is not the vendor itself but where its device sits: on the same network as the POS. Isolating the machine on the Devices segment reduces most of the risk regardless of the vendor's own security.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
