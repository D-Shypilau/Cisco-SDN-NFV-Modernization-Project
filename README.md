# Cisco SD-WAN & NFV Network Modernization

**Bachelor Thesis Engineering Project / Выпускной инженерный проект**  
**Research of SDN & NFV IT Technologies in Cisco Corporate Networks**

A portfolio-oriented enterprise network modernization case study built around **Cisco SD-WAN**, **SDN**, **NFV**, logical simulation, and an **EVE-NG digital twin**.

> This public repository contains the engineering artifacts of the project. **The full bachelor thesis text/PDF is intentionally private and is not published here.**

## Project Goal

The project evaluates how a geographically distributed enterprise network can move away from device-by-device CLI administration toward centralized policy, virtualization and automated WAN operations.

The engineering workflow is:

1. identify operational and architectural weaknesses;
2. design a Cisco-based SDN/NFV target architecture;
3. validate addressing, routing, segmentation and resiliency concepts;
4. build a practical Cisco SD-WAN laboratory in EVE-NG;
5. compare the proposed approach using technical and economic KPIs.

## Architecture

The academic case study focuses on four key European locations:

- **DE-FRA - Frankfurt:** core and management/control infrastructure;
- **PL-WAR - Warsaw:** branch office;
- **ES-MAD - Madrid:** regional site;
- **ES-SEV - Sevilla:** warehouse / WMS scenario.

The exported EVE-NG snapshot contains Cisco SD-WAN/Viptela control components, WAN Edge nodes, an ASAv security VNF, ISP/underlay simulation and endpoint nodes.

![EVE-NG network topology](./lab/eve-ng/topology.png)

## Design vs. Implementation

The defended project is broader than the exported EVE-NG snapshot. Cisco Catalyst Center/DNA Center, Cisco ISE, SGT-based microsegmentation, ENCS/NFVIS, NETCONF/YANG, ZTP and Hybrid-WAN concepts are part of the wider design and research scope.

The public repository therefore uses four evidence levels:

```text
Designed / researched
        ↓
Logically modeled
        ↓
Implemented in EVE-NG
        ↓
Measured / evidenced
```

See [`docs/IMPLEMENTATION_STATUS.md`](./docs/IMPLEMENTATION_STATUS.md) for the current technical boundary.

## Project Results and Evidence Status

The defense materials report these academic case-study technical values:

- **SD-WAN failover:** ~850 ms;
- **ZTP onboarding:** 22 min measured / target <30 min;
- **security isolation scenario:** 3.8 s.

These remain **thesis-reported** values because the current public EVE-NG snapshot does not reproduce the exact test conditions needed to verify them. The repository therefore keeps generated expected-state examples separate from real runtime evidence.

### Reconciled economic model

The public portfolio now uses one internally consistent business-case calculation:

- traditional annual OPEX: **€430,000**;
- optimized annual OPEX: **€262,000**;
- annual OPEX saving: **€168,000**;
- OPEX reduction: **39.1% (~40% rounded)**;
- avoided-loss assumption: **€247,000/year**;
- reconciled gross annual economic effect: **€415,000/year**;
- implementation investment range: **€180,000–€220,000**;
- simple full-effect payback: **0.43–0.53 years**;
- simple first-year ROI: **88.6%–130.6%**.

The defense materials also report **€422,000/year**, **28% ROI** and **1.4-year payback**. Those values are preserved as **legacy thesis-reported figures**, but they are not mixed into the reconciled public model because the currently published inputs do not reproduce them under one consistent formula set.

See [`analytics/ECONOMIC_MODEL.md`](./analytics/ECONOMIC_MODEL.md) for the formulas, assumptions and reconciliation notes.

## Historical Software Compatibility

The recovered lab preserves historical software for traceability, including **Cisco SD-WAN 20.6.2** and **ASAv 9.9(1)**. These versions are documented to reproduce the defended academic environment and are **not** recommendations for a new production deployment.

The thesis also uses historical product names such as `vManage`, `vBond`, `vSmart` and `Cisco DNA Center`. Current Cisco terminology is documented alongside those names where useful.

See [`docs/HISTORICAL_SOFTWARE_COMPATIBILITY.md`](./docs/HISTORICAL_SOFTWARE_COMPATIBILITY.md) for lifecycle, naming and reproduction guidance.

## Repository Structure

```text
Cisco-SDN-NFV-Modernization-Project/
├── README.md
├── LICENSE
├── SECURITY.md
├── analytics/
│   ├── README.md
│   ├── ECONOMIC_MODEL.md
│   └── case-study/
├── configs/
│   ├── README.md
│   ├── canonical/
│   └── snapshots/
├── docs/
│   ├── ARCHITECTURE_BASELINE.md
│   ├── HISTORICAL_SOFTWARE_COMPATIBILITY.md
│   ├── IMPLEMENTATION_STATUS.md
│   ├── PUBLICATION_CHECKLIST.md
│   └── presentation/
│       └── README.md
├── evidence/
│   ├── README.md
│   ├── VERIFICATION_RUNBOOK.md
│   └── simulated/
└── lab/
    └── eve-ng/
        ├── README.md
        ├── inventory.yaml
        ├── NetCore_SDN_Project.unl
        └── topology.png
```

### `lab/eve-ng/`

The current sanitized EVE-NG laboratory snapshot, topology image and machine-readable inventory. Cisco appliance images are not distributed.

### `configs/canonical/`

Sanitized configuration extracts aligned with the public `.unl` baseline. Complete controller startup state is not claimed because it is not fully present in the exported lab.

### `configs/snapshots/`

Original text configuration exports preserved for analysis. They are explicitly marked as snapshots because the audit found parameter differences between some text exports and the `.unl` startup state.

### `evidence/`

Contains the verification runbook and clearly labeled simulated/expected outputs. Simulated files are not presented as captures from a running lab.

### `analytics/`

Supporting academic case-study documents and the reconciled economic model.

### `docs/presentation/`

Reserved for the public defense presentation. A verified PDF has been prepared locally; it will be committed only through a binary-safe upload path. The full thesis document is not included.

## Reproducing the Lab

Cisco virtual appliance images are proprietary and intentionally absent. A user reproducing this project must supply appropriately licensed images in their own EVE-NG environment.

Recommended validation flow:

```text
Import .unl topology
        ↓
Provide licensed Cisco images
        ↓
Start underlay and SD-WAN components
        ↓
Verify control connections / OMP / BFD
        ↓
Verify branch reachability and policies
        ↓
Run controlled failure tests where the topology supports them
        ↓
Save raw evidence in evidence/
```

Because the recovered controller startup state is incomplete, importing the `.unl` is not claimed to provide one-click reconstruction of a fully operational SD-WAN fabric.

## Publication Scope

**Not published:**

- full bachelor thesis PDF;
- thesis ODT/DOCX source;
- complete thesis text;
- Cisco proprietary software images;
- credentials, private keys or secrets.

**Published:**

- architecture and lab topology;
- sanitized EVE-NG definition;
- canonical sanitized configuration extracts;
- historical configuration snapshots with limitations documented;
- simulated/expected evidence clearly separated from runtime evidence;
- academic case-study summaries and economic model;
- implementation notes, software-compatibility note and limitations.

## Status

The repository is currently being cleaned and reconciled on the `portfolio-cleanup` branch before a reviewed `v1.0-thesis-portfolio` release. The architecture/configuration baseline, `.unl` sanitization, economic model and documentation/link audit are substantially complete. Remaining work focuses on presentation publication, the unrecovered exact EVE-NG edition and any future replacement of simulated evidence with genuine runtime captures if the lab becomes available.

## Responsible Use

For education, research and authorized laboratory use only. Cisco names and trademarks belong to their respective owners. Proprietary Cisco software is not distributed here.

## Author

**Dzmitry Shypilau**  
*Research of SDN & NFV IT Technologies in Cisco Corporate Networks*

## License

Repository-authored source materials are published under the [MIT License](./LICENSE), excluding third-party trademarks and proprietary software.
