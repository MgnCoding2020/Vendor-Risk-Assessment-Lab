# Vendor Risk Assessment Report
## Internet Service Provider

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Internet service provider (unnamed, fictional) |
| **Vendor ID** | V-008 |
| **Service** | Small-business broadband with a provider-managed router |
| **Assessment Date** | 2026-11-02 (in use since the shop opened) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | Moderate (10 of 18) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

The provider can't read the shop's important traffic, since payments and cloud services are encrypted end to end, so confidentiality risk is low. Its risks are **control** (it manages the router at the edge of the store network and holds the password) and **availability** (no restoration commitment). The relationship continues with the router treated as outside the shop's network, its Wi-Fi off, and an Owner decision on cellular failover by the end of the year.

## 2. Scope & Methodology

[Intake](../intake/vendor-intake.md), [six-factor score](../risk-scoring/inherent-risk-score.md), [due diligence](../due-diligence/security-review.md) of the contract, terms and router settings (simulated), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md).

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | Provider controls the router and its password | Medium |
| F-02 | Router Wi-Fi still broadcasting | Medium |
| F-03 | No outage restoration commitment | Medium |
| F-04 | No incident-notification commitment | Low |

## 4. Program Linkage

- **Vendor inventory:** V-008 assessment Complete, 2026-11-02, inherent tier Moderate
- **POA&M:** POAM-015 (network boundary), POAM-005 (contingency)
- **Procedures:** Network Security (P-005), Device Baselines (PR-015 §7), Contingency (PR-005)
- **Re-assessment:** every two years (Moderate, P-008), or at contract renewal

---

*This report is a simulation for educational and portfolio purposes only. The vendor is fictional.*
