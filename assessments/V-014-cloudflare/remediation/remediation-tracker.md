# Remediation Tracker — Cloudflare (Website Hosting and Database)

Tracked in the GRC program's POA&M under **POAM-036** (SA-9).

---

## Tracker

| Finding ID | Severity | Remediation Action | Owner | Target | Status |
|---|---|---|---|---|---|
| F-01 | Low | Download and review the SOC 2 Type II report and the PCI DSS AOC; record the review | Owner | 2026-12-08 | Open |
| F-02 | Medium | Time Travel restore test on the preview database, recorded; `audit_log` export with each weekly review | Owner (Michael runs the restore) | Before the register goes live (CR-005 acceptance); exports from 2026-11-14 | Open |
| F-03 | Low | Accept self-serve breach-notice terms; yearly review and before customer accounts | Owner | 2027-11-08, or CR-002 step 6 if sooner | Open (accepted) |
| F-04 | Medium | Compensating control (website ADR-0030) **done 2026-11-07**; own limiter before the first paid-service route; re-check issue #16097 at website Phase 4; Free vs Paid decision before CR-005 | Owner | Website Phase 4 | Open |
| F-05 | Medium | Recovery codes into the Owner's password manager (SYS-022; revised 2026-11-11, was Bitwarden); Cloudflare account audit log added to the weekly review | Owner (codes); IT Technician (review) | 2026-11-15 | Open |

---

## Status Legend

- **Open** — remediation not yet started
- **In Progress** — remediation underway
- **Overdue** — past its target with no evidence of remediation
- **Closed** — remediation verified complete

## Linkage

- Findings source: [Vendor Risk Findings](../findings/vendor-risk-findings.md)
- Final decision: [Vendor Risk Assessment Report](../final-assessment/vendor-risk-assessment-report.md)
- Program rollup: POAM-036 (SA-9); change CR-002; PR-004 (weekly log review); PR-009 (credentials)

---

*This document is a simulation for educational and portfolio purposes only.*
