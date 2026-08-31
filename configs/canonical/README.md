# Canonical Public Configuration Baseline

This directory contains the **sanitized public configuration baseline** derived from the embedded startup state of `lab/eve-ng/NetCore_SDN_Project.unl`.

## Meaning of "canonical"

For this repository, canonical means that site IDs, system IPs, organization name, transport addressing and transport colors follow the current exported `.unl` snapshot.

It does **not** mean that the repository can already rebuild the complete SD-WAN control plane from scratch. The exported lab does not contain complete embedded startup configurations for vManage/SD-WAN Manager, vSmart/SD-WAN Controller or vBond/Validator.

## Sanitization

The public extracts intentionally omit:

- local usernames;
- password hashes;
- enable password hashes;
- certificates and private keys;
- device-specific secrets;
- unrelated generated/default configuration.

The files preserve the network parameters required to document the public laboratory baseline.

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

Older, conflicting text exports remain under `../snapshots/` for provenance only.

## Important limitation

The original `.unl` currently embeds credential hashes inside several startup-config records. These hashes are **not copied into this directory**. A sanitized/re-exported `.unl` is still required before the final public `v1.0` release.
