# Vendor Risk Findings — Microsoft (Microsoft 365)

Findings from the due diligence review. Outside this repository they are cited as `VRA-V003:F-01` to `VRA-V003:F-05` (see the program's [identifier conventions](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/00-company-profile/org/identifiers.md)).

---

## Findings

| Finding ID | Description | Risk Area | Severity | Recommended Remediation | Status |
|---|---|---|---|---|---|
| F-01 | The tenant runs on Entra ID Free, so Conditional Access isn't available; MFA can only be enforced per user or through tenant-wide security defaults | Access Control (customer side) | High | Enforce per-user MFA on every Burn and Churn account before go-live; plan for Entra ID P1 (included in the planned Business Premium and F1 licences) and move to Conditional Access when licensed | Open |
| F-02 | Microsoft's SOC 2 Type 2 and ISO/IEC 27001 reports have not been obtained or reviewed, including the customer-side controls they assume | Assurance / Evidence | Medium | After onboarding, sign in to the Service Trust Portal with the tenant's organizational account, download the current reports, and record the review (report period, exceptions, customer responsibilities) within 30 days | Open |
| F-03 | Just-in-time admin (PIM) needs Entra ID P2; admin roles will be standing | Privileged Access (customer side) | Medium | Accept the risk with compensating controls: separate `adm-` accounts with least-privilege roles, MFA, two break-glass accounts, admin roles checked in every quarterly access review | Open |
| F-04 | Entra ID Free keeps sign-in logs for only 7 days | Logging (customer side) | Low | Export sign-in and audit logs within the week as part of the log review procedure; use the Microsoft 365 audit log (180 days by default) once licensed | Open |
| F-05 | Nobody is subscribed to Microsoft's subprocessor change notifications | Third-Party Oversight | Low | Subscribe through the Service Trust Portal after onboarding; review changes at each annual vendor review | Open |

---

## Notes

None of the findings blocks onboarding if F-01's condition (MFA enforced before go-live) is met. With the conditions applied, residual risk falls from High to **Moderate**. Status is tracked in the [remediation tracker](../remediation/remediation-tracker.md), and the findings roll up to the GRC program's POA&M under control **SA-9**.

**Next step:** [Remediation Tracker](../remediation/remediation-tracker.md)

---

*This document is a simulation for educational and portfolio purposes only.*
