# Vendor Offboarding Record — Vertex IT Support (V-004)

| | |
|---|---|
| **Vendor** | Vertex IT Support (managed service provider; fictional) |
| **Vendor ID** | V-004 |
| **Service ending** | Outsourced IT administration: Google Workspace admin, store network admin, device support |
| **Reason** | IT brought in-house under [CR-003](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-003-it-support-in-house.md): Q1 access review findings assigned to Vertex went about seven months without remediation, and Vertex administered through a generic shared account, which P-001 §5.7 doesn't allow |
| **Handover date** | 2026-11-15 (scheduled, with CR-001) |
| **Business owner** | Olivia Carter (Owner) |
| **Performed by** | Riley Morgan (IT Technician), witnessed by the Owner |
| **Status** | **Planned:** sections 3 to 6 are filled in on the handover day |

---

## 1. Why an Offboarding Record

Ending a vendor relationship is as much a third-party risk event as starting one (NIST SP 800-53 SA-9; PS-7 for external personnel). A vendor that leaves with working credentials, undocumented knowledge or company data is a risk that outlives the contract. This record proves, item by item, that Vertex left with none of them.

---

## 2. What Vertex Has Today

From the Q1 2026 access review ([IAM access matrix](https://github.com/MgnCoding2020/IAM-Access-Review-Lab/blob/main/evidence/user-access-matrix.csv)) and the program's records:

| Access or asset | Detail | Risk |
|---|---|---|
| **Generic "Vertex IT Support" account, Google Workspace admin** | Shared by Vertex staff; MFA on | Unattributable admin actions (missed in Q1: AL-13) |
| **Generic "Vertex IT Support" account, network admin** | Firewall, router and access point administration | Network control after the contract ends |
| **Shared passwords Vertex knows** | Router, firewall, access points, Wi-Fi passphrases, Google admin | Reuse after exit |
| **Documentation and knowledge** | Network layout, firewall rules, device history, open tickets | Lost knowledge; no maintenance records exist (POAM-023, POAM-024) |
| **Company data** | Any exports, notes or tickets held in Vertex's own systems | Data retained outside the company |
| **Contract** | Managed services agreement | Notice period, final invoice, return-of-data clause |

---

## 3. Knowledge Transfer (handover checklist)

The checklist in the program's [IT Administration and Coverage Procedure, PR-008 §7](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/05-procedures/PR-008-it-administration.md). Tick on the day; the completed list is signed below.

- [ ] Network diagram and every network device with its admin interface
- [ ] Current firewall rules, with the reason for each
- [ ] Every account and credential Vertex holds or knows, listed
- [ ] Open tickets and known issues (including IAM:F-001, F-003 and F-004, assigned to Vertex)
- [ ] Vendor and warranty contacts, purchase dates, firmware versions and maintenance history (entered in the equipment register and maintenance log)
- [ ] Google Workspace admin tasks still pending before CR-001 completes
- [ ] Firewall and access point configurations exported: the program's first backup ([PR-012](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/05-procedures/PR-012-backup-and-recovery.md))

---

## 4. Access Removal

| Step | Done | Date and time | By | Evidence |
|---|---|---|---|---|
| Every credential Vertex knew rotated, new ones stored in the password manager (PR-009) | ☐ | | | CR-003 log entry |
| Generic Google Workspace admin account disabled (then deleted with Google Workspace at the end of CR-001) | ☐ | | | Admin console screenshot (simulated system) |
| Generic network admin account removed from the firewall, router and access points | ☐ | | | Device user list after removal |
| No Vertex account in the new Microsoft 365 tenant (none is ever created) | ☐ | | | Entra user list from build day |
| Any Vertex remote-access tool removed from company devices | ☐ | | | Device check |
| NorthPeak Systems network admin account disabled at the same time (IAM:F-003) | ☐ | | | Device user list |

---

## 5. Data and Contract

| Item | Done | Date | Evidence |
|---|---|---|---|
| Written confirmation that Vertex has returned or deleted all company data, notes and exports | ☐ | | Signed letter or email from Vertex |
| Contract termination notice given and acknowledged | ☐ | | Notice and reply |
| Final invoice settled; any equipment Vertex supplied returned or bought out | ☐ | | Invoice |
| Vendor inventory: V-004 → Offboarded | ☐ | | Program `vendors.csv` |

---

## 6. Sign-off

| | Name | Signature | Date |
|---|---|---|---|
| Handover received (IT Technician) | Riley Morgan | | |
| Offboarding approved (Owner) | Olivia Carter | | |

---

## 7. Follow-up

The **Q4 2026 access review** confirms that no Vertex or NorthPeak account remains anywhere, and records the generic-account finding (AL-13) with its closure evidence. That review is also the post-implementation review for CR-003.

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
