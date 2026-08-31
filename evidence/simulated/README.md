# Simulated / Expected Evidence

> **SIMULATED — NOT CAPTURED FROM A RUNNING LAB**

The files in this directory are deterministic, project-consistent **expected outputs** created because the EVE-NG laboratory is currently unavailable for execution.

They are useful for:

- documenting the expected healthy state;
- showing what the verification commands should demonstrate;
- reviewing addressing, site IDs, transport colors and control-plane intent;
- preparing a portfolio without pretending that generated text is raw device evidence.

They must **not** be cited as measured laboratory results.

## Source hierarchy

The simulated evidence follows:

1. `lab/eve-ng/NetCore_SDN_Project.unl`;
2. `lab/eve-ng/inventory.yaml`;
3. `configs/canonical/`;
4. thesis/presentation values only when explicitly labeled as thesis-reported rather than reproduced.

## Controller assumptions

The exported `.unl` does not embed complete controller startup configurations. Where a controller identity is needed for an expected-state example, this directory uses the project reference identities:

- SD-WAN Manager / vManage: `1.1.1.1`;
- SD-WAN Controller / vSmart: `1.1.1.3`;
- Validator / vBond service address referenced by the Edge baseline: `192.168.1.3`.

Those controller values are **scenario assumptions**, not recovered runtime evidence.

## Evidence status labels

- `SIMULATED-PASS` — expected healthy outcome based on the modeled design;
- `SIMULATED-NOT-TESTABLE` — the published topology/configuration does not contain enough implementation to perform the claimed test;
- `THESIS-REPORTED` — value reported by the defended project but not reproduced by the current public lab.

The final release should replace these files with real captures if the lab becomes runnable.
