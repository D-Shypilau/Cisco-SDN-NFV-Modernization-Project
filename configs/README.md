# Configuration Material

This directory separates historical configuration exports from the public canonical baseline.

## `snapshots/`

Preserved text exports from the original project repository. They are intentionally retained as **historical snapshots**, not as one synchronized running configuration set.

The audit found differences between these files and the startup parameters embedded in the EVE-NG `.unl` snapshot, including organization name, site IDs, addressing, transport colors and site mapping.

Do not deploy or merge these files blindly.

## `canonical/`

Sanitized public extracts aligned to the current exported EVE-NG baseline.

Current canonical material includes:

- Warsaw WAN Edge;
- Madrid WAN Edge;
- Sevilla warehouse WAN Edge;
- underlay ISP interfaces/routes;
- Frankfurt ASAv interface/routing baseline.

Controller configs are intentionally not fabricated: the current `.unl` does not contain complete embedded startup state for vManage/Manager, vSmart/Controller and vBond/Validator.

## Security note

The public `.unl` and `canonical/` baseline have been sanitized. Credential-bearing AAA/user content and the recovered ASAv enable-password hash are not included in the public baseline.

Historical text snapshots remain non-canonical and must still be reviewed before reuse. They are retained for provenance, not deployment.

## Version note

The recovered lab uses historical Cisco software, including SD-WAN 20.6.2 and ASAv 9.9(1). These versions are preserved for academic traceability rather than recommended as current production software. See [`../docs/HISTORICAL_SOFTWARE_COMPATIBILITY.md`](../docs/HISTORICAL_SOFTWARE_COMPATIBILITY.md).

See also:

- [`canonical/README.md`](./canonical/README.md)
- [`../docs/ARCHITECTURE_BASELINE.md`](../docs/ARCHITECTURE_BASELINE.md)
- [`../docs/IMPLEMENTATION_STATUS.md`](../docs/IMPLEMENTATION_STATUS.md)
