# Vendor Risk Findings — Stripe (Card Payments, Test Mode)

Cited outside this repository as `VRA-V013:F-01` to `VRA-V013:F-06`.

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | Stripe's PCI DSS Attestation of Compliance (service provider) and SOC 2 Type II report haven't been obtained; the public SOC 3's period ended 2025-09-30, more than a year ago | Assurance (PCI DSS 12.8.4, SA-9) | Medium | Request the current SOC 2 Type II, or a bridge letter covering the gap, and the PCI DSS service-provider AOC from Stripe (signed in, as the account owner). Record the period, exceptions and complementary user entity controls, and which PCI DSS requirements Stripe manages for the company (12.8.5). Keep the documents out of the repositories (confidential); commit only the review facts | Open |
| F-02 | The company hasn't determined its own PCI DSS scope or SAQ type for the counter (Terminal) and online (Checkout) channels; the website's `docs/pci-scope.md` (plan §6.4) isn't written | Compliance (PCI DSS 12.5.2, 12.8) | Medium | Write the scope document for both channels, checking current SAQ eligibility against PCI SSC and Stripe documents and dating it; use Stripe's Dashboard guidance on which SAQ applies; update the hub's crosswalk from it. Before online ordering goes live (CR-002 step 6) | **Closed 2026-11-14**: website `docs/pci-scope.md` (SAQ A online, SAQ C counter, checked against PCI SSC and Stripe sources that day); hub crosswalk scope note; gaps tracked as hub POAM-040 (ASV scans) and POAM-041 (payment network segment) |
| F-03 | Standard terms: breach notice "without undue delay"; a fixed 48 hours only for GDPR or UK GDPR personal data; no fixed 72-hour window (P-008 §4) | Contractual | Low | Accept for a test-mode account with no real cardholder or personal data; review yearly | Open (accepted) |
| F-04 | No uptime commitment found for a standard account | Availability | Low | Accept, with compensating controls already in place: cash at the counter if Stripe is down, and the register asks Stripe directly when a webhook is late (website ADR-0036). Watch Stripe's status page during trading; re-decide at the CR-005 cutover | Open (accepted) |
| F-05 | Account housekeeping: the two-factor recovery codes have no recorded home; Stripe's security history isn't reviewed; a test-mode secret key was exposed in an AI chat on 2026-11-09 (expired the same day) | Account security (IA-5, AU-6) | Medium | Recovery codes into the Owner's password manager (Google Password Manager, program SYS-022; PR-009 §3a) by 2026-11-15. (Revised 2026-11-11: was Bitwarden's admin collection; owner-only codes don't belong in the vault the IT Technician shares.) Stripe's security history and API request log into the weekly log review (PR-004, from 2026-11-14). Restricted key yearly rotation (2027-11-09, website secrets inventory). Rule: keys go from the Dashboard straight into the local settings file or the Worker's secrets, never through a chat or a ticket. Consider a passkey for the Dashboard | Open |
| F-06 | The sub-processor list's email subscription link appeared (2026-11-10) to point to another company's sub-processor page, so the company may not receive Stripe's 30-day notice of changes | Contractual, supply chain | Low | Ask Stripe support for the correct way to subscribe; until confirmed, check the list during the yearly reassessment | Open |

---

## Notes

No finding requires leaving Stripe. With F-01 (current assurance documents) and F-02 (the company's own PCI scope) closed, residual risk is **Low**. The findings roll up to the program's POA&M under **POAM-037** (SA-9; PCI DSS 12.8), opened because the assessment came a day after the service went into use.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only.*
