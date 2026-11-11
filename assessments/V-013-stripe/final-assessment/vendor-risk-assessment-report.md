# Vendor Risk Assessment Report
## Stripe (Card Payments, Test Mode)

| | |
|---|---|
| **Assessing Organization** | Burn and Churn Coffee |
| **Vendor** | Stripe, Inc. |
| **Vendor ID** | V-013 |
| **Service** | Stripe Terminal (server-driven, simulated reader), Checkout (website Phase 5), the Refunds API and webhooks; standard account, **test mode only** |
| **Assessment Date** | 2026-11-10 (in use since 2026-11-09; assessed a day late, see §1) |
| **Assessor** | Olivia Carter (Owner) |
| **Inherent Risk** | High (16 of 18; 17 at the CR-005 cutover) |
| **Residual Risk** | Low once F-01 and F-02 close |
| **Risk Decision** | **Continue with Conditions** |

---

## 1. Executive Summary

Stripe may continue as the company's card-payment provider for the counter and, from website Phase 5, online orders. Its own security is strongly evidenced:

- **PCI DSS Service Provider Level 1**;
- an **unqualified SOC 3** (security, availability, confidentiality) whose system description includes Stripe Terminal;
- an isolated card data vault with AES-256 encryption at rest;
- a Terminal certified to EMVCo and PA-DSS.

The company's integration keeps card data off its own systems entirely.

**This assessment is one day late.** On 2026-11-09 the Owner decided Stripe would be assessed before the card payments went live. The build went first: the Stripe set-up ran that evening, and card payments and refunds went live the same night. [P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) doesn't allow that, and it's the second time on this change (Cloudflare, V-014, was also assessed after use). Exposure was minimal, because the account runs in **test mode only** with no real money or card data. The lesson for the program: **assess before the go-live PR is merged, not after.**

The conditions are mostly on the company's side:

- obtain current assurance documents (the public SOC 3 period ended 2025-09-30);
- determine the company's own PCI scope and SAQ type;
- account housekeeping;
- confirm how to receive sub-processor notices.

## 2. Scope & Methodology

The assessment followed the program's workflow:

- the [intake](../intake/vendor-intake.md);
- the [six-factor inherent risk score](../risk-scoring/inherent-risk-score.md);
- [due diligence](../due-diligence/security-review.md) of Stripe's public documentation (checked 2026-11-10), its public SOC 3, and the service's behaviour in use: tests against Stripe's real test API on 2026-11-09 and 2026-11-10, and the Owner's production evidence;
- [findings](../findings/vendor-risk-findings.md) and a [remediation plan](../remediation/remediation-tracker.md).

The SOC 2 Type II and the PCI AOC are confidential and provided on request; they're reviewed under F-01.

## 3. Findings Summary

| ID | Finding | Severity |
|---|---|---|
| F-01 | PCI AOC and SOC 2 Type II not obtained; public SOC 3 period ended 2025-09-30 | Medium |
| F-02 | The company's own PCI scope and SAQ type not determined for either channel | Medium |
| F-03 | No fixed breach-notice window for this account | Low (accepted) |
| F-04 | No uptime commitment found | Low (accepted) |
| F-05 | Recovery codes, security-history review, and a key exposed in a chat (contained) | Medium |
| F-06 | Sub-processor notice subscription link appears broken | Low |

## 4. Conditions

1. **Already met (2026-11-09):**
   - a restricted key with custom permissions;
   - a one-time set-up key, deleted after use;
   - the exposed `sk_test_` key expired;
   - signed, replay-checked webhooks;
   - test mode enforced in code (website ADR-0006, ADR-0035).
2. **By 2026-11-15:** recovery codes in the Owner's password manager (SYS-022), and Stripe's security history and request log in the weekly review from 2026-11-14 (F-05).
3. **By 2026-12-10:**
   - current SOC 2 Type II (or bridge letter) and PCI service-provider AOC reviewed, with the 12.8.5 responsibility split recorded (F-01);
   - sub-processor notices confirmed (F-06).
4. **Before online ordering goes live** (CR-002 step 6): the company's PCI scope document and SAQ type, verified against current PCI SSC and Stripe documents (F-02).
5. **At the CR-005 cutover:** re-score (17, High), and re-decide the availability acceptance (F-04).

## 5. Program Linkage

- **Vendor inventory:** V-013 assessment Complete, 2026-11-10, inherent tier High; status Active (continue with conditions)
- **POA&M:** **POAM-037** (SA-9; PCI DSS 12.8), new, tracking these findings and the late assessment
- **Change:** CR-002 exit criterion "V-013 and V-014 assessed" is now met; its other half, "SAQ type confirmed", stays open as F-02
- **Re-assessment:** yearly (High, P-008), at the CR-005 cutover, or if the account ever leaves test mode (it won't in this project)

---

*This report is a simulation for educational and portfolio purposes only.*
