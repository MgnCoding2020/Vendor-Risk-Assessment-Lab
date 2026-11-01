# Vendor Risk Assessment Report
## Espresso Machine Service Company

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Espresso machine service company (unnamed, fictional) |
| **Vendor ID** | V-011 |
| **Service** | Espresso machine service contract, telemetry portal and remote diagnostics |
| **Assessment Date** | 2026-11-01 (in use since 2026-01-15) |
| **Assessor** | Olivia Carter (Owner), with Daniel Lopez (Store Manager) |
| **Inherent Risk** | Moderate (12 of 18) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

The espresso machine's service company can reach into the store: its technicians control the machine remotely through the vendor's cloud, and the machine shares a network with the POS terminal. The vendor holds almost no sensitive data and its platform is reasonably designed, but the shop hasn't switched on the protections it offers, doesn't own its portal account, and has no breach-notification timeline. **The relationship continues**, on condition that remote sessions need the shop's approval and are recorded, the portal moves to a company account with MFA, and the machine moves to the isolated Devices segment.

## 2. Scope & Methodology

The program's vendor risk process: [intake](../intake/vendor-intake.md), [inherent risk scoring](../risk-scoring/inherent-risk-score.md) with the six-factor worksheet, a [due diligence review](../due-diligence/security-review.md) of the vendor's questionnaire answers and contract (simulated), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md).

## 3. Vendor Overview

A regional equipment dealer that supplies and services the shop's connected espresso machine (ESP-01) under a service contract renewed each January.

## 4. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | Remote sessions need no approval and aren't seen by the shop; machine shares the POS network | High |
| F-02 | Vendor-wide local service PIN | Medium |
| F-03 | No independent security assurance | Medium |
| F-04 | No breach-notification timeline in the contract | Medium |
| F-05 | Portal account in a personal email, MFA off | Medium |

## 5. Conditions

1. **By 2026-11-30:** customer approval required for remote sessions, and sessions recorded (F-01); portal on a company account with MFA (F-05); risk acceptance for F-03 recorded.
2. **By 2026-12-15:** unique service PIN (F-02).
3. **At renewal, 2027-01-15:** 72-hour breach-notification clause (F-04).
4. **With POAM-015:** the machine moves to the Devices segment (F-01).

## 6. Program Linkage

- **Vendor inventory:** V-011 assessment status → Complete, last assessed 2026-11-01, inherent tier Moderate
- **POA&M:** POAM-026 (MA-4, SC-7)
- **Procedures:** Connected Devices Procedure (PR-011 §4 remote access), Equipment Lifecycle (PR-010 §4 technician visits)
- **Incident response:** breach-notification gap recorded in IRP-006 §4
- **Re-assessment:** annually, at contract renewal

---

*This report is a simulation for educational and portfolio purposes only. The vendor is fictional.*
