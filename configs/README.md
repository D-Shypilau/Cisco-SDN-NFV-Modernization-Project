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

Credential hashes discovered inside the embedded `.unl` startup configuration are omitted from `canonical/`. Before the final public `v1.0` release, the `.unl` itself still needs to be sanitized/re-exported so credential hashes are not retained inside its base64 configuration records.

See:

- [`canonical/README.md`](./canonical/README.md)
- [`../docs/ARCHITECTURE_BASELINE.md`](../docs/ARCHITECTURE_BASELINE.md)
- [`../docs/IMPLEMENTATION_STATUS.md`](../docs/IMPLEMENTATION_STATUS.md)
