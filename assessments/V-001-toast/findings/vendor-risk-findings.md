# Vendor Risk Findings — Toast, Inc.

Outside this repository these findings are cited as `VRA-V001:F-01` to `VRA-V001:F-04` (see the program's [identifier conventions](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/00-company-profile/org/identifiers.md)).

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | Toast's PCI DSS Attestation of Compliance and PCI responsibility guide have not been obtained, so Toast's compliance status is unverified and there is no record of which PCI requirements Toast, the company, or both are responsible for (PCI DSS 12.8.4, 12.8.5) | PCI Third-Party Management | High | Request Trust Center access; download the current AOC and responsibility guide; record the AOC dates and covered services; build the company's responsibility matrix; repeat at least every 12 months | Open |
| F-02 | The company has not completed its own PCI DSS self-assessment, and the correct SAQ type is unknown | PCI Merchant Validation | High | Confirm the SAQ type with Toast and the acquiring bank, using the responsibility guide from F-01; complete the SAQ; the Owner signs it (P-004 §8) | Open |
| F-03 | No written agreement acknowledging Toast's responsibility for cardholder data security is on file (PCI DSS 12.8.2) | Contractual | Medium | Locate the Toast service agreement and confirm the acknowledgment language; file a copy with the vendor records | Open |
| F-04 | Toast's SOC 2 Type II report has not been obtained or reviewed | Assurance / Evidence | Medium | Download from the Trust Center with F-01; record the report period, exceptions and customer responsibilities | Open |

Company-side issues found during the review and already tracked elsewhere: POS terminal inspection (POAM-004) and an unnecessary POS admin role (IAM:F-002, POAM-014).

---

## Notes

Toast stays in service: it is the company's only way to take card payments, and nothing found suggests Toast itself is insecure. The findings are about the evidence the company is required to hold. With F-01 to F-04 closed, residual risk falls from High to **Moderate**. Status is tracked in the [remediation tracker](../remediation/remediation-tracker.md) and rolls up to the GRC program's POA&M under control **SA-9**.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only.*
