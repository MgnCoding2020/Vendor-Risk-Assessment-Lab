# Vendor Risk Assessment Report
## Microsoft (Microsoft 365)

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Microsoft Corporation |
| **Vendor ID** | V-003 |
| **Service** | Microsoft 365 (identity, email, files, intranet, bookkeeping workbook) |
| **Assessment Date** | 2026-10-30 (before onboarding) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | High (16 of 18) |
| **Residual Risk** | Moderate |
| **Risk Decision** | **Approve with Conditions** |

---

## 1. Executive Summary

Microsoft 365 is approved for onboarding under change CR-001, **on condition that MFA is enforced on every Burn and Churn account before go-live**. Microsoft's own security is well evidenced in public: independent SOC 2 Type 2 and ISO/IEC 27001 audits, a 72-hour breach-notification commitment, and a published subprocessor list. The material risks are on the company's side of the shared-responsibility line, where the licence the company actually holds (Entra ID Free) limits identity protection, privileged-access management and log retention.

## 2. Scope & Methodology

The assessment followed the program's vendor risk process: [intake](../intake/vendor-intake.md), [inherent risk scoring](../risk-scoring/inherent-risk-score.md) with the six-factor worksheet, a [due diligence review](../due-diligence/security-review.md) of Microsoft's public compliance documentation (checked 2026-10-30), [findings](../findings/vendor-risk-findings.md), and a [remediation plan](../remediation/remediation-tracker.md). Microsoft's confidential audit reports were not reviewed; obtaining them is finding F-02.

## 3. Vendor Overview

Microsoft provides the company's identity provider (Entra ID) and productivity suite. It holds no cardholder data; card payments stay in Toast POS.

## 4. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | No Conditional Access on Entra ID Free; MFA only per user | High |
| F-02 | SOC 2 Type 2 and ISO/IEC 27001 reports not yet obtained or reviewed | Medium |
| F-03 | Standing admin roles (PIM requires Entra ID P2) | Medium |
| F-04 | 7-day sign-in log retention on Entra ID Free | Low |
| F-05 | No subscription to subprocessor change notices | Low |

## 5. Conditions of Approval

1. **Before go-live:** per-user MFA enforced on every Burn and Churn account (F-01); standing-admin risk acceptance recorded (F-03); within-7-days log export added to the log review procedure (F-04).
2. **Within 30 days of onboarding:** SOC 2 Type 2 and ISO/IEC 27001 reports obtained and reviewed (F-02); subprocessor notices subscribed (F-05).

## 6. Program Linkage

- **Vendor inventory:** V-003 assessment status → Complete, last assessed 2026-10-30
- **POA&M:** POAM-018 under SA-9
- **Change:** CR-001 (Microsoft 365 migration)
- **Re-assessment:** annually, or when the licence changes (for example, if a Business Premium trial adds Conditional Access, F-01 can close)

---

*This report is a simulation for educational and portfolio purposes only.*
