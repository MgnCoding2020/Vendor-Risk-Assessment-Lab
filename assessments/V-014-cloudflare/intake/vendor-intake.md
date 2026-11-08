# Vendor Intake — Cloudflare (Website Hosting and Database)

Captured 2026-11-08, **after the service went into use**. Cloudflare has hosted the company's website since 2026-11-02 (CR-002), and since 2026-11-07 it also holds staff data. Under [P-008](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/04-policies/P-008-third-party-risk.md) step 5, a vendor in use but never assessed is assessed as soon as it's found, and the decision is continue, continue with conditions, or exit. The gap was found in the program alignment pass of 2026-11-07 (hub AL-30, POAM-036).

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Cloudflare, Inc. |
| **Vendor ID** | V-014 |
| **Service** | Workers (the website, staff portal and its API), D1 (database), static assets, Workers Logs, Workers Builds (build and deploy from GitHub); **Workers Free plan**, self-serve terms |
| **System** | SYS-020, the online ordering website ([CR-002](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/09-change-management/CR-002-online-ordering-website.md)) |
| **Internal business owner** | Olivia Carter (Owner) |
| **Requested by** | Owner, via CR-002 |
| **In use since** | 2026-11-02 (public site); 2026-11-07 (staff sign-in and staff data) |
| **Intake date** | 2026-11-08 |

---

## Data Handled by the Vendor

| Data | Where | Classification |
|---|---|---|
| Website code, content and menu | Workers, static assets | Public |
| Staff names, Entra directory IDs and portal roles | D1 `users` | Internal |
| Signed-in sessions (only a hash of each session token) | D1 `sessions` | Internal |
| Staff audit log: sign-ins, sign-outs, refused sign-ins | D1 `audit_log` | Internal |
| Request logs: method, path, status, timing; Cloudflare's own logs also hold IP addresses (3 days) | Workers Logs | Internal |
| Worker secrets: the staff app's certificate private key and its IDs; later Stripe test keys | Encrypted Worker secrets | Restricted |
| Later (Phase 3 onwards): test orders, no card data | D1 | Internal |

**No cardholder data** is stored or processed: card details stay on Stripe's pages and readers (CR-002, CR-005). The staff are fictional lab accounts.

---

## System Access

Cloudflare runs the company's code and holds its secrets. Whoever controls the Cloudflare account can deploy code to the site and read every Worker secret by redeploying, including the certificate that lets the website sign people in through Entra ID. The account is the Owner's alone, with two-factor sign-in (confirmed 2026-11-02, website threat model §2.4).

---

## Business Criticality

Moderate today: the public site and staff portal. **Rising to High** when the register replaces Toast (CR-005): the counter then depends on it to take orders.

---

## Initial Risk Indicators

  - Holds a credential to the company's identity tenant (the staff app's certificate) as a Worker secret
  - Free plan: no published uptime commitment; support through the community and documentation
  - A documented security feature (the Rate Limiting binding) was found not to work on this account (website ADR-0029)
  - D1 point-in-time restore reaches back 7 days on the Free plan

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only.*
