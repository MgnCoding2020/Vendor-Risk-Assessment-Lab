# Vendor Risk Assessment Report
## Toast, Inc. (Toast POS and xtraCHEF)

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Toast, Inc. |
| **Vendor ID** | V-001 |
| **Service** | Point of sale, card-present payment processing, inventory (xtraCHEF) |
| **Assessment Date** | 2026-10-30 (vendor in use since 2026-02-01) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | High (18 of 18) |
| **Residual Risk** | Moderate, once F-01 to F-04 close |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

Toast processes every card payment the company takes and is its highest-risk vendor. It had been in use for eight months without an assessment. Toast publicly states that it is a PCI DSS Level 1 service provider, but the company holds none of the evidence PCI DSS Requirement 12.8 expects it to keep about a payment service provider, and it has never completed its own PCI self-assessment. Toast **continues in service** (there is no alternative way to take card payments and no sign that Toast itself is insecure), on condition that the evidence gaps close on the dates below.

## 2. Scope & Methodology

The program's vendor risk process: [intake](../intake/vendor-intake.md), six-factor [inherent risk scoring](../risk-scoring/inherent-risk-score.md), a [due diligence review](../due-diligence/security-review.md) of Toast's public information (checked 2026-10-30) against PCI DSS v4.0.1 Requirement 12.8, [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md). Toast's customer-only reports were not reviewed; obtaining them is F-01 and F-04.

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | No AOC or PCI responsibility guide on file (12.8.4, 12.8.5) | High |
| F-02 | Company's own SAQ not completed; SAQ type unknown | High |
| F-03 | No written 12.8.2 acknowledgment on file | Medium |
| F-04 | SOC 2 Type II not obtained | Medium |

Already tracked elsewhere: POS terminal inspection (POAM-004); unnecessary POS admin role (IAM:F-002, POAM-014).

## 4. Conditions

1. **By 2026-11-30:** AOC and responsibility guide obtained, responsibility matrix built (F-01); service agreement located (F-03); SOC 2 Type II reviewed (F-04).
2. **By 2026-12-31:** SAQ type confirmed and SAQ completed and signed by the Owner (F-02).
3. **Every 12 months:** Toast's PCI DSS compliance status re-checked (12.8.4).

## 5. Program Linkage

- **Vendor inventory:** V-001 assessment status → Complete, last assessed 2026-10-30
- **POA&M:** POAM-020 under SA-9; the assessment itself addresses the long-standing gap in POAM-006
- **Policy:** Payment Card Data Protection Policy (P-004) §6 and §8
- **Re-assessment:** annually, or on any change to the payment service or a Toast security incident

---

## 6. Status Updates

| Date | Update |
|---|---|
| 2026-10-30 | **Exit approved.** The Owner approved replacing Toast under [CR-005](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-005-toast-pos-replacement.md), blocked until the company's new register passes acceptance testing. The risk decision above stands until cutover: Toast still processes the company's card payments, so conditions 1 to 3 and findings F-01 to F-04 stay due on their dates. At cutover, Toast is offboarded (account closed, terminal returned or wiped, written confirmation), recorded here as exit evidence. |

---

*This report is a simulation for educational and portfolio purposes only.*
