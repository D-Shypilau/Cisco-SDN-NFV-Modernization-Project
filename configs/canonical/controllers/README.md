# Controller Configuration Status

The exported EVE-NG topology contains these controller roles:

- `DE-FRA-MGMT-01` — vManage / SD-WAN Manager role;
- `DE-FRA-SMART-01` — vSmart / SD-WAN Controller role;
- `vBond` — vBond / SD-WAN Validator role.

However, the current `.unl` snapshot does **not** embed a complete reproducible startup configuration for these nodes:

- vManage/Manager: no embedded startup configuration;
- vSmart/Controller: no embedded startup configuration;
- vBond/Validator: embedded config record is effectively empty/incomplete.

For this reason, no fabricated "canonical" controller config is published here.

The older files in `../../snapshots/` are retained only for historical comparison. They use a different organization name, controller addressing and transport plan than the exported `.unl` baseline.

A future canonical controller set must be exported from the same running lab state that produces the verification evidence in `evidence/`.
