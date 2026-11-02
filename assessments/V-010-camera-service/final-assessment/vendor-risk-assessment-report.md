# Vendor Risk Assessment Report
## Cloud Camera Service

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Cloud camera service (unnamed, fictional) |
| **Vendor ID** | V-010 |
| **Service** | Two indoor cameras with cloud recording |
| **Assessment Date** | 2026-11-02 (in use since 2026-01-20) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | Moderate (12 of 18) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

The camera vendor's platform is sound: an independent SOC 2 Type II audit, a 72-hour breach-notification commitment, encryption and signed firmware. The risks come from how the cameras were set up for convenience: a shared login without MFA, 60-day retention against the program's 30, standing support access to footage, and a local video stream protected only by a default password. The relationship continues once those four settings are changed by 2026-11-30.

## 2. Scope & Methodology

[Intake](../intake/vendor-intake.md), [six-factor score](../risk-scoring/inherent-risk-score.md), [due diligence](../due-diligence/security-review.md) from the vendor's questionnaire, terms and camera settings (simulated), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md).

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | Shared account, MFA off | Medium |
| F-02 | 60-day retention (rule is 30) | Low |
| F-03 | Support access to footage always allowed | Medium |
| F-04 | Local stream open with the default password | High |

## 4. Program Linkage

- **Vendor inventory:** V-010 assessment Complete, 2026-11-02, inherent tier Moderate
- **POA&M:** POAM-027 (cameras, PE-6), POAM-026 (connected devices)
- **Procedures:** Connected Devices (PR-011 §5 camera rules), Records Retention (P-010), Device Baselines (PR-015)
- **Incident response:** 72-hour notification recorded in IRP-006 §4
- **Re-assessment:** every two years (Moderate, P-008)

---

*This report is a simulation for educational and portfolio purposes only. The vendor is fictional.*
