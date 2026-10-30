# Inherent Risk Score — Northwind Payroll Services

Inherent risk is the level of risk a vendor introduces **before** reviewing its security controls. It is scored using the factors defined in the GRC program's **Inherent Risk Scoring Worksheet**, and it determines how much due diligence is required.

---

## Scoring Factors

| Factor | Rating | Rationale |
|--------|--------|-----------|
| Data sensitivity | High | Employee PII, payroll/tax records, and direct-deposit banking data |
| System access | High | Internal HR/finance access plus vendor administrative access to sensitive data |
| Operational dependency | High | Payroll is a critical, time-sensitive business function |
| Regulatory exposure | Moderate | Employee privacy and financial data; no cardholder data (PCI DSS Req. 12.8 not applicable) |

---

## Scoring Method

Each factor is rated Low, Moderate, or High. The overall inherent risk tier is driven primarily by the highest-impact factors — here, data sensitivity, system access, and operational dependency are all High.

## Result

**Overall Inherent Risk: High**

A High inherent rating requires a full due diligence review before a final risk decision can be made.

**Next step:** [Security Due Diligence Review](../due-diligence/security-review.md)
