# Vendor Risk Findings — Cloudflare (Website Hosting and Database)

Cited outside this repository as `VRA-V014:F-01` to `VRA-V014:F-05`.

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | Cloudflare's SOC 2 Type II report and PCI DSS Attestation of Compliance haven't been obtained or reviewed; the public ISO scope doesn't name Workers or D1 | Assurance | Low | The Owner, as Super Administrator, accepts the confidentiality statement and downloads both from the dashboard; record the review (period, exceptions, complementary user entity controls). D1 isn't in Cloudflare's PCI list: confirm no card data ever goes to D1 (the website design already says so) | Open |
| F-02 | D1 point-in-time restore reaches back only 7 days on the Free plan and has never been tested here; the audit log can't be recovered beyond that | Availability, integrity (CP-9, AU-9) | Medium | Test a Time Travel restore on the preview database and record it (website plan §9); export `audit_log` with each weekly log review (PR-004, from 2026-11-14) so the record survives beyond 7 days | Open |
| F-03 | Self-serve terms: breach notice "without undue delay", no fixed 72-hour window (P-008 §4) | Contractual | Low | Accept for the Free plan, which holds no cardholder or real personal data; review yearly and before customer accounts go live (CR-002 step 6) | Open (accepted) |
| F-04 | No uptime commitment on the Free plan, and a documented security feature (the Rate Limiting binding) doesn't enforce on this account (open issue #16097, no fix date) | Availability, abuse protection (SC-5) | Medium | Compensating control in place: no anonymous request writes to the database (website ADR-0030, 2026-11-07). Before the first route that calls a paid service (Stripe, AI): the website's own limiter on a Durable Object. Re-check #16097 at the start of website Phase 4. Re-decide the plan (Free vs Paid) before the register replaces Toast (CR-005) | Open |
| F-05 | The account's two-factor recovery codes have no recorded home, and the Cloudflare account audit log (changes to settings and secrets) isn't reviewed | Account security (IA-5, AU-6) | Medium | Store the recovery codes in the password manager's admin collection once Bitwarden is onboarded (CR-003, 2026-11-15; PR-009); add the Cloudflare account audit log to the weekly log review (PR-004) | Open |

---

## Notes

No finding requires leaving Cloudflare. With F-02's restore test and F-05's recovery codes in place, residual risk is **Low**. The findings roll up to the program's POA&M under **POAM-036** (SA-9), which was opened for this assessment being overdue.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only.*
