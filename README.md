# Cisco SD-WAN & NFV Network Modernization

**Bachelor Thesis Project / Выпускная квалификационная работа**  
**Research of SDN & NFV IT Technologies in Cisco Corporate Networks**

A portfolio-oriented case study of enterprise network modernization using **Cisco SD-WAN**, **software-defined networking (SDN)**, **network function virtualization (NFV)**, and an **EVE-NG digital twin**.

> The project combines architectural research, an enterprise modernization scenario, a virtual laboratory, device configurations, verification materials, economic analysis, and a defense presentation.

## Project Goal

The thesis develops and evaluates a modernization model for a geographically distributed enterprise network that is difficult to operate with a traditional device-by-device CLI approach.

The project focuses on five stages:

1. audit the existing network and identify operational weaknesses;
2. study SDN and NFV architectural principles;
3. design a target Cisco-based network model;
4. validate the proposed architecture in EVE-NG;
5. evaluate technical and economic efficiency.

## Architecture

The case study models four European locations:

- **DE-FRA — Frankfurt:** core and management/control infrastructure;
- **PL-WAR — Warsaw:** branch office;
- **ES-MAD — Madrid:** branch/regional site;
- **ES-SEV — Sevilla:** warehouse and WMS-related segment.

The EVE-NG laboratory includes Cisco SD-WAN components and virtual network/security functions such as **vManage**, **vSmart**, **vBond**, **vEdge**, and **ASAv**.

![EVE-NG network topology](./NetCore_SDN_Project/topology/EVE.png)

## Technology Areas

- **SDN:** centralized control, policy-driven networking, reduced dependence on per-device CLI administration;
- **Cisco SD-WAN / Viptela:** management, control and orchestration planes, WAN Edge connectivity and policy distribution;
- **NFV:** virtualization of routing and security functions;
- **EVE-NG:** virtual validation environment used as a digital twin of the proposed network;
- **Security:** segmentation, firewalling and Zero Trust concepts considered in the thesis;
- **Business analysis:** assessment of OPEX, ROI, payback period and downtime impact.

## Thesis Results

The thesis and defense materials report the following case-study outcomes:

- **ROI:** 28%;
- **payback period:** 1.4 years;
- **OPEX reduction:** approximately 40%;
- **SD-WAN failover result:** approximately 850 ms;
- **ZTP deployment scenario:** approximately 30 minutes per site;
- **estimated annual economic effect:** €422,000.

These figures belong to the thesis case study and its verification/economic-analysis materials. They should be interpreted together with the assumptions and test methodology documented in the project reports rather than as universal Cisco product benchmarks.

## Repository Contents

```text
Cisco-SDN-NFV-Modernization-Project/
├── README.md
├── LICENSE
└── NetCore_SDN_Project/
    ├── analytics/       # assessment, verification and efficiency reports
    ├── configs/         # SD-WAN component configuration snapshots
    ├── presentation/    # thesis defense presentation
    └── topology/        # EVE-NG lab, topology image and node description
```

### `analytics/`

Contains the analytical part of the project: infrastructure assessment, SDN/NFV functionality verification and efficiency metrics.

### `configs/`

Contains configuration snapshots for the SD-WAN control components and branch WAN Edge devices.

### `topology/`

Contains the EVE-NG `.unl` laboratory, topology diagram and a short description of the simulated nodes.

### `presentation/`

Contains the defense presentation associated with the bachelor thesis.

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
Compare observations with project reports
```

## Publication Status

This repository is being prepared as a clean public portfolio version of the bachelor thesis. During publication cleanup, the documentation, exported configurations and EVE-NG snapshot are being reconciled so that naming, site IDs, software versions and architecture descriptions refer to the same laboratory state.

For that reason, treat the thesis documents as the research narrative and the `.unl` file as the laboratory snapshot until the final tagged release is published.

## Responsible Use

This repository is intended for **education, research and authorized laboratory use**. Cisco software images and other proprietary software are intentionally not included.

## Author

**Dzmitry Shypilau**  
Bachelor Thesis: *Research of SDN & NFV IT Technologies in Cisco Corporate Networks*

## License

The repository source materials are published under the [MIT License](./LICENSE), except for third-party product names, trademarks and proprietary software referenced by the project.
