# Security Due Diligence Review — Microsoft (Microsoft 365)

This review uses Microsoft's **public** compliance documentation, checked on 2026-10-30 (sources at the end). A key input is Microsoft's **shared responsibility model**: for software-as-a-service, Microsoft runs the platform, but the customer always keeps responsibility for its **data, accounts and identities**, and shares responsibility for devices. Several gaps below are therefore on Burn and Churn's side of the line, not Microsoft's. Each gap is carried into the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Independent assurance | SOC 2 Type 2 and ISO/IEC 27001 reports | Published on Microsoft's Service Trust Portal, but available only after signing in with an organizational account and accepting a confidentiality agreement. **Not yet obtained or reviewed**, including the customer-side controls the reports assume | F-02 |
| Breach notification | Contractual incident-notice commitment | Microsoft states it notifies affected customers within 72 hours of declaring a security incident involving customer data, under its Data Protection Addendum (DPA) | Adequate |
| Subprocessors | Disclosure and change notice | Subprocessor list published; new subprocessors handling customer data are announced six months ahead, with notifications available through the Service Trust Portal | F-05 |
| Customer identity security (shared responsibility) | MFA and sign-in policy available to the company's tenant | The tenant runs on **Entra ID Free**: no Conditional Access; MFA only through per-user MFA or security defaults | F-01 |
| Privileged access (shared responsibility) | Just-in-time admin (PIM) | Requires Entra ID P2, which the company doesn't have; admin roles would be standing | F-03 |
| Logging (shared responsibility) | Log availability and retention | Entra ID Free keeps sign-in logs for 7 days; longer retention needs a higher licence or the Microsoft 365 audit log (180 days by default) | F-04 |
| Encryption | Data in transit and at rest | Microsoft-managed encryption, documented in its service assurance pages | Adequate |

---

## Summary

Microsoft's own controls are strongly evidenced in public, but the reports themselves still need to be obtained and read. The larger risks sit on the company's side of the shared-responsibility line: identity protection, privileged access and log retention are limited by the licence the company actually has. These are findings F-01 to F-05.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

## Sources (checked 2026-10-30)

- [SOC 2 Type 2 (Microsoft compliance offerings)](https://learn.microsoft.com/en-us/compliance/regulatory/offering-soc-2)
- [ISO/IEC 27001 (Azure compliance offerings)](https://learn.microsoft.com/en-us/azure/compliance/offerings/offering-iso-27001)
- [Security incident management overview](https://learn.microsoft.com/en-us/compliance/assurance/assurance-incident-management)
- [Supplier management overview](https://learn.microsoft.com/en-us/compliance/assurance/assurance-supplier-management)
- [Shared responsibility in the cloud](https://learn.microsoft.com/en-us/azure/security/fundamentals/shared-responsibility)
- [Microsoft Entra data retention](https://learn.microsoft.com/en-us/entra/identity/monitoring-health/reference-reports-data-retention)
- [Microsoft Entra licensing](https://learn.microsoft.com/en-us/entra/fundamentals/licensing)

---

*This document is a simulation for educational and portfolio purposes only.*
