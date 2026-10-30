# Security Due Diligence Review — Northwind Payroll Services

This review evaluates the vendor's security posture across key control domains. Documentation was requested covering independent assurance, access control, encryption, incident response, and data handling. Each gap identified here is carried into the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|-------------|-------------------|--------|---------|
| Independent assurance (SOC 2) | Independent audit report covering security controls | SOC 2 Type I provided; Type II (operating effectiveness over time) not available | F-01 |
| Access control & authentication | MFA enforcement, role-based access, administrative access | Role-based access present; MFA not enforced on all vendor admin/support accounts | F-02 |
| Encryption | Protection of data in transit and at rest | TLS in transit; encryption at rest confirmed | Adequate |
| Incident response & breach notification | Incident handling process and contractual notification timeline | Incident process exists; breach-notification timeline not defined in contract | F-03 |
| Data retention & secure deletion | Handling of terminated-employee PII | Retention and secure-deletion policy not documented | F-04 |
| Operational resilience / availability | Uptime and availability commitments | Documented uptime commitments | Adequate |

---

## Summary

The vendor's overall security posture is reasonable, with encryption and operational resilience adequate. Four gaps were identified across assurance, access control, incident response, and data protection. These are documented as findings F-01 through F-04 and drive the residual risk determination.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)
