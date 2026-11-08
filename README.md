# Vendor Risk Assessment Lab

> Part of the Burn and Churn Coffee security program: [program hub](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop). Company, people, systems and vendors are defined there.

This repository demonstrates the **execution** of third-party vendor risk management, end to end, as part of a broader Governance, Risk, and Compliance (GRC) program: nine vendor assessments and one vendor exit, each documented from intake to decision.

It is the operational companion to the **[GRC Security Program Simulation – Burn and Churn Coffee](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** repository. That repository defines the governance program and the reusable vendor risk management *templates*; this lab puts those templates to work, following the program's [Third-Party Risk Management Policy (P-008)](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md), and feeds the results back into the program. Real vendors (Toast, Microsoft, Bitwarden) are assessed from their public compliance documents; fictional vendors from simulated questionnaire answers, labelled as such.

---

## Assessments

Each vendor assessment has its own folder under `assessments/`, following the same workflow.

| Vendor | Service | Date | Inherent | Residual | Decision | Findings | Program linkage |
|---|---|---|---|---|---|---|---|
| [Toast, Inc. (V-001)](assessments/V-001-toast/final-assessment/vendor-risk-assessment-report.md) | POS and card payments; xtraCHEF | 2026-10-30 (in use since 2026-02-01) | High (18/18) | Moderate once conditions close | Continue with Conditions | 4 open (`VRA-V001:F-01`–`F-04`) | POAM-020 (SA-9); PCI DSS 12.8 |
| [Northwind Payroll Services (V-002)](assessments/V-002-northwind/final-assessment/vendor-risk-assessment-report.md) | Cloud payroll and HR | 2026-06-23 | High | Moderate | Approve with Conditions; **onboarding pending** (pre-go-live conditions open at the 2026-10-30 check) | 4 open, 2 overdue (`VRA-V002:F-01`–`F-04`) | POAM-013 (SA-9) |
| [Microsoft, Microsoft 365 (V-003)](assessments/V-003-microsoft/final-assessment/vendor-risk-assessment-report.md) | Identity, email, files, intranet | 2026-10-30 (before onboarding) | High (16/18) | Moderate | Approve with Conditions | 5 open (`VRA-V003:F-01`–`F-05`) | POAM-018 (SA-9); change CR-001 |
| [Espresso machine service company (V-011)](assessments/V-011-espresso-service/final-assessment/vendor-risk-assessment-report.md) | Espresso machine servicing, telemetry and **remote diagnostics** | 2026-11-01 (in use since 2026-01-15) | Moderate (12/18) | Low once conditions are met | Continue with Conditions | 5 open (`VRA-V011:F-01`–`F-05`) | POAM-026 (MA-4, SC-7); PR-011 |
| [Bitwarden, password manager (V-009)](assessments/V-009-bitwarden/final-assessment/vendor-risk-assessment-report.md) | Shared admin credentials (Free organization) | 2026-11-02 (before onboarding, CR-003) | Moderate (13/18) | Low once conditions are met | Approve with Conditions | 5 open (`VRA-V009:F-01`–`F-05`; F-01 accepted as EXC-006) | POAM-021 (IA-5); PR-009 |
| [Cloud camera service (V-010)](assessments/V-010-camera-service/final-assessment/vendor-risk-assessment-report.md) | Security cameras and cloud recording | 2026-11-02 (in use since 2026-01-20) | Moderate (12/18) | Low once conditions are met | Continue with Conditions | 4 open (`VRA-V010:F-01`–`F-04`) | POAM-027 (PE-6), POAM-026; PR-011 |
| [Temperature monitoring service (V-012)](assessments/V-012-temperature-monitoring/final-assessment/vendor-risk-assessment-report.md) | Fridge sensors, food-safety log and alerts | 2026-11-02 (in use since 2026-03-01) | Moderate (9/18) | Low once conditions are met | Continue with Conditions | 4 open (`VRA-V012:F-01`–`F-04`) | POAM-026; PR-011 |
| [Internet service provider (V-008)](assessments/V-008-internet-provider/final-assessment/vendor-risk-assessment-report.md) | Broadband and a provider-managed router | 2026-11-02 (in use since the shop opened) | Moderate (10/18) | Low once conditions are met | Continue with Conditions | 4 open (`VRA-V008:F-01`–`F-04`) | POAM-015, POAM-005 |
| [Cloudflare, website hosting and database (V-014)](assessments/V-014-cloudflare/final-assessment/vendor-risk-assessment-report.md) | Website, staff portal, API and database (Workers Free plan) | 2026-11-08 (in use since 2026-11-02; **assessed late**) | Moderate (13/18; High once the register replaces Toast) | Low once conditions are met | Continue with Conditions | 5 open (`VRA-V014:F-01`–`F-05`; F-03 accepted) | POAM-036 (SA-9); CR-002 |

**Offboarding:** [Vertex IT Support (V-004)](offboarding/V-004-vertex-msp/offboarding-record.md), under change CR-003: record prepared, completed at the handover on 2026-11-15.

**Planned:** time-limited guest access for Northwind's payroll contact, under change CR-004, once F-02 is confirmed.

### Awaiting assessment

| Vendor | Why it's due | When | Tracked as |
|---|---|---|---|
| **Stripe (V-013)**, online and counter payments (test mode) | High inherent risk; card-payment provider for [CR-002](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-002-online-ordering-website.md) and CR-005 | Before the website's Phase 4 (Stripe Terminal) | Hub POAM-036, CR-002 exit criteria |

Vendors that don't need one: V-004 Vertex (offboarding record instead), V-005 NorthPeak (inactive), V-006 Intuit and V-007 Google (being offboarded under CR-001).

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

The company's payment service provider and highest-risk vendor, assessed eight months after it went into use. Measured against PCI DSS Requirement 12.8: Toast states it is a PCI DSS Level 1 service provider, but the company held none of the evidence it is required to keep. Start at the [intake](assessments/V-001-toast/intake/vendor-intake.md). **Update 2026-10-30:** the Owner approved replacing Toast ([CR-005](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-005-toast-pos-replacement.md)). **Update 2026-11-02:** because Toast is leaving, its conditions are deferred under program exception EXC-007 until it exits, lapsing on 2027-01-31 if the change slips.

### Northwind Payroll Services (V-002)

Burn and Churn Coffee engaged a third-party **cloud payroll and HR vendor** to process employee management and payroll. The vendor handles sensitive employee data (PII, payroll and tax records, direct-deposit banking details), so it was assessed before approval. Start at the [intake](assessments/V-002-northwind/intake/vendor-intake.md); supporting context is in the [vendor profile](assessments/V-002-northwind/scenario/vendor-profile.md).

### Microsoft, Microsoft 365 (V-003)

Assessed **before onboarding**, as part of the planned migration from Google Workspace. Based on Microsoft's public compliance documentation and its shared-responsibility model, which places accounts, identities and data on the customer's side. Most findings are therefore about what the company's own licence allows. Start at the [intake](assessments/V-003-microsoft/intake/vendor-intake.md).

### Internet service provider (V-008)

Scored Moderate, not Low: the provider manages the router at the edge of the store network, and everything depends on the connection. The answer is to treat the router as outside the network and plan for outages. Start at the [report](assessments/V-008-internet-provider/final-assessment/vendor-risk-assessment-report.md).

### Bitwarden (V-009)

The password manager, assessed **before onboarding**. Strong, publicly evidenced security (zero-knowledge encryption, SOC 2 Type II, ISO 27001); the gaps come from the free plan and from zero-knowledge itself (no vendor recovery). Start at the [report](assessments/V-009-bitwarden/final-assessment/vendor-risk-assessment-report.md).

### Cloudflare (V-014)

Hosting for the company's website and its database, assessed **late**: in use from 2026-11-02 and holding staff data from 2026-11-07 before anyone assessed it, which the program's own alignment pass caught (hub AL-30). Cloudflare's security is well evidenced (SOC 2 Type II naming Workers and D1, ISO 27001); the conditions come from the Free plan, self-serve terms and a rate-limiting feature that doesn't work on this account, which the website compensated for in its own design. Start at the [report](assessments/V-014-cloudflare/final-assessment/vendor-risk-assessment-report.md).

### Connected-device vendors (V-010, V-011, V-012)

Three vendors found already in use, so each decision is continue, conditions or exit. The **espresso machine service company** can control its machine remotely on the same network as the POS; the **camera service** left a local video stream open with a default password; the **temperature service** keeps a food-safety record tied to one person's phone. Start at the [V-011 report](assessments/V-011-espresso-service/final-assessment/vendor-risk-assessment-report.md).

### Offboarding: Vertex IT Support (V-004)

The model for a vendor exit: what the vendor holds, knowledge transfer, every account removed, credentials rotated, data returned or deleted with confirmation, sign-off. Prepared for the 2026-11-15 handover under change CR-003. See the [offboarding record](offboarding/V-004-vertex-msp/offboarding-record.md).

The [glossary](docs/glossary.md) covers terms used across assessments.

*Files moved on 2026-10-30 into per-vendor folders; the old paths hold redirect notes.*

---

## Relationship to the GRC Program

This lab and the GRC program are designed to work together:

- The **[GRC program](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop)** holds the vendor inventory, the blank assessment templates (intake questionnaire, inherent risk scoring worksheet, due diligence checklist, assessment template), and the program-level POA&M and risk register.
- This **lab** executes full assessments using those templates.
- The findings flow **back** into the program: each assessment is recorded in the program's vendor inventory and rolled up in the program POA&M: Toast **POAM-020**, Northwind **POAM-013**, Microsoft **POAM-018** (all SA-9); Bitwarden **POAM-021** (IA-5); the connected-device vendors **POAM-026** and **POAM-027**; the internet provider **POAM-015** and **POAM-005**. Accepted risks go to the program's [exception register](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/risk-exceptions.md).

This closes the loop between governance (the program) and operations (the assessment).

**Incident response:** the program's [vendor breach playbook (IRP-006)](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/06-incident-playbooks/IRP-006-vendor-breach.md) lists each vendor's breach-notification commitment, taken from these assessments. Microsoft and the camera service commit to 72 hours. Gaps found here: no Toast agreement on file (`VRA-V001:F-03`), and no notification timeline from Northwind (`VRA-V002:F-03`), the espresso service (`VRA-V011:F-04`), the temperature service (`VRA-V012:F-04`) or the internet provider (`VRA-V008:F-04`); Bitwarden is on standard terms (`VRA-V009:F-05`). After a vendor breach, IRP-006 sends the vendor back here for reassessment.

---

## Key Concepts Demonstrated

- Risk-based, third-party vendor evaluation
- Inherent vs. residual risk determination
- Security due diligence and findings documentation
- Remediation tracking and governance rollup
- Scoping judgment (why PCI DSS Req. 12.8 applies to Toast but **not** to a payroll vendor)
- Shared responsibility: separating what the vendor secures from what the customer must configure
- Assessing vendors already in use (continue, conditions or exit), and assessing before onboarding
- Proportionate depth by risk tier, with honest scoring (the ISP scored Moderate, not the expected Low)
- Vendor exit: a documented offboarding record
- Risk acceptance tied to a planned exit (Toast's conditions deferred until it leaves, with a fallback date)

---

## Purpose

This repository is a **portfolio artifact** demonstrating how governance processes translate into a documented, defensible vendor risk assessment. It is a simulation for educational and portfolio purposes only.
