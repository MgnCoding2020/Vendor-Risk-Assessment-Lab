# Security Due Diligence Review — Cloudflare (Website Hosting and Database)

This review uses Cloudflare's **public** compliance, product and contract documentation, checked on 2026-11-08 (sources at the end), against the program's [due diligence checklist](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/02-risk-management/vendor-risk-management/vendor-due-diligence-checklist.md), plus what the company has seen of the service in use since 2026-11-02. Gaps go to the [findings register](../findings/vendor-risk-findings.md).

---

## Review Results

| Review Area | What Was Reviewed | Result | Finding |
|---|---|---|---|
| Independent assurance | Audits and certifications | **SOC 2 Type II** (security, confidentiality, availability); Cloudflare states **all plans are in scope** and lists **Workers and D1** as in-scope services. **ISO 27001:2022** (since 2019), **ISO 27018** and **ISO 27701**, scoped to "the Cloudflare global cloud platform"; Workers and D1 aren't named in the public ISO scope. **PCI DSS 4.0, Level 1 service provider** for a listed set of products: **Workers is listed; D1 is not**. Cloudflare doesn't publish a SOC 3. The reports need an NDA and a dashboard download by a Super Administrator; **not yet obtained** | F-01 |
| Encryption | Data at rest and in transit | D1 encrypts everything at rest (live and inactive databases, metadata) with AES-256, keys managed by Cloudflare; TLS between Workers, nodes and D1, and for the API and Wrangler | Adequate |
| Account security | Who controls the account and its secrets | One account, owned by the Owner, two-factor sign-in on (confirmed 2026-11-02); the build uses a dedicated token held by Cloudflare, not GitHub; secrets are Worker secrets, never in the repository (website secrets inventory). Where the account's two-factor **recovery codes** are kept isn't recorded | F-05 |
| Contract and breach notice | Terms for this account | Self-serve subscription agreement and Cloudflare's customer DPA. The DPA says Cloudflare will notify "without undue delay" on becoming aware of a breach; **no fixed 72-hour window** as P-008 §4 asks. New sub-processors are listed 30 days ahead, with 10 days to object | F-03 |
| Availability commitment | SLA | Cloudflare's published SLA applies to the Business and Enterprise plans; **no uptime commitment** for this Free account was found | F-04 |
| Security features working as documented | Use since 2026-11-02 | The **Rate Limiting binding** is attached to the Worker but **doesn't enforce** on this account: tested 2026-11-07 on a preview and in production (no request refused), while Cloudflare's local runtime enforces it. Matches an open Cloudflare issue ([workers-sdk #16097](https://github.com/cloudflare/workers-sdk/issues/16097)) with no published fix date. Compensated in the website: no anonymous request writes to the database (website ADR-0030) | F-04 |
| Sub-processors | Who else handles the service | Cloudflare's own affiliates, plus third-party cloud infrastructure (including Google, Oracle and AWS) supporting the Developer Platform, and support tools. New sub-processors are announced 30 days ahead (DPA). The list doesn't say whether these providers handle customer content for Workers and D1 | Adequate (scored in the inherent risk) |
| Backup and recovery | D1 Time Travel | Always-on point-in-time restore, **7 days back on the Free plan** (30 on Paid). A restore overwrites the database in place and can be undone. **Not yet tested** for this site; the audit log can't be recovered beyond 7 days | F-02 |
| Logging | What the company can see | Workers Logs for request logs (3-day retention on this plan, website ADR-0021); query strings redacted. The account audit log (who changed settings and secrets) wasn't reviewed | F-05 |
| Data location | Where D1 data lives | Not stated on the D1 data security page; not a constraint for this fictional US company, and no regulated data is held. Recorded, not a finding | — |

---

## Summary

Cloudflare's own security is well evidenced: a SOC 2 Type II that names Workers and D1, ISO 27001, 27018 and 27701, and encryption at rest and in transit by default. The gaps come from **how the company uses it**: the Free plan (no uptime commitment, 7-day restore window), self-serve terms (no fixed breach-notice window), a security feature that doesn't work on this account, and reports not yet obtained. Each has a compensating control or a dated action.

**Next step:** [Vendor Risk Findings](../findings/vendor-risk-findings.md)

---

## Sources (checked 2026-11-08)
  - [Cloudflare: SOC 2 FAQs](https://www.cloudflare.com/trust-hub/compliance-resources/soc-2/) (criteria, all plans in scope, Workers and D1 listed, NDA, no SOC 3 or SOC 1)
  - [Cloudflare: ISO certifications FAQs](https://www.cloudflare.com/trust-hub/compliance-resources/iso-certifications/) (27001:2022, 27018, 27701; scope)
  - [Cloudflare: Compliance documentation](https://developers.cloudflare.com/fundamentals/reference/policies-compliances/compliance-docs/) (Super Administrators only, confidentiality statement)
  - [Cloudflare D1: Data security](https://developers.cloudflare.com/d1/reference/data-security/) (AES-256 at rest, TLS in transit)
  - [Cloudflare D1: Time Travel](https://developers.cloudflare.com/d1/reference/time-travel/) (7 days on Free, 30 on Paid)
  - [Cloudflare: PCI DSS 4.0 FAQs](https://www.cloudflare.com/trust-hub/compliance-resources/pci-dss/) (Level 1 service provider; Workers listed, D1 not)
  - [Cloudflare: sub-processors for Cloudflare services](https://www.cloudflare.com/gdpr/subprocessors/cloudflare-services/)
  - [Cloudflare customer DPA](https://www.cloudflare.com/cloudflare-customer-dpa/) (breach notice "without undue delay"; sub-processor notice 30 days)
  - [Cloudflare: Business SLA](https://www.cloudflare.com/business-sla/) (Business plan; Enterprise has its own)
  - [Cloudflare: Rate Limiting binding](https://developers.cloudflare.com/workers/runtime-apis/bindings/rate-limit/) and [workers-sdk issue #16097](https://github.com/cloudflare/workers-sdk/issues/16097)
  - Website repository: [ADR-0029](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/adr/0029-rate-limits.md) (rate-limit tests), [ADR-0030](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/adr/0030-no-anonymous-database-writes.md), [threat model](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/threat-model.md), [secrets inventory](https://github.com/MgnCoding2020/burn-and-churn-website/blob/main/docs/secrets-inventory.md)

---

*This document is a simulation for educational and portfolio purposes only.*
