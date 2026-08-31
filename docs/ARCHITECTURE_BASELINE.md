# Exported Lab Architecture Baseline

This document defines the **public technical baseline** for the exported EVE-NG laboratory.

The source of truth for this baseline is:

```text
lab/eve-ng/NetCore_SDN_Project.unl
```

The private thesis remains useful for checking research intent and defended scope, but it is **not** used to overwrite facts present in the exported laboratory file.

## Baseline principle

For the public repository:

```text
.unl exported state
      ↓
machine-readable inventory
      ↓
documentation
      ↓
verified/sanitized configs
      ↓
evidence
```

If an older text configuration, presentation statement or narrative conflicts with the `.unl`, the conflict is documented until it can be reproduced and resolved from a final lab state.

## Sites in the exported snapshot

### Frankfurt

Published nodes:

- `DE-FRA-CORE-01` — core/switching role;
- `DE-FRA-FW-01` — ASAv security VNF;
- `DE-FRA-MGMT-01` — SD-WAN management component;
- `DE-FRA-SMART-01` — SD-WAN control component;
- `vBond` — SD-WAN orchestration/validation component;
- `INTERNET-ISP` — simulated WAN/underlay provider node.

### Warsaw

- `PL-WAR-GW-01` — vEdge WAN Edge;
- `PL-WAR-VPC-01` — endpoint.

Embedded edge values in the exported snapshot:

- system IP: `1.1.1.5`;
- site ID: `200`;
- organization: `NetCore_Solutions_2026`;
- vBond address: `192.168.1.3`;
- WAN address: `10.255.0.6/30`;
- next hop: `10.255.0.5`;
- transport color: `mpls`.

### Madrid

- `ES-MAD-GW-01` — one vEdge WAN Edge;
- `ES-MAD-VPC-01` — endpoint.

Embedded edge values:

- system IP: `1.1.1.9`;
- site ID: `300`;
- organization: `NetCore_Solutions_2026`;
- vBond address: `192.168.1.3`;
- WAN address: `10.255.0.10/30`;
- next hop: `10.255.0.9`;
- transport color: `biz-internet`.

The current export contains **one** Madrid WAN Edge and **no Madrid ASAv**.

### Sevilla

- `ES-SEV-WHR-GW-01` — vEdge warehouse WAN Edge;
- `ES-SEV-VPC-WMS` — WMS endpoint;
- `ES-SEV-VPC-GUEST` — guest endpoint.

Embedded edge values:

- system IP: `1.1.1.13`;
- site ID: `400`;
- organization: `NetCore_Solutions_2026`;
- vBond address: `192.168.1.3`;
- WAN address: `10.255.0.14/30`;
- next hop: `10.255.0.13`;
- transport color: `public-internet`.

## Important differences from older snapshots / narrative

The repository previously contained text exports and descriptions that do not match this baseline. Important examples include:

- older organization names such as `NetCore-Solutions-GmbH`;
- a different vBond reference (`1.1.1.2`) in older text configs;
- different transport addressing;
- Madrid/Sevilla site-ID mapping differences;
- descriptions of two Madrid WAN Edges although the exported `.unl` contains one;
- descriptions of a Madrid ASAv although the exported `.unl` contains only the Frankfurt ASAv;
- claims of dual-transport branch failover although the current exported branch edges expose one ISP-facing transport path each.

These older files are retained under `configs/snapshots/` for provenance and comparison, not as a deployable configuration set.

## Controller configuration limitation

The exported `.unl` does not contain a complete reproducible startup configuration for every SD-WAN controller component. In particular, the management/control components are present as nodes, but their full startup state is not embedded consistently.

Therefore the public repository currently documents the topology snapshot but does not yet claim one-command reproduction of the complete SD-WAN control plane.

## Technology scope boundary

The exported lab does **not** contain dedicated nodes for:

- Cisco Catalyst Center / DNA Center;
- Cisco ISE;
- Cisco ENCS/NFVIS.

These technologies belong to the broader target architecture and defended research scope. They should not be described as running components of this particular exported `.unl` snapshot.

## Next verification target

The next canonical state should be backed by command evidence for:

1. controller/control connections;
2. OMP peer and route state;
3. BFD/app-route state;
4. Warsaw/Madrid/Sevilla reachability;
5. policy behavior;
6. controlled failover if a second transport is actually added and tested;
7. sanitized configuration exports from the same tested state.

Machine-readable details are maintained in [`../lab/eve-ng/inventory.yaml`](../lab/eve-ng/inventory.yaml).
