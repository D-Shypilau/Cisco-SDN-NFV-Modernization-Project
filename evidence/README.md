# Verification Evidence

This directory is reserved for publishable, reproducible evidence from the laboratory.

Planned evidence groups:

- `control-plane/` - controller reachability, control connections and OMP state;
- `connectivity/` - branch and endpoint reachability;
- `failover/` - BFD/SLA state and measured path changes;
- `security/` - firewall/segmentation validation that is actually implemented in the published lab;
- `ztp/` - onboarding timing and controller-side proof, if reproducible evidence is available.

Evidence rule:

```text
Claim -> Test method -> Raw result -> Calculation -> Conclusion
```

A thesis or presentation value is not automatically treated as a reproducible GitHub result. See [`../docs/IMPLEMENTATION_STATUS.md`](../docs/IMPLEMENTATION_STATUS.md).
