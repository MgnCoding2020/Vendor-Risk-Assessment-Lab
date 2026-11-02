# Vendor Risk Assessment Report
## Temperature Monitoring Service

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Temperature monitoring service (unnamed, fictional) |
| **Vendor ID** | V-012 |
| **Service** | Fridge temperature sensors, food-safety log and alerts |
| **Assessment Date** | 2026-11-02 (in use since 2026-03-01) |
| **Assessor** | Daniel Lopez (Store Manager), approved by Olivia Carter (Owner) |
| **Inherent Risk** | Moderate (9 of 18) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

A low-exposure vendor: the sensors only send temperatures out, and the vendor holds no sensitive data. Its Moderate score comes from the food-safety record it keeps. The real risks are continuity: the account and the alerts depend on one person's personal email and phone, and the log has never been exported. The relationship continues once the account is company-owned with MFA and alerts reach more than one person (by 2026-11-30).

## 2. Scope & Methodology

[Intake](../intake/vendor-intake.md), [six-factor score](../risk-scoring/inherent-risk-score.md), [due diligence](../due-diligence/security-review.md) (simulated), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md), kept proportionate to the low data sensitivity.

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | Account in a personal email, MFA off | Medium |
| F-02 | Alerts to one personal phone only | Medium |
| F-03 | Food-safety log never exported | Low |
| F-04 | No breach-notification timeline | Low |

## 4. Program Linkage

- **Vendor inventory:** V-012 assessment Complete, 2026-11-02, inherent tier Moderate
- **POA&M:** POAM-026 (connected devices)
- **Procedures:** Connected Devices (PR-011 §6), Backup and Recovery (PR-012), Records Retention (P-010)
- **Re-assessment:** every two years (Moderate, P-008)

---

*This report is a simulation for educational and portfolio purposes only. The vendor is fictional.*
