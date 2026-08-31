# Verification Evidence

This directory separates **real reproducible evidence** from **simulated/expected evidence**.

## Evidence types

### Runtime evidence

Reserved for output captured from a running laboratory:

- `control-plane/` - controller reachability, control connections and OMP state;
- `connectivity/` - branch and endpoint reachability;
- `failover/` - BFD/SLA state and measured path changes;
- `security/` - implemented firewall/segmentation validation;
- `ztp/` - onboarding timing and controller-side proof.

### Simulated evidence

`simulated/` contains expected command outputs generated from the published `.unl` baseline because the laboratory is currently unavailable for execution.

Every simulated file is explicitly marked:

```text
SIMULATED — NOT CAPTURED FROM A RUNNING LAB
```

Simulated outputs are useful for architecture review and portfolio explanation, but they are **not measured laboratory evidence**.

## Evidence rule

```text
Claim -> Test method -> Raw result -> Calculation -> Conclusion
```

For simulated material, the equivalent rule is:

```text
Expected state -> Source baseline -> Simulated output -> Limitation
```

A thesis or presentation value is not automatically treated as a reproducible GitHub result. See [`../docs/IMPLEMENTATION_STATUS.md`](../docs/IMPLEMENTATION_STATUS.md) and [`simulated/limitations/project_claims_status.md`](./simulated/limitations/project_claims_status.md).
