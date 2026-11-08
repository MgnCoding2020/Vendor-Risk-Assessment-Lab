# Vendor Risk Assessment Report
## Cloudflare (Website Hosting and Database)

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Cloudflare, Inc. |
| **Vendor ID** | V-014 |
| **Service** | Workers, D1, Workers Logs and Workers Builds, Workers Free plan (self-serve terms) |
| **Assessment Date** | 2026-11-08 (in use since 2026-11-02; assessed late, see §1) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | Moderate (13 of 18; High at 14 once the register replaces Toast) |
| **Residual Risk** | Low once conditions are met |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

Cloudflare may continue to host the website, staff portal and database. Its own security is well evidenced: a SOC 2 Type II whose scope names Workers and D1 and covers every plan; ISO 27001, 27018 and 27701; and encryption at rest and in transit by default.

This assessment is **late**. Cloudflare went into use on 2026-11-02 and began holding staff data on 2026-11-07 without one, which [P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) doesn't allow. The program's alignment pass found the gap the same day (hub AL-30, POAM-036). As step 5 of the policy requires for a vendor already in use, the decision is continue, continue with conditions, or exit.

The conditions come from how the company uses the service:
- **the Free plan:** no uptime commitment, and a 7-day restore window;
- **self-serve terms:** no fixed breach-notice window;
- **a rate-limiting feature that doesn't work on this account;**
- **reports not yet obtained.**

## 2. Scope & Methodology

[Intake](../intake/vendor-intake.md), [six-factor inherent risk score](../risk-scoring/inherent-risk-score.md), [due diligence](../due-diligence/security-review.md) of Cloudflare's public documentation (checked 2026-11-08) and of the service's behaviour in use (the website's own tests, 2026-11-07), [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md). The SOC 2 report and PCI AOC themselves need an NDA and are reviewed under F-01.

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | SOC 2 Type II and PCI DSS AOC not yet reviewed | Low |
| F-02 | 7-day restore window, untested; audit log not kept beyond it | Medium |
| F-03 | No fixed breach-notice window (self-serve terms) | Low (accepted) |
| F-04 | No uptime commitment; Rate Limiting binding doesn't enforce on this account | Medium |
| F-05 | Recovery codes have no recorded home; account audit log not reviewed | Medium |

## 4. Conditions

1. **Already met (2026-11-07):** no anonymous request writes to the database, compensating for F-04 (website ADR-0030).
2. **By 2026-11-15:** recovery codes stored in the password manager, and the Cloudflare account audit log in the weekly review (F-05). `audit_log` exported with each weekly review from 2026-11-14 (F-02).
3. **By 2026-12-08:** SOC 2 Type II and PCI DSS AOC reviewed and recorded (F-01).
4. **Before the first website route that calls a paid service** (Stripe, website Phase 4): the website's own rate limiter, and a re-check of Cloudflare's fix (F-04).
5. **Before the register replaces Toast** (CR-005):
   - a recorded D1 restore test (F-02);
   - a decision on Free versus Paid (uptime, 30-day restore window);
   - a re-score of this assessment: operational dependency rises, giving 14, High.

## 5. Program Linkage

- **Vendor inventory:** V-014 assessment Complete, 2026-11-08, inherent tier Moderate; status Active (continue with conditions)
- **POA&M:** POAM-036 (SA-9), now tracking these findings
- **Change:** CR-002 exit criterion "V-013 and V-014 assessed" half met: V-014 done, V-013 Stripe still to come before website Phase 4
- **Re-assessment:** at the CR-005 cutover (re-scored High, then yearly), otherwise every two years (Moderate, P-008), or if the plan changes

---

*This report is a simulation for educational and portfolio purposes only.*
