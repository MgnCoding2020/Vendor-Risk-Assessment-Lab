# Vendor Intake — Bitwarden (Password Manager)

Captured 2026-11-02, **before onboarding**. Bitwarden is set up with change CR-003 (IT brought in-house) on 2026-11-15 to hold the shared admin credentials Vertex IT Support used to know.

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Bitwarden, Inc. |
| **Vendor ID** | V-009 |
| **Service** | Password manager: a **Free organization** plan with two members (Owner and IT Technician) and two shared collections ([PR-009](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/05-procedures/PR-009-credential-vault.md)) |
| **Internal business owner** | Olivia Carter (Owner) |
| **Requested by** | IT Technician, via CR-003 |
| **Intake date** | 2026-11-02 |

---

## Data Handled by the Vendor

| Data | Classification |
|---|---|
| Shared admin credentials: firewall, access points, router, Wi-Fi passphrases, vendor and device portals | Restricted |
| Member account details (two email addresses) | Internal |

The vault is **end-to-end encrypted**: Bitwarden stores it but can't read it. **No cardholder data** is ever stored in it (PR-009 §3).

---

## System Access

Bitwarden has no access to company systems. It holds the credentials **to** them, encrypted with keys only the members hold.

---

## Business Criticality

Moderate. Losing access would slow admin work and incident response, but nothing stops trading, and an encrypted export is kept offline every quarter ([PR-012](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/05-procedures/PR-012-backup-and-recovery.md)).

---

## Initial Risk Indicators

  - Holds the keys to every network device and vendor portal: a compromised member account exposes them all
  - Free plan: no event log, no enforced organization policies
  - Zero-knowledge design: if both members lose their master passwords, the vault can't be recovered

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only.*
