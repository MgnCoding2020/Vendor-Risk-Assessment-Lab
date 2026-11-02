# Vendor Risk Findings — Bitwarden (Password Manager)

Cited outside this repository as `VRA-V009:F-01` to `VRA-V009:F-05`.

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | No event log on the Free plan: nobody can see who viewed or changed a shared credential | Logging (AU-2) | Low | Accepted as program exception **EXC-006**: two members only, per-item password history, rotation on every staff or vendor change, monthly membership check. Revisit if a third member is ever needed (Teams plan) | Open (accepted) |
| F-02 | The Free plan can't enforce two-step login or master password strength for members | Authentication (IA-5) | Medium | Both members turn on two-step login (authenticator app) and use long master passwords at setup; the IT Technician confirms both monthly (PR-008 §3) and records it | Open |
| F-03 | Bitwarden's SOC 2 Type II report has not been obtained or reviewed | Assurance | Low | Request the report after onboarding; record the review (period, exceptions, customer responsibilities) | Open |
| F-04 | If both members lose their master passwords or two-step devices, the vault can't be recovered (zero-knowledge) | Availability | Medium | Each member stores their two-step recovery code sealed with the break-glass credentials kept by the Owner; quarterly encrypted export to the offline drives (PR-012); the IT Technician and the Owner never rely on one device alone | Open |
| F-05 | Standard terms only: no negotiated 72-hour breach-notification clause (P-008 §4) | Contractual | Low | Record what Bitwarden's published terms say about incident notification; accept for a zero-knowledge service (encrypted vault contents aren't readable by the vendor), reviewed yearly | Open |

---

## Notes

No finding blocks onboarding. With F-02 and F-04's controls in place at setup, residual risk is **Low**. The findings roll up to the program's POA&M under **POAM-021** (IA-5, the password manager).

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only.*
