# Vendor Risk Assessment Lab

> Part of the Burn and Churn Coffee security program: [program hub](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop). Company, people, systems and vendors are defined there.

This repository demonstrates the **execution** of a third-party vendor risk assessment, end to end, as part of a broader Governance, Risk, and Compliance (GRC) program.

It is the operational companion to the **[GRC Security Program Simulation – Burn and Churn Coffee](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** repository. That repository defines the governance program and the reusable vendor risk management *templates*; this lab puts those templates to work by assessing a real-feeling vendor and feeding the results back into the program.

---

## Assessments

Each vendor assessment has its own folder under `assessments/`, following the same workflow.

| Vendor | Service | Date | Inherent | Residual | Decision | Findings | Program linkage |
|---|---|---|---|---|---|---|---|
| [Toast, Inc. (V-001)](assessments/V-001-toast/final-assessment/vendor-risk-assessment-report.md) | POS and card payments; xtraCHEF | 2026-10-30 (in use since 2026-02-01) | High (18/18) | Moderate once conditions close | Continue with Conditions | 4 open (`VRA-V001:F-01`–`F-04`) | POAM-020 (SA-9); PCI DSS 12.8 |
| [Northwind Payroll Services (V-002)](assessments/V-002-northwind/final-assessment/vendor-risk-assessment-report.md) | Cloud payroll and HR | 2026-06-23 | High | Moderate | Approve with Conditions; **onboarding pending** (pre-go-live conditions open at the 2026-10-30 check) | 4 open, 2 overdue (`VRA-V002:F-01`–`F-04`) | POAM-013 (SA-9) |
| [Microsoft, Microsoft 365 (V-003)](assessments/V-003-microsoft/final-assessment/vendor-risk-assessment-report.md) | Identity, email, files, intranet | 2026-10-30 (before onboarding) | High (16/18) | Moderate | Approve with Conditions | 5 open (`VRA-V003:F-01`–`F-05`) | POAM-018 (SA-9); change CR-001 |

**Planned:** offboarding record for Vertex IT Support (V-004), under change CR-003; time-limited guest access for Northwind's payroll contact, under change CR-004, once F-02 is confirmed.

---

## Assessment Workflow

Each assessment folder documents every stage:

1. **Intake** (`intake/`): service, data and access captured
2. **Inherent risk score** (`risk-scoring/`): risk rated before reviewing controls
3. **Security due diligence review** (`due-diligence/`): vendor security posture assessed
4. **Findings** (`findings/`): gaps documented
5. **Remediation tracker** (`remediation/`): per-finding status to closure
6. **Final report** (`final-assessment/`): consolidated decision

### Toast, Inc. (V-001)

The company's payment service provider and highest-risk vendor, assessed eight months after it went into use. Measured against PCI DSS Requirement 12.8: Toast states it is a PCI DSS Level 1 service provider, but the company held none of the evidence it is required to keep. Start at the [intake](assessments/V-001-toast/intake/vendor-intake.md).

### Northwind Payroll Services (V-002)

Burn and Churn Coffee engaged a third-party **cloud payroll and HR vendor** to process employee management and payroll. The vendor handles sensitive employee data (PII, payroll and tax records, direct-deposit banking details), so it was assessed before approval. Start at the [intake](assessments/V-002-northwind/intake/vendor-intake.md); supporting context is in the [vendor profile](assessments/V-002-northwind/scenario/vendor-profile.md).

### Microsoft, Microsoft 365 (V-003)

Assessed **before onboarding**, as part of the planned migration from Google Workspace. Based on Microsoft's public compliance documentation and its shared-responsibility model, which places accounts, identities and data on the customer's side. Most findings are therefore about what the company's own licence allows. Start at the [intake](assessments/V-003-microsoft/intake/vendor-intake.md).

The [glossary](docs/glossary.md) covers terms used across assessments.

*Files moved on 2026-10-30 into per-vendor folders; the old paths hold redirect notes.*

---

## Relationship to the GRC Program

This lab and the GRC program are designed to work together:

- The **[GRC program](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** holds the vendor inventory, the blank assessment templates (intake questionnaire, inherent risk scoring worksheet, due diligence checklist, assessment template), and the program-level POA&M and risk register.
- This **lab** executes full assessments using those templates.
- The findings flow **back** into the program: each assessment is recorded in the program's vendor inventory and rolled up in the program POA&M under control **SA-9 (External System Services)**: Northwind as **POAM-013**, Microsoft as **POAM-018**.

This closes the loop between governance (the program) and operations (the assessment).

---

## Key Concepts Demonstrated

- Risk-based, third-party vendor evaluation
- Inherent vs. residual risk determination
- Security due diligence and findings documentation
- Remediation tracking and governance rollup
- Scoping judgment (why PCI DSS Req. 12.8 applies to Toast but **not** to a payroll vendor)
- Shared responsibility: separating what the vendor secures from what the customer must configure

---

## Purpose

This repository is a **portfolio artifact** demonstrating how governance processes translate into a documented, defensible vendor risk assessment. It is a simulation for educational and portfolio purposes only.
