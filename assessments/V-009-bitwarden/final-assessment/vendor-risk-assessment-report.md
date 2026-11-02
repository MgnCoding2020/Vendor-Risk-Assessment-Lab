# Vendor Risk Assessment Report
## Bitwarden (Password Manager)

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Bitwarden, Inc. |
| **Vendor ID** | V-009 |
| **Service** | Password manager, Free organization plan (two members, two collections) |
| **Assessment Date** | 2026-11-02 (before onboarding) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | Moderate (13 of 18) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Approve with Conditions** |

---

## 1. Executive Summary

Bitwarden is approved to hold the company's shared admin credentials, from the CR-003 handover on 2026-11-15. Its own security is strongly evidenced: zero-knowledge, end-to-end encryption, SOC 2 Type II, SOC 3 and ISO 27001, and annual independent testing. The gaps come from the Free plan (no event log, no enforced member policies) and the zero-knowledge design (no vendor recovery), and are handled by setup conditions and an existing exception (EXC-006).

## 2. Scope & Methodology

[Intake](../intake/vendor-intake.md), [six-factor inherent risk score](../risk-scoring/inherent-risk-score.md), [due diligence](../due-diligence/security-review.md) of Bitwarden's public documentation (checked 2026-11-02), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md). The SOC 2 report itself is requested after onboarding (F-03).

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | No event log on the Free plan | Low (accepted) |
| F-02 | Two-step login and master password strength not enforceable | Medium |
| F-03 | SOC 2 Type II not yet reviewed | Low |
| F-04 | Vault unrecoverable if both members lose access | Medium |
| F-05 | No negotiated breach-notification clause | Low |

## 4. Conditions

1. **At setup (2026-11-15):** two-step login and strong master passwords for both members (F-02); recovery codes sealed with the break-glass credentials (F-04); exception EXC-006 in force (F-01).
2. **By 2026-12-15:** SOC 2 Type II reviewed (F-03); Bitwarden's incident terms recorded (F-05).

## 5. Program Linkage

- **Vendor inventory:** V-009 assessment Complete, 2026-11-02, inherent tier Moderate; status Planned until CR-003
- **POA&M:** POAM-021 (IA-5); exception EXC-006
- **Procedure:** Shared Credential Management (PR-009), including Michael's lab test with test entries only
- **Re-assessment:** every two years (Moderate, P-008), or if the plan changes

---

*This report is a simulation for educational and portfolio purposes only.*
