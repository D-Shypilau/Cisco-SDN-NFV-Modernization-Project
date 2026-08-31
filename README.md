# Cisco SD-WAN & NFV Network Modernization

**Bachelor Thesis Engineering Project / Выпускной инженерный проект**  
**Research of SDN & NFV IT Technologies in Cisco Corporate Networks**

A portfolio-oriented case study of enterprise network modernization using **Cisco SD-WAN**, **software-defined networking (SDN)**, **network function virtualization (NFV)**, and an **EVE-NG digital twin**.

> The repository publishes the engineering artifacts of the project: architecture, laboratory topology, configurations, verification material, analysis and defense presentation. **The full bachelor thesis text/PDF is intentionally not published here.**

## Project Goal

The project develops and evaluates a modernization model for a geographically distributed enterprise network that is difficult to operate with a traditional device-by-device CLI approach.

The work focuses on five stages:

1. audit the existing network and identify operational weaknesses;
2. study SDN and NFV architectural principles;
3. design a target Cisco-based network model;
4. validate the proposed architecture using logical simulation and EVE-NG;
5. evaluate technical and economic efficiency.

## Architecture

The case study models four key European locations:

- **DE-FRA — Frankfurt:** core and management/control infrastructure;
- **PL-WAR — Warsaw:** branch office;
- **ES-MAD — Madrid:** branch/regional site;
- **ES-SEV — Sevilla:** warehouse and WMS-related segment.

The exported EVE-NG laboratory includes Cisco SD-WAN components and virtual network/security functions such as **vManage**, **vSmart**, **vBond**, **vEdge**, and **ASAv**.

![EVE-NG network topology](./NetCore_SDN_Project/topology/EVE.png)

## Technology Areas

- **SDN:** centralized policy and reduced dependence on per-device CLI administration;
- **Cisco SD-WAN / Viptela:** management, control and orchestration planes, WAN Edge connectivity and policy distribution;
- **NFV:** virtualization of routing and security functions;
- **EVE-NG:** virtual validation environment used as a digital twin of the implemented lab segment;
- **Security:** segmentation, firewalling and Zero Trust concepts studied in the project;
- **Business analysis:** assessment of OPEX, ROI, payback period and downtime impact.

## Design vs. Implementation

The academic project is broader than the exported EVE-NG snapshot. Technologies such as Cisco DNA Center / Catalyst Center, Cisco ISE, SGT-based microsegmentation, ENCS/NFVIS, NETCONF/YANG and some Hybrid-WAN scenarios are part of the target design and research scope.

The public repository distinguishes between:

```text
Designed / researched
        ↓
Logically modeled
        ↓
Implemented in EVE-NG
        ↓
Measured / evidenced
```

See [`docs/IMPLEMENTATION_STATUS.md`](./docs/IMPLEMENTATION_STATUS.md) for the current implementation and evidence status.

## Reported Project Results

The defense materials report the following academic case-study outcomes:

- **ROI:** 28%;
- **payback period:** 1.4 years;
- **OPEX reduction:** approximately 40%;
- **SD-WAN failover result:** approximately 850 ms;
- **ZTP onboarding:** measured 22 minutes, with a project target below 30 minutes;
- **security isolation:** 3.8 seconds in the reported test scenario;
- **estimated annual economic effect:** approximately €422,000.

These values belong to the academic case study. Before the final portfolio release, public claims are being reconciled with reproducible laboratory evidence and a single consistent financial model. They must not be interpreted as generic Cisco product benchmarks.

## Repository Contents

```text
Cisco-SDN-NFV-Modernization-Project/
├── README.md
├── LICENSE
├── PUBLICATION_CHECKLIST.md
├── docs/
│   └── IMPLEMENTATION_STATUS.md
└── NetCore_SDN_Project/
    ├── analytics/       # assessment, verification and efficiency reports
    ├── configs/         # SD-WAN configuration snapshots
    ├── presentation/    # defense presentation
    └── topology/        # EVE-NG lab, topology image and node description
```

### `analytics/`

Analytical and verification materials used to support the engineering case study.

### `configs/`

Configuration snapshots for SD-WAN control components and branch WAN Edge devices.

### `topology/`

The EVE-NG `.unl` laboratory, topology diagram and node description.

### `presentation/`

The public defense presentation associated with the project.

## Reproducing the Lab

The repository provides the EVE-NG topology definition and configuration material, but **Cisco virtual appliance images are not distributed in this repository**. A user reproducing the lab must provide appropriately licensed Cisco images in their own EVE-NG environment.

Recommended validation workflow:

```text
Import EVE-NG topology
        ↓
Provide licensed Cisco images
        ↓
Start infrastructure and SD-WAN nodes
        ↓
Verify control connections and OMP
        ↓
Verify branch connectivity and policies
        ↓
Run failure / recovery tests
        ↓
Compare observations with published evidence
```

## Publication Scope

The **full bachelor thesis document, thesis PDF and complete thesis text are private and are not part of this public repository**.

The private thesis is used only as a source for checking that the public architecture, explanations, metrics and presentation are consistent with the defended project.

The public repository is intended to contain only material appropriate for an engineering portfolio:

- architecture and diagrams;
- laboratory topology;
- sanitized configurations;
- reproducible verification evidence;
- technical/economic summaries;
- defense presentation;
- implementation notes and limitations.

## Publication Status

This repository is being prepared as a clean public portfolio version of the bachelor thesis engineering project. Documentation, exported configurations and the EVE-NG snapshot are being reconciled so that naming, site IDs, software versions and architecture descriptions refer to the same laboratory state.

## Responsible Use

This repository is intended for **education, research and authorized laboratory use**. Cisco software images and other proprietary software are intentionally not included.

## Author

**Dzmitry Shypilau**  
Bachelor Thesis Engineering Project: *Research of SDN & NFV IT Technologies in Cisco Corporate Networks*

## License

The repository source materials are published under the [MIT License](./LICENSE), except for third-party product names, trademarks and proprietary software referenced by the project.
