# Vendor Intake — Northwind Payroll Services

This intake record is the first step of the vendor risk assessment. It captures basic information about the vendor and the service, and is used to determine the inherent risk level and the depth of due diligence required. It is the completed version of the GRC program's **Vendor Intake Questionnaire** template.

---

## Vendor Information

| Field | Detail |
|-------|--------|
| Vendor Name | Northwind Payroll Services |
| Vendor ID | V-002 |
| Service Type | Cloud Payroll & HR platform (SaaS) |
| Internal Sponsor | HR / Finance |
| Assessing Organization | Burn and Churn Coffee |

---

## Service Description

Northwind provides a web-based SaaS platform used for payroll processing, employee onboarding, tax form management, direct-deposit management, and employee information storage. It integrates with the company's internal payroll workflow.

---

## Data Handled by the Vendor

- Employee personally identifiable information (PII)
- Payroll and tax records
- Direct-deposit banking information

---

## System Access

- Internal HR and finance staff access the platform through a web interface.
- Vendor support personnel may require limited administrative access for platform maintenance.
- The platform integrates with the internal payroll workflow.

---

## Business Criticality

Payroll is a **critical, time-sensitive** business function. An outage or data issue directly affects employees being paid accurately and on time.

---

## Regulatory & Compliance Considerations

- The data includes employee PII and financial/banking information (privacy and financial-data sensitivity).
- The vendor does **not** process cardholder data, so **PCI DSS Req. 12.8 does not apply**. The governing control is **NIST SP 800-53 SA-9 (External System Services)**.

---

## Initial Risk Indicators

Sensitive employee/financial data, a critical business function, and vendor administrative access together indicate an elevated inherent risk. A full inherent risk scoring and due diligence review are required.

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)
