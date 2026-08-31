# Canonical Public Configuration Baseline

This directory contains the **sanitized public configuration baseline** aligned with `lab/eve-ng/NetCore_SDN_Project.unl`.

## Meaning of "canonical"

For this repository, canonical means that site IDs, system IPs, organization name, transport addressing and transport colors follow the current exported `.unl` snapshot.

It does **not** mean that the repository can rebuild the complete SD-WAN control plane from scratch. The exported lab still does not contain complete embedded startup configurations for SD-WAN Manager/vManage, SD-WAN Controller/vSmart or Validator/vBond.

## Sanitization

The public extracts intentionally omit:

- local usernames;
- password hashes;
- enable password hashes;
- certificates and private keys;
- device-specific secrets;
- unrelated generated/default configuration.

The EVE-NG `.unl` itself has also been sanitized: the topology, node identities, interfaces and documented network parameters are preserved, while embedded startup configuration was rewritten without credential material.

## Layout

```text
canonical/
├── controllers/
│   └── README.md
├── edges/
│   ├── PL-WAR-GW-01.conf
│   ├── ES-MAD-GW-01.conf
│   └── ES-SEV-WHR-GW-01.conf
├── security/
│   └── DE-FRA-FW-01.conf
└── underlay/
    └── INTERNET-ISP.conf
```

Older, conflicting text exports remain under `../snapshots/` for provenance only and should not be treated as deployable canonical configuration.

## Remaining limitation

Controller startup state is still incomplete in the exported lab. The sanitized `.unl` therefore documents a safe portfolio snapshot, not a one-click fully operational controller environment.
