# Security Due Diligence Review — Bitwarden (Password Manager)

This review uses Bitwarden's **public** compliance and plan documentation, checked on 2026-11-02 (sources at the end), against the program's [due diligence checklist](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-due-diligence-checklist.md). Gaps go to the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Encryption | Vault encryption model | **End-to-end encryption** for all vault data, decryptable only with the member's master password; **zero-knowledge** architecture, so Bitwarden can't read vault contents (AES-256, keys derived with PBKDF2 or Argon2) | Adequate |
| Independent assurance | Audits and certifications | Bitwarden states it is **SOC 2 Type II and SOC 3** certified and holds **ISO 27001**. The SOC 3 report is published; the SOC 2 report is available on request and **not yet obtained** | F-03 |
| Security testing | Penetration tests and code audits | Annual third-party source code audits and penetration tests; annual network assessments; a public bug bounty | Adequate |
| Logging | Who viewed or changed shared items | **Event logs come only with the paid Teams plan**; the Free organization has none | F-01 |
| Organization policies | Enforcing two-step login and master password strength for members | Enterprise policies aren't available on the Free plan; each member's settings are their own responsibility | F-02 |
| Recovery | What happens if members lose access | Zero-knowledge means Bitwarden can't recover a vault. With two members, one can still reach the shared items if the other loses access; if both do, the vault is lost | F-04 |
| Contract | Breach notification and data terms | Free-plan customers accept Bitwarden's standard terms; no negotiated 72-hour clause as P-008 §4 requires | F-05 |
| Plan limits | Members and collections | Free organization: two users, up to two collections. This matches the design: only the Owner and the IT Technician hold shared credentials | Adequate |

---

## Summary

Bitwarden's own security is strong and well evidenced: zero-knowledge encryption, recognised certifications and regular independent testing. The gaps come from the **Free plan** (no event log, no enforced policies) and from the **zero-knowledge design itself** (no vendor recovery), and each has a straightforward compensating control.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

## Sources (checked 2026-11-02)
  - [Bitwarden: Compliance](https://bitwarden.com/compliance/) (SOC 2 Type II, SOC 3, ISO 27001, audits, encryption)
  - [Bitwarden: Organizations overview](https://bitwarden.com/help/about-organizations/) (Free organization: two users, two collections; event logs on Teams)
  - [Bitwarden: Business pricing](https://bitwarden.com/pricing/business/)

---

*This document is a simulation for educational and portfolio purposes only.*
