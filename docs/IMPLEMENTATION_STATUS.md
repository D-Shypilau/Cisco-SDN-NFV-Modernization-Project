# Implementation Status

This document separates the **thesis design**, the **exported EVE-NG laboratory**, and the **evidence currently published in this repository**.

It exists to keep the public portfolio technically honest and reproducible.

## Scope model

The bachelor thesis contains three different engineering layers:

1. **Enterprise modernization design** — the target architecture proposed for the NetCore Solutions academic case study.
2. **Logical validation** — routing, addressing, VLAN, ACL and resiliency concepts described through Cisco Packet Tracer and design calculations.
3. **High-fidelity laboratory** — the Cisco SD-WAN / Viptela and ASAv topology exported from EVE-NG.

Not every technology discussed in the target architecture is represented as a running node in the exported EVE-NG file.

## Exported EVE-NG lab: currently documented

The exported topology contains the following main functions:

- Cisco SD-WAN management component (`vManage` / SD-WAN Manager role);
- Cisco SD-WAN orchestration component (`vBond` / SD-WAN Validator role);
- Cisco SD-WAN control component (`vSmart` / SD-WAN Controller role);
- WAN Edge nodes for Warsaw, Madrid and Sevilla;
- Cisco ASAv security VNF in Frankfurt;
- an ISP/underlay simulation node;
- a Frankfurt core switching node;
- endpoint/VPC nodes used to represent branch and warehouse clients.

The public `.unl` has been sanitized and its branch addressing/site/transport baseline is documented in [`ARCHITECTURE_BASELINE.md`](./ARCHITECTURE_BASELINE.md), [`../lab/eve-ng/inventory.yaml`](../lab/eve-ng/inventory.yaml) and [`../configs/canonical/`](../configs/canonical/).

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

## Evidence status for headline technical results

The thesis/defense materials report several important results. For a public engineering portfolio, every measured result should have a traceable evidence chain.

- SD-WAN recovery / failover: **850 ms** — thesis-reported; current public topology lacks the same dual-transport test condition.
- ZTP deployment: **22–30 min** — thesis-reported; current public artifacts do not contain a reproducible onboarding capture.
- Security isolation: **3.8 s** — thesis-reported; current public lab does not implement the same ISE/SGT test chain.

Generated expected-state examples are therefore stored separately under [`../evidence/simulated/`](../evidence/simulated/) and explicitly labeled as not captured from a running lab.

## Economic KPI status

The economic model has now been reconciled separately from the legacy thesis KPI set. See [`../analytics/ECONOMIC_MODEL.md`](../analytics/ECONOMIC_MODEL.md).

The canonical public calculation uses:

- traditional annual OPEX: **€430,000**;
- optimized annual OPEX: **€262,000**;
- annual OPEX saving: **€168,000**;
- OPEX reduction: **39.1% (~40% rounded)**;
- avoided-loss assumption: **€247,000/year**;
- reconciled gross annual economic effect: **€415,000/year**;
- investment range: **€180,000–€220,000**;
- simple full-effect payback: **0.43–0.53 years**;
- simple first-year ROI: **88.6%–130.6%**.

The defense-material values **€422,000/year**, **28% ROI** and **1.4-year payback** remain historical **thesis-reported** values because the public inputs do not reproduce them under one consistent formula set.

## Resolved public-baseline items

The following audit items are resolved for the current GitHub baseline:

- one public source of truth: `lab/eve-ng/NetCore_SDN_Project.unl`;
- Warsaw/Madrid/Sevilla site mapping;
- public branch `site-id` and `system-ip` values;
- branch underlay subnets, next hops and transport colors;
- one Madrid WAN Edge and no Madrid ASAv in the exported lab;
- sanitized `.unl` startup payloads;
- sanitized canonical Edge/underlay/ASAv extracts;
- economic KPI reconciliation;
- historical-software/product-naming documentation.

## Remaining reproducibility limits

Remaining limitations include:

- complete canonical startup configs for SD-WAN Manager/vManage, Controller/vSmart and Validator/vBond are not available from the exported snapshot;
- the exact EVE-NG edition used for the historical lab has not been independently verified;
- genuine runtime control-plane/OMP/BFD/reachability captures are unavailable because the lab cannot currently be executed;
- the current public topology does not reproduce the thesis dual-transport Sevilla failover scenario;
- Cisco DNA Center / Catalyst Center, Cisco ISE and ENCS/NFVIS are not present as running nodes;
- API/NETCONF/YANG automation scripts are not part of the recovered defended-lab artifacts;
- the reviewed defense-presentation PDF has not yet been uploaded to the repository through a verified binary-safe path.

These gaps do **not** invalidate the thesis design. They define the boundary between defended research, preserved implementation artifacts and what is reproducible from the public repository today.

## Historical software / product naming

The lab preserves software and naming from the defended project, including Cisco SD-WAN 20.6.2, ASAv 9.9(1), `vManage`, `vBond`, `vSmart` and Cisco DNA Center terminology.

These versions/names are retained for traceability, not presented as current production recommendations. Current Cisco naming and lifecycle context are documented in [`HISTORICAL_SOFTWARE_COMPATIBILITY.md`](./HISTORICAL_SOFTWARE_COMPATIBILITY.md).

## Academic case-study notice

The organization, incident narrative, financial figures and internal-document style material in the thesis are presented as an **academic enterprise case study**. This repository is an educational engineering portfolio and is not an official corporate repository or a publication of confidential company records.
