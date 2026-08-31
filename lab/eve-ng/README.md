# EVE-NG Laboratory

This directory contains the exported EVE-NG snapshot used as the practical Cisco SD-WAN laboratory for the portfolio.

## Included

- `NetCore_SDN_Project.unl` - sanitized EVE-NG topology definition;
- `inventory.yaml` - machine-readable inventory derived from the published topology;
- `topology.png` - visual topology snapshot.

## Source of truth

The `.unl` file is the primary reference for what is actually present in the published EVE-NG topology. The wider bachelor-thesis design includes additional technologies that are not all represented as running nodes in this export.

## Sanitization status

The public `.unl` has been rewritten to remove credential-bearing startup content while preserving the topology structure and the documented project baseline:

- Warsaw: system IP `1.1.1.5`, site `200`, WAN `10.255.0.6/30`, color `mpls`;
- Madrid: system IP `1.1.1.9`, site `300`, WAN `10.255.0.10/30`, color `biz-internet`;
- Sevilla: system IP `1.1.1.13`, site `400`, WAN `10.255.0.14/30`, color `public-internet`;
- organization: `NetCore_Solutions_2026`;
- Validator/vBond reference used by the Edge baseline: `192.168.1.3`.

Embedded local usernames, password hashes and ASAv enable-password hashes are not included in the public snapshot.

## Reproduction limitation

The topology still does not include complete embedded startup state for all SD-WAN controller components. Importing the `.unl` should therefore be treated as importing the documented topology and sanitized baseline, not as guaranteed one-click reconstruction of a fully operational controller fabric.

Cisco virtual appliance images are proprietary and are **not** included. To reproduce the lab, provide appropriately licensed images in your own EVE-NG installation.

Before treating a result as reproducible runtime evidence, see [`../../docs/IMPLEMENTATION_STATUS.md`](../../docs/IMPLEMENTATION_STATUS.md) and [`../../evidence/README.md`](../../evidence/README.md).
