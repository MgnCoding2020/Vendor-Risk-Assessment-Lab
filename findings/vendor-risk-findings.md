# Vendor Risk Findings — Northwind Payroll Services

This register documents the findings from the due diligence review, with severity and recommended remediation. Severity reflects the potential impact to Burn and Churn Coffee if the gap is not addressed.

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|------------|-------------|-----------|----------|-------------------------|--------|
| F-01 | Vendor provided a SOC 2 Type I report only; Type II was not available, so control operating effectiveness over time is unverified | Assurance / Evidence | Medium | Obtain SOC 2 Type II, or interim compensating assurance, within 90 days | Open |
| F-02 | Multi-factor authentication is not enforced for all vendor administrative access to the platform | Access Control | High | Require MFA on all administrative and support accounts before go-live | Open |
| F-03 | Breach notification timeline is not defined in the contract or service agreement | Incident Response / Contractual | Medium | Add a defined breach-notification SLA (e.g., 72 hours) to the contract before go-live | Open |
| F-04 | Retention and secure-deletion policy for terminated-employee PII is not documented | Data Protection | Low | Obtain documented data retention and secure-deletion commitments within 90 days | Open |

---

## Notes

After the planned remediations are applied — most importantly F-02 and F-03 before go-live — residual risk is reduced from High to **Moderate**. Remediation status for each finding is tracked in the [remediation tracker](../remediation/remediation-tracker.md), and the findings roll up to the GRC program's POA&M as **POAM-013** under control **SA-9**.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)
