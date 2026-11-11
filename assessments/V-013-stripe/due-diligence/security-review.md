# Security Due Diligence Review — Stripe (Card Payments, Test Mode)

This review uses Stripe's **public** security, compliance and legal documentation, checked on 2026-11-10 (sources at the end), against the program's [due diligence checklist](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-due-diligence-checklist.md). It adds what the company has seen of the service in use since 2026-11-09. Gaps go to the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Independent assurance | Audits and certifications | **PCI DSS Service Provider Level 1**, assessed by a PCI-certified auditor, covering Stripe's card data vault. **SOC 1 and SOC 2 Type II** "produced annually and can be provided upon request". **SOC 3** is public and was reviewed (next row). Stripe Terminal is certified to **EMVCo Level 1 and 2** and **PA-DSS**. Stripe states its policies are aligned with the NIST Cybersecurity Framework. **The PCI AOC and SOC 2 report haven't been obtained** | F-01 |
| SOC 3 (public report) | The report itself | Stripe Global Payments and Revenue and Finance Automation System. **Period: October 1, 2024 to September 30, 2025**. Criteria: security, availability, confidentiality. **Unqualified opinion** ("fairly stated, in all material respects"), report dated October 27, 2025. **Stripe Terminal is in the system description.** Data-centre colocation subservice organizations are carved out, and the opinion depends on complementary user entity controls, which only the SOC 2 lists. **The period ended more than a year ago**, and no newer public report was found on 2026-11-10 | F-01 |
| The company's own PCI scope | What the company must do itself | Stripe tells each user which validation form (SAQ) applies and helps complete it in the Dashboard. The company hasn't yet determined its SAQ for the counter (Terminal) and online (Checkout) channels, and its scope document (website `docs/pci-scope.md`, plan §6.4) isn't written. The design already keeps card data off the company's systems (website ADR-0036) | F-02 |
| Encryption and card data handling | At rest and in transit | Card numbers encrypted at rest with AES-256, keys on separate machines; the card data vault runs in a separate, isolated AWS environment; TLS 1.2 or higher required; HSTS preloaded; mTLS between Stripe's internal services | Adequate |
| Contract and breach notice | Terms for this account | Standard services agreement and Stripe's DPA (updated 2026-09-28). Breach notice: "without undue delay"; a fixed **48 hours** applies only to personal data under the GDPR or UK GDPR. **No fixed window for this US company** as P-008 §4 asks. Audit reports are provided on written request, as Stripe's confidential information; a security questionnaire at most once a year | F-03 |
| Availability commitment | SLA | **No uptime commitment found** for a standard account; Stripe publishes a status page. In the website: cash works if Stripe is down, and the register asks Stripe directly if a webhook is late (website ADR-0036) | F-04 |
| Account security | Who controls the account and its keys | One account, the Owner's, with two-factor authentication (prompted when the key was created, 2026-11-09); Stripe supports passkeys and hardware keys, and recommends them over SMS. The website uses a **restricted key** with custom permissions; a one-time set-up key was deleted after use (website ADR-0035). **On 2026-11-09 the test-mode secret key was pasted into an AI chat**; it was expired the same day and nothing uses a full secret key. Where the two-factor **recovery codes** are kept isn't recorded, and Stripe's **security history** (its account audit log) isn't reviewed | F-05 |
| Security features working as documented | Use since 2026-11-09 | Checked against Stripe's real test API on 2026-11-09 and 2026-11-10: signed webhooks (unsigned and forged ones refused by the site), PaymentIntents, the simulated reader and its test helper, declines, cancel, and refunds (partial, full, over-refund refused). The restricted key's permissions covered every call, and nothing more was needed (website evidence `2026-11-09-stripe-setup`, `2026-11-09-card-payments`, `2026-11-10-card-refunds`) | Adequate |
| Sub-processors | Who else handles the data | Published list (updated 2026-09-27): AWS (US and India), Microsoft Azure, Google, Snowflake, Databricks and others. Changes: 30 days' notice to users who subscribe by email, with 30 days to object. **On 2026-11-10 the list page's subscribe link appeared to point to another company's sub-processor page**, so whether the company can actually subscribe is unconfirmed | F-06 |
| Logging | What the company can see | Stripe's request logs per API key, the account security history (exportable), and webhook delivery logs in the Dashboard; the website records each event's ID and outcome (never the payload) for 90 days | Adequate (review covered under F-05) |

---

## Summary

Stripe's own security is strongly evidenced:

- PCI DSS Level 1 as a service provider;
- an unqualified SOC 3 that names Stripe Terminal;
- an isolated card data vault with AES-256 at rest;
- an EMVCo- and PA-DSS-certified Terminal.

The gaps are on the company's side:

- reports not yet obtained, and the public SOC 3 more than a year old;
- the company's own PCI scope and SAQ not yet determined;
- self-serve terms with no fixed breach-notice window;
- no uptime commitment;
- account housekeeping: recovery codes, security-history review, and the lesson of a key pasted into a chat;
- a sub-processor notice link that looks broken.

None of these calls for leaving Stripe.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

## Sources (checked 2026-11-10)

- [Stripe: Security at Stripe](https://docs.stripe.com/security) (PCI Service Provider Level 1; SOC 1 and SOC 2 Type II on request; SOC 3 public; EMVCo and PA-DSS for Terminal; NIST CSF; AES-256 and the isolated card data vault; TLS 1.2+, HSTS, mTLS; Dashboard MFA options; restricted keys; security history)
- [Stripe SOC 3 report](https://docs.stripecdn.com/ebe9bebbdc5210a59ca18de4917ff3b152961a83fa3a98fbb81c758792472389.pdf), linked from the security page: period 2024-10-01 to 2025-09-30, report dated 2025-10-27
- [Stripe Data Processing Agreement](https://stripe.com/legal/dpa), updated 2026-09-28: breach notice, sub-processor notice, audit reports on request
- [Stripe: service providers (sub-processors)](https://stripe.com/legal/service-providers), updated 2026-09-27
- [Stripe status](https://status.stripe.com)
- [Stripe: Test Stripe Terminal](https://docs.stripe.com/terminal/references/testing) and [Collect card payments (server-driven)](https://docs.stripe.com/terminal/payments/collect-card-payment), checked 2026-11-09
- Website repository: [ADR-0035](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/adr/0035-stripe-library-keys-and-webhooks.md) (keys, webhooks), [ADR-0036](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/adr/0036-counter-card-payments.md) (card payments), [ADR-0037](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/adr/0037-card-refunds.md) (card refunds), [secrets inventory](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/secrets-inventory.md), and the evidence folders named above

---

*This document is a simulation for educational and portfolio purposes only.*
