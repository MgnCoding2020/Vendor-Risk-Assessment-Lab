# Vendor Risk Assessment Report
## Northwind Payroll Services

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Northwind Payroll Services |
| **Vendor ID** | V-002 |
| **Service** | Cloud Payroll & HR platform (SaaS) |
| **Assessment Date** | YYYY-MM-DD |
| **Assessor** | [Name / Role] |
| **Inherent Risk** | High |
| **Residual Risk** | Moderate |
| **Risk Decision** | **Approve with Conditions** |

---

## 1. Executive Summary

Northwind Payroll Services was assessed as a third-party cloud payroll and HR platform that will process sensitive employee data on behalf of Burn and Churn Coffee, including employee personally identifiable information (PII), payroll and tax records, and direct-deposit banking details.

Because of the sensitivity of this data, the vendor's **inherent risk** is rated **High**. Due diligence identified four findings, none of which are disqualifying, but two of which should be remediated before the platform goes live. With the planned remediations applied, **residual risk** is reduced to **Moderate**.

The recommended decision is to **approve the vendor with conditions**, with the open findings tracked to closure through the GRC program's POA&M.

---

## 2. Scope & Methodology

This assessment followed the vendor risk management process defined in the GRC program, using its standard templates:

1. **Vendor intake** — service type, data processed, and access requirements collected
2. **Inherent risk scoring** — risk rated before reviewing the vendor's controls
3. **Due diligence** — review of the vendor's security documentation and practices
4. **Findings & remediation** — gaps documented and assigned remediation
5. **Final risk determination** — residual risk and approval decision

The governing control is **NIST SP 800-53 SA-9 (External System Services)**. Note that **PCI DSS Req. 12.8 does not apply** to this vendor, because Northwind does not process cardholder data — this is what distinguishes it from a payment vendor such as Toast POS, which would fall under PCI service-provider management.

---

## 3. Vendor Overview

Northwind Payroll Services provides a web-based Software-as-a-Service (SaaS) platform used for payroll processing, employee onboarding, tax form management, direct-deposit management, and employee information storage. The platform integrates with the company's internal payroll workflow and is accessed by internal HR and finance personnel. Vendor support staff may require limited administrative access for platform maintenance.

**Data processed by the vendor:**

- Employee personally identifiable information (PII)
- Payroll and tax records
- Direct-deposit banking information

---

## 4. Inherent Risk Rating — High

Inherent risk was assessed as **High** before reviewing the vendor's controls, driven by:

- **Data sensitivity** — employee PII, financial, and banking data
- **Operational dependency** — payroll is a critical, time-sensitive business function
- **System access** — internal HR/finance access plus vendor administrative access to sensitive data

A High inherent rating requires full due diligence, which was performed below.

---

## 5. Due Diligence Summary

The vendor's security posture was reviewed across the following areas. Documentation was requested covering independent assurance, access control, encryption, incident response, and data handling.

| Area | Result |
|------|--------|
| Independent security assurance (SOC 2) | Partial — see F-01 |
| Access control & authentication | Gap — see F-02 |
| Encryption (in transit / at rest) | Adequate — TLS in transit, encryption at rest confirmed |
| Incident response & breach notification | Gap — see F-03 |
| Data retention & secure deletion | Gap — see F-04 |
| Operational resilience / availability | Adequate — documented uptime commitments |

---

## 6. Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation |
|------------|-------------|-----------|----------|-------------------------|
| F-01 | Vendor provided a SOC 2 Type I report only; Type II (operating effectiveness over time) was not available | Assurance / Evidence | Medium | Obtain SOC 2 Type II, or interim compensating assurance, within 90 days |
| F-02 | Multi-factor authentication is not enforced for all vendor administrative access to the platform | Access Control | High | Require MFA on all administrative and support accounts before go-live |
| F-03 | Breach notification timeline is not defined in the contract or service agreement | Incident Response / Contractual | Medium | Add a defined breach-notification SLA (e.g., 72 hours) to the contract |
| F-04 | Retention and secure-deletion policy for terminated-employee PII is not documented | Data Protection | Low | Obtain documented data retention and secure-deletion commitments |

---

## 7. Residual Risk — Moderate

After applying the planned remediations — most importantly enforcing MFA on vendor administrative access (F-02) and establishing a contractual breach-notification SLA (F-03) — the residual risk is reduced from High to **Moderate**. The remaining residual risk reflects the inherent sensitivity of the data combined with the dependency on a third party, which cannot be fully eliminated.

---

## 8. Risk Decision — Approve with Conditions

The vendor is **approved with conditions**. The following must be satisfied:

- **Before go-live:** remediate F-02 (enforce MFA on vendor admin access) and F-03 (contractual breach-notification SLA)
- **Within 90 days:** obtain SOC 2 Type II or compensating assurance (F-01)
- **Within 90 days:** obtain documented data retention and secure-deletion commitments (F-04)

The vendor will be **reassessed in 12 months**, or sooner upon any material change to the service or a security incident.

---

## 9. Governance Linkage

This assessment connects back to the GRC program as follows:

- **Vendor inventory:** V-002 (Northwind Payroll) is updated to **Assessment Status = Complete** with this assessment date.
- **POA&M:** the open findings are tracked at the program level under control **SA-9** as a single rolled-up item (**POAM-013**), which references this report. Per-finding remediation status is tracked in the lab's remediation tracker.
- **Governing control:** NIST SP 800-53 **SA-9** (External System Services).

---

## 10. References

- GRC program — Vendor Inventory (`02-risk-management/vendor-risk-management/vendor-inventory.md`)
- GRC program — POA&M (`07-evidence-pack/poam/poam.md`)
- GRC program — Risk Register, control SA-9
- NIST SP 800-53 Rev. 5 — SA-9 (External System Services)

---

*This report is a simulation for educational and portfolio purposes only.*
