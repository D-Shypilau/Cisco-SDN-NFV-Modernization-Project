# Configuration Snapshots

The files under `snapshots/` are preserved configuration exports from the original project repository.

They are intentionally published as **snapshots**, not as a guaranteed single synchronized running configuration set. During audit, differences were found between these text exports and startup parameters embedded in the EVE-NG `.unl` snapshot (organization name, site IDs, addressing and site mapping).

Do not merge or deploy these configurations blindly. The final portfolio release should only promote a configuration into a canonical directory after it is verified against the same EVE-NG lab state.

See [`../docs/IMPLEMENTATION_STATUS.md`](../docs/IMPLEMENTATION_STATUS.md) for the reconciliation status.
