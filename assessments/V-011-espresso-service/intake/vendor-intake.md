# Vendor Intake — Espresso Machine Service Company

Captured 2026-11-01 for a vendor already in use. The connected espresso machine was installed by this company when the shop opened (2026-01-15), and nobody assessed the vendor or its remote access at the time. The program's Connected Devices Procedure (PR-011) found the gap.

---

## Vendor Information

| | |
|---|---|
| **Vendor** | Espresso machine service company (unnamed; a regional equipment dealer and service provider) |
| **Vendor ID** | V-011 |
| **Service** | Commercial espresso machine supply and service contract: preventive maintenance every quarter, repairs, a telemetry portal (shot counts, boiler temperature, fault alerts, water filter life), and **remote diagnostics and firmware updates** through the vendor's cloud |
| **Internal business owner** | Daniel Lopez (Store Manager), with Olivia Carter (Owner) accountable |
| **Intake date** | 2026-11-01 |
| **In use since** | 2026-01-15 |

---

## Service Description

The machine (ESP-01) connects to the store Wi-Fi and makes outbound connections to the vendor's cloud. From there the vendor's technicians see its status, receive fault alerts, change settings, restart it and push firmware. Field technicians visit for quarterly maintenance and repairs.

---

## Data Handled by the Vendor

| Data | Classification |
|---|---|
| Machine telemetry (usage counts, temperatures, fault codes) | Internal |
| Store address and contact names and phone numbers | Internal |
| Service history and invoices | Internal |

**No cardholder data and no staff personal data** beyond contact details.

---

## System Access

  - **Remote:** the vendor can control the machine at any time through its cloud.
  - **Network:** the machine sits on the store network. Today that is the staff Wi-Fi, which the POS terminal also uses (P-005 §7 exception, POAM-015).
  - **On site:** field technicians use the machine's local service menu.
  - **Portal:** the shop has a portal account for viewing status and alerts.

---

## Business Criticality

**High for trading.** Most drinks depend on the espresso machine; an outage stops a large part of the menu. Payments are unaffected.

---

## Regulatory & Compliance Considerations

  - No PCI DSS data. The concern is the **network path**: a vendor-controlled device on the same network as the POS (PCI DSS Requirement 1 segmentation, SC-7)
  - Third-party remote access (NIST SP 800-53 MA-4)

---

## Initial Risk Indicators

  - Remote access with no record of who connects or when
  - Device shares the network with the POS until the Devices segment is built
  - Portal account set up by the vendor, not owned by the company

**Next step:** [Inherent Risk Score](../risk-scoring/inherent-risk-score.md)

---

*This document is a simulation for educational and portfolio purposes only. The vendor is fictional.*
