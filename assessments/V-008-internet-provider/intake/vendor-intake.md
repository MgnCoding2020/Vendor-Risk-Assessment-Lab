# Vendor Intake — Internet Service Provider

Captured 2026-11-02 for the shop's internet provider, in use since the shop opened and never scored or assessed.

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Internet service provider (unnamed; fictional) |
| **Vendor ID** | V-008 |
| **Service** | Small-business broadband, with a **provider-supplied and provider-managed router** (RTR-01) |
| **Internal business owner** | Olivia Carter (Owner) |
| **Intake date** | 2026-11-02 |

---

## Data Handled by the Vendor

| Data | Classification |
|---|---|
| All store internet traffic in transit (card payments are encrypted end to end by the POS provider; cloud services use TLS) | Confidential in transit |
| Account and billing details | Internal |

---

## System Access

The provider **manages the router remotely** (firmware, settings) and can reach it at any time. The shop's own firewall (FW-01) sits behind the router.

---

## Business Criticality

**High.** Without the internet the POS runs in offline mode or the shop goes to cash ([PR-005](https://github.com/MgnCoding2020/grc-paper-project-coffee-shop/blob/main/05-procedures/PR-005-contingency-plan.md)), and every cloud service stops.

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
