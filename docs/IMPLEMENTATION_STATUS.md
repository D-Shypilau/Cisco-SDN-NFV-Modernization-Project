# Implementation Status

This document separates the **thesis design**, the **exported EVE-NG laboratory**, and the **evidence currently published in this repository**.

It exists to keep the public portfolio technically honest and reproducible.

## Scope model

The bachelor thesis contains three different engineering layers:

1. **Enterprise modernization design** — the target architecture proposed for the NetCore Solutions academic case study.
2. **Logical validation** — routing, addressing, VLAN, ACL and resiliency concepts described through Cisco Packet Tracer and design calculations.
3. **High-fidelity laboratory** — the Cisco SD-WAN / Viptela and ASAv topology exported from EVE-NG.

Not every technology discussed in the target architecture is represented as a running node in the exported EVE-NG file.

## Exported EVE-NG lab: currently verifiable

The exported topology contains the following main functions:

- Cisco SD-WAN management component (`vManage` / SD-WAN Manager role);
- Cisco SD-WAN orchestration component (`vBond` / SD-WAN Validator role);
- Cisco SD-WAN control component (`vSmart` / SD-WAN Controller role);
- WAN Edge nodes for Warsaw, Madrid and Sevilla;
- Cisco ASAv security VNF in Frankfurt;
- an ISP/underlay simulation node;
- a Frankfurt core switching node;
- endpoint/VPC nodes used to represent branch and warehouse clients.

The repository should describe these components as the **implemented EVE-NG lab**.

## Thesis-level target architecture

The thesis additionally discusses or proposes:

- Cisco DNA Center / Cisco Catalyst Center;
- Cisco ISE;
- SGT-based microsegmentation / Zero Trust policy;
- Cisco NFVIS and ENCS-based SD-Branch/NFV deployment;
- automated ZTP workflow;
- NETCONF/YANG and API-driven management;
- dual-transport Hybrid WAN using Internet/MPLS/LTE/5G;
- HSRP and Packet Tracer logical validation;
- OSPF/OSPFv3 underlay concepts.

Until matching configuration, screenshots, logs, scripts or EVE-NG nodes are published, these items should be described as **designed, researched, modeled conceptually, or proposed**, not as fully reproduced by the exported EVE-NG lab.

## Evidence status for headline results

The thesis/defense materials report several important results. For a public engineering portfolio, every result should have a traceable evidence chain.

| Claim | Thesis result | Required public evidence |
| --- | ---: | --- |
| SD-WAN recovery / failover | 850 ms | topology showing both usable transports, BFD/SLA state, failure method, timestamped before/during/after output |
| ZTP deployment | 22–30 min | onboarding workflow, device state before onboarding, vBond/vManage evidence, timestamps, final template/config state |
| Security isolation | 3.8 s | actual ISE/SGT or equivalent implementation evidence, policy, trigger, timestamps and post-isolation verification |
| OPEX reduction | ~40% | assumptions and calculation workbook/report |
| Annual economic effect | ~€422k | baseline loss model and post-modernization assumptions |
| ROI | 28% | one documented ROI formula and the exact inputs used |
| Payback | 1.4 years | cash-flow/payback calculation consistent with the ROI and annual-savings model |

## Current reconciliation blockers

Before the final `v1.0-thesis-portfolio` release, the following values must be made consistent across the thesis, presentation, text configs and `.unl` export:

- organization name;
- site IDs;
- system IPs;
- controller management addresses;
- vBond/Validator address;
- Madrid and Sevilla site mapping;
- number of Madrid WAN Edge devices;
- presence/absence of a Madrid firewall;
- exact EVE-NG edition;
- exact Cisco image versions;
- WAN transport colors and subnets;
- whether a branch has one or two active WAN transports;
- whether the published security test used actual Cisco ISE/SGT or a simplified VLAN/ACL model.

## Important lab limitations

The current exported EVE-NG snapshot should not yet be presented as proof of every thesis experiment.

In particular:

- the current export does not show Cisco DNA Center / Catalyst Center or Cisco ISE nodes;
- the current export does not show an ENCS/NFVIS appliance;
- the published topology/configuration set does not yet provide a reproducible dual-transport LTE/5G failover scenario for the Sevilla WAN Edge;
- the repository does not yet contain API/NETCONF/YANG automation scripts proving controller-driven configuration;
- the text configuration files and embedded EVE-NG startup configurations currently represent different parameter sets.

These gaps do **not** invalidate the thesis design. They define what still needs to be reconciled or documented before the repository can claim full reproducibility.

## Product naming note

The thesis preserves the names used in the original laboratory and academic text: **Cisco SD-WAN, vManage, vBond, vSmart and Cisco DNA Center**.

In current Cisco documentation these are commonly branded as **Cisco Catalyst SD-WAN**, **Catalyst SD-WAN Manager**, **Catalyst SD-WAN Validator**, **Catalyst SD-WAN Controller**, and **Cisco Catalyst Center**. The repository may show both terms so that the thesis remains historically consistent while the portfolio remains understandable to current readers.

## Academic case-study notice

The organization, incident narrative, financial figures and internal-document style material in the thesis are presented as an **academic enterprise case study**. This repository is an educational engineering portfolio and is not an official corporate repository or a publication of confidential company records.
