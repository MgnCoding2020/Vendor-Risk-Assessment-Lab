# Vendor Intake — Microsoft (Microsoft 365)

Captured before onboarding, as part of change CR-001 (migration from Google Workspace to Microsoft 365, scheduled 2026-11-15).

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Microsoft Corporation |
| **Vendor ID** | V-003 |
| **Service** | Microsoft 365: Entra ID (identity), Exchange Online (email), SharePoint Online and Teams (files, intranet, chat), Excel for the web (bookkeeping workbook); Intune and Defender for Business if licensed |
| **Internal business owner** | Olivia Carter (Owner) |
| **Requested by** | IT administrator, via CR-001 |
| **Intake date** | 2026-10-30 |

---

## Service Description

Microsoft 365 replaces Google Workspace as the company's productivity suite and becomes its **identity provider**: every staff account, group and admin role will live in Entra ID. It also hosts the intranet (SOPs, access requests, training tracker, timesheets) and the bookkeeping workbook that replaces QuickBooks Online.

---

## Data Handled by the Vendor

| Data | Classification |
|---|---|
| Staff accounts, group memberships, sign-in and audit logs | Restricted |
| Business email | Confidential |
| Financial records (bookkeeping workbook) | Confidential |
| Payroll export (timesheets sent to Northwind) | Restricted |
| SOPs, policies, training records | Internal |

**No cardholder data.** Card payments stay in Toast POS.

---

## System Access

Microsoft operates the platform that holds the company's identities and data. Burn and Churn administers its own tenant (users, groups, roles, MFA). Microsoft staff do not routinely access customer data; Microsoft documents its own access-management process on its trust pages.

---

## Business Criticality

High for administration (email, documents, sign-in to every Microsoft 365 service). **Store sales are unaffected by an outage**, because Toast POS is independent of Microsoft 365.

---

## Regulatory & Compliance Considerations

- Employee personal data (contact details, sign-in records, payroll export)
- No PCI DSS scope (no cardholder data), so PCI DSS 12.8 applies only in the general sense of managing a service provider
- Microsoft publishes independent audit reports (SOC 2 Type 2, ISO/IEC 27001) on its Service Trust Portal

---

## Initial Risk Indicators

- Becomes the single identity provider: a compromise of an admin account exposes everything
- The tenant runs on Entra ID Free today, which has no Conditional Access
- Subprocessors are used (Microsoft publishes a subprocessor list)

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only.*
