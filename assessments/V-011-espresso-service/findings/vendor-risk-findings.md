# Vendor Risk Findings — Espresso Machine Service Company

Findings from the due diligence review. Outside this repository they are cited as `VRA-V011:F-01` to `VRA-V011:F-05` (see the program's [identifier conventions](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/00-company-profile/org/identifiers.md)).

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | Vendor technicians can connect to the machine at any time without the shop's approval, and the shop never sees the session log; the machine shares a network with the POS | Third-party remote access (MA-4, SC-7) | High | Turn on "require customer approval" for remote sessions; ask for the session log at each quarterly visit and record sessions in the maintenance log (PR-011 §4); move the machine to the Devices segment (POAM-015) | Open |
| F-02 | The machine's local service menu uses a vendor-wide PIN, the same on every machine of this model | Authentication (on-site) | Medium | Ask the vendor to set a unique service PIN for this machine, stored in the password manager; until then, technicians are always supervised (PR-010 §4) | Open |
| F-03 | No independent security assurance (no SOC 2 or ISO/IEC 27001) | Assurance / Evidence | Medium | Accept for a low-data vendor, with compensating controls: network isolation, approval for remote sessions, supervised visits. Re-check yearly | Open |
| F-04 | The contract defines no breach-notification timeline ("without undue delay") | Incident response / Contractual | Medium | Add a 72-hour notification clause at the contract renewal (2027-01-15); recorded in the vendor breach playbook (IRP-006 §4) meanwhile | Open |
| F-05 | The portal account was created in the Store Manager's personal email, with MFA off | Account ownership | Medium | Move the portal to a company-owned account (the IT Technician's admin mailbox once available), turn on MFA, store the login in the password manager (PR-009, PR-011 §3) | Open |

---

## Notes

The device has been in use since 2026-01-15, so this is a continue-or-exit decision, not an onboarding approval. None of the findings justifies exit. With the conditions met, residual risk falls from Moderate to **Low**, mainly because network isolation removes the path from the machine to the POS. The findings roll up to the GRC program's POA&M under **POAM-026** (MA-4, SC-7).

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
