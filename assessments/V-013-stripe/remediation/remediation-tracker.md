# Remediation Tracker — Stripe (Card Payments, Test Mode)

Tracked in the GRC program's POA&M under **POAM-037** (SA-9; PCI DSS 12.8).

---

## Tracker

| Finding ID | Severity | Remediation Action | Owner | Target | Status |
|---|---|---|---|---|---|
| F-01 | Medium | Request and review the current SOC 2 Type II (or a bridge letter) and the PCI DSS service-provider AOC; record the period, exceptions, complementary user entity controls and the 12.8.5 responsibility split | Owner | 2026-12-10 | Open |
| F-02 | Medium | Write the website's `docs/pci-scope.md` for both channels with the SAQ type verified against current PCI SSC and Stripe documents; update the hub crosswalk | Owner (Michael writes it) | Before CR-002 step 6 (online ordering) | Open |
| F-03 | Low | Accept standard breach-notice terms; yearly review | Owner | 2027-11-10 | Open (accepted) |
| F-04 | Low | Accept no uptime commitment; compensating controls in place (cash fallback, the register's own status check); re-decide at CR-005 | Owner | CR-005 cutover | Open (accepted) |
| F-05 | Medium | Recovery codes into Bitwarden's admin collection; Stripe security history and request log in the weekly log review; restricted key rotated yearly | IT Technician (codes, review); Owner (key) | 2026-11-15 (codes); 2026-11-14 (first review); 2027-11-09 (key) | Open |
| F-06 | Low | Confirm with Stripe how to subscribe to sub-processor changes, then subscribe | Owner | 2026-12-10 | Open |

---

## Status Legend

- **Open** — remediation not yet started
- **In Progress** — remediation underway
- **Overdue** — past its target with no evidence of remediation
- **Closed** — remediation verified complete

## Linkage

- Findings source: [Vendor Risk Findings](../findings/vendor-risk-findings.md)
- Final decision: [Vendor Risk Assessment Report](../final-assessment/vendor-risk-assessment-report.md)
- Program rollup: POAM-037 (SA-9; PCI DSS 12.8); changes CR-002 and CR-005; PR-004 (weekly log review); PR-009 (credentials)

---

*This document is a simulation for educational and portfolio purposes only.*
