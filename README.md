# Vendor Risk Assessment Lab

This repository demonstrates the **execution** of a third-party vendor risk assessment, end to end, as part of a broader Governance, Risk, and Compliance (GRC) program.

It is the operational companion to the **[GRC Security Program Simulation – Burn and Churn Coffee](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** repository. That repository defines the governance program and the reusable vendor risk management *templates*; this lab puts those templates to work by assessing a real-feeling vendor and feeding the results back into the program.

---

## Assessment Scenario

Burn and Churn Coffee engaged a third-party **cloud payroll and HR vendor**, Northwind Payroll Services, to process employee management and payroll. The vendor handles sensitive employee data — PII, payroll and tax records, and direct-deposit banking details — so it was subject to a formal vendor risk assessment before approval.

---

## Assessment Outcome

| | |
|---|---|
| **Vendor** | Northwind Payroll Services (V-002) |
| **Inherent Risk** | High |
| **Residual Risk** | Moderate |
| **Decision** | Approve with Conditions |
| **Open Findings** | 4 (tracked to closure) |
| **Program Linkage** | POAM-013 under control SA-9 |

---

## Assessment Workflow

Each stage of the assessment is documented in this repository:

1. [Vendor Intake](intake/vendor-intake.md) — service, data, and access captured
2. [Inherent Risk Score](risk-scoring/inherent-risk-score.md) — risk rated before reviewing controls (High)
3. [Security Due Diligence Review](due-diligence/security-review.md) — vendor security posture assessed
4. [Vendor Risk Findings](findings/vendor-risk-findings.md) — gaps documented (F-01–F-04)
5. [Remediation Tracker](remediation/remediation-tracker.md) — per-finding status to closure
6. [Final Vendor Risk Assessment Report](final-assessment/vendor-risk-assessment-report.md) — consolidated decision

Supporting context is in [scenario/vendor-profile.md](scenario/vendor-profile.md) and the [glossary](docs/glossary.md).

---

## Relationship to the GRC Program

This lab and the GRC program are designed to work together:

- The **[GRC program](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** holds the vendor inventory, the blank assessment templates (intake questionnaire, inherent risk scoring worksheet, due diligence checklist, assessment template), and the program-level POA&M and risk register.
- This **lab** executes one full assessment using those templates.
- The findings flow **back** into the program: the Northwind assessment is recorded in the program's vendor inventory (V-002, status Complete) and rolled up in the program POA&M as **POAM-013** under control **SA-9 (External System Services)**.

This closes the loop between governance (the program) and operations (the assessment).

---

## Key Concepts Demonstrated

- Risk-based, third-party vendor evaluation
- Inherent vs. residual risk determination
- Security due diligence and findings documentation
- Remediation tracking and governance rollup
- Scoping judgment (e.g., why PCI DSS Req. 12.8 does **not** apply to a payroll vendor)

---

## Purpose

This repository is a **portfolio artifact** demonstrating how governance processes translate into a documented, defensible vendor risk assessment. It is a simulation for educational and portfolio purposes only.
