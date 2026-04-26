# Cisco SD-WAN & NFV Network Modernization Project
**Enterprise Case Study: NetCore Solutions GmbH**


## 🚀 Executive Summary
This project delivers a complete architectural redesign and verification of a distributed enterprise network using **Cisco SDN (Software-Defined Networking)** and **NFV (Network Function Virtualization)**. The solution transitions a legacy CLI-managed infrastructure into a programmable, automated, and secure SD-WAN environment.

## 📊 Key Results (Verified in EVE-NG)
* **ROI (1st Year):** 28%
* **Payback Period:** 1.4 years
* **OPEX Reduction:** 40% through automation and Hybrid WAN.
* **Network Convergence:** < 850 ms (verified failover between MPLS and Internet).
* **Deployment Speed (ZTP):** < 30 minutes per site (200x faster than traditional methods).

## 🏗 Network Architecture
The infrastructure follows a hub-and-spoke topology across 4 major European sites:
* **DE-FRA-CORE (Frankfurt):** Central Data Center with Management (vManage), Orchestration (vBond), and Control (vSmart) planes.
* **PL-WAR-BR01 (Warsaw):** Remote office with vEdge routing.
* **ES-MAD-HQ (Madrid):** Regional hub with High Availability (HA) and ASAv security.
* **ES-SEV-WH (Sevilla):** Warehouse site with automated WMS traffic prioritization.

![Network Topology](./topology/EVE.png)

## 🛠 Technology Stack
* **Control/Management:** Cisco SD-WAN (Viptela) vManage, vSmart, vBond.
* **Data Plane:** Cisco vEdge Cloud, cEdge.
* **Virtualization:** Cisco NFV, ENCS 5400, ASAv (Firewall).
* **Simulation:** EVE-NG Professional.
* **Automation:** Zero Touch Provisioning (ZTP), Policy-based routing.

## 📂 Project Structure
* [/configs](./configs) - Base and operational configurations for all SD-WAN components.
* [/topology](./topology) - EVE-NG export files and visual network diagrams.
* [/analytics](./analytics) - Business impact reports, ROI calculations, and verification protocols.
* [/presentation](./presentation) - Full technical documentation and thesis presentation.

## 🛡 Business Impact
The project was initiated following a critical outage in Sevilla that cost the company **€57,480**. By implementing SD-WAN policies, we eliminated single points of failure and reduced manual configuration errors by **99.6%**, preventing an estimated **€247,000/year** in potential downtime losses.

---
**Author:** [Dzmitry Shypilau]
**Contact:** [https://www.linkedin.com/in/dzmitry-shypilau-383b181a0/ru/?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BcpoxsVJ%2FRS%2BRfCEPL9tlxQ%3D%3D]
