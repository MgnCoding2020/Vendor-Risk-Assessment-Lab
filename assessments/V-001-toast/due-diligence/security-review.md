# Security Due Diligence Review — Toast, Inc.

This review uses Toast's **public** information, checked on 2026-10-30 (sources at the end). Toast's detailed compliance reports are shared only with active customers through its Trust Center, after an access request; obtaining them is a finding below. PCI DSS v4.0.1 Requirement 12.8 sets what a merchant must hold for each payment service provider: a list of providers (12.8.1), a written agreement acknowledging the provider's responsibility for cardholder data (12.8.2), due diligence before engagement (12.8.3), at least annual monitoring of the provider's PCI DSS compliance status (12.8.4), and a record of which requirements the provider manages, which the merchant manages, and which are shared (12.8.5).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| PCI DSS status (12.8.4) | Service-provider validation | Toast states in its annual report (Form 10-K) that it is a **PCI DSS Level 1 service provider**, assessed annually by an independent assessor. Its Attestation of Compliance (AOC) is available to customers in the Toast Trust Center but **has not been obtained**, so the validity dates and the services it covers are unconfirmed | F-01 |
| Responsibility split (12.8.5) | Which PCI requirements Toast covers vs the company | Toast publishes a PCI responsibility guide to customers. **Not obtained**; the company has no record of which requirements it owns | F-01 |
| Merchant validation | The company's own PCI DSS self-assessment (SAQ) | **No SAQ has been completed**, and the correct SAQ type is unknown. Toast's PCI-validated point-to-point encryption (which can shorten merchant validation) was announced for select enterprise customers only, so the company can't assume it qualifies | F-02 |
| Written agreement (12.8.2) | Contract language acknowledging Toast's responsibility for cardholder data | Not located in company records | F-03 |
| Independent assurance | SOC 2 Type II | Toast's Trust Center offers a SOC 2 Type II report covering its core POS offering. **Not obtained** | F-04 |
| POS device security (shared) | Terminal inspection for tampering (PCI DSS 9.5.1) | Company side. Already tracked by the program as POAM-004 (no formal inspection process) | Covered by POAM-004 |
| POS admin access (company side) | Least privilege for POS roles | Company side. The Q1 access review found a shift leader with an unnecessary Toast admin role (IAM:F-002), overdue | Covered by POAM-014 |
| Vulnerability reporting | Public security contact | Toast publishes a vulnerability-reporting page | Adequate |

---

## Summary

Toast publicly states strong PCI credentials, but the company holds **none of the evidence PCI DSS 12.8 expects it to keep**: no AOC, no responsibility matrix, no written agreement on file, and no SAQ of its own. These are paperwork gaps rather than evidence that Toast is insecure, but for the company's highest-risk vendor they are significant. Two company-side issues (device inspection, POS admin rights) are already tracked elsewhere in the program.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

## Sources (checked 2026-10-30)

- [Toast, Inc. Form 10-K, fiscal year 2025 (SEC)](https://www.sec.gov/Archives/edgar/data/1650164/000165016426000057/tost-20251231.htm): PCI DSS Level 1 service provider statement
- [Access Toast Compliance Reports in the Toast Trust Center](https://support.toasttab.com/en/article/Access-Toast-Compliance-Reports-in-the-Toast-Trust-Center): AOC, PCI responsibility guide, SOC 2 Type II; customer access on request
- [Toast and Bluefin P2PE announcement (2023)](https://www.businesswire.com/news/home/20230425005369/en): PCI-validated P2PE for select enterprise customers
- [Toast security and vulnerability reporting](https://pos.toasttab.com/security)
- PCI DSS v4.0.1 Requirement 12.8 sub-requirements as summarised by secondary sources; confirm against the PCI SSC standard text

---

*This document is a simulation for educational and portfolio purposes only.*
