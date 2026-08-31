# EVE-NG Verification Runbook

This runbook defines the evidence to collect from one consistent running lab state before the repository can claim reproducible SD-WAN behavior.

Use the exact topology and addressing documented in `lab/eve-ng/inventory.yaml` and `docs/ARCHITECTURE_BASELINE.md`.

## Evidence rule

For every test, save:

```text
Claim
→ Preconditions
→ Command / test method
→ Raw output
→ Timestamp
→ Result
→ Conclusion
```

Do not edit command output except to redact secrets/tokens/certificates.

## 1. Device identity

Run on each WAN Edge:

```text
show system status
show running-config system
```

Confirm:

- hostname;
- system IP;
- site ID;
- organization name;
- vBond/Validator address.

Expected baseline:

```text
PL-WAR-GW-01      system-ip 1.1.1.5   site-id 200
ES-MAD-GW-01      system-ip 1.1.1.9   site-id 300
ES-SEV-WHR-GW-01  system-ip 1.1.1.13  site-id 400
organization-name NetCore_Solutions_2026
vbond             192.168.1.3
```

Save output under:

```text
evidence/control-plane/device-identity/
```

## 2. Control connections

On each WAN Edge:

```text
show control connections
show control connections-history
```

Goal: prove that the edge has established SD-WAN control connections to the available controller roles.

Record the peer type, system IP, site ID, local/remote color, state and uptime where present.

Save under:

```text
evidence/control-plane/control-connections/
```

## 3. OMP state

On WAN Edge / controller nodes where the command is supported:

```text
show omp peers
show omp routes
show omp tlocs
```

Goal: demonstrate OMP adjacency and route/TLOC exchange.

Save under:

```text
evidence/control-plane/omp/
```

## 4. BFD / transport state

On each WAN Edge:

```text
show bfd sessions
show bfd history
```

If application-aware routing statistics are configured and available:

```text
show app-route stats
```

Goal: document the transport path actually present in the published lab.

Important: the current public `.unl` exposes one ISP-facing transport for each branch edge. Do not claim dual-transport failover until a second transport is actually configured, visible and tested.

Save under:

```text
evidence/transport/bfd/
```

## 5. Underlay reachability

From the WAN Edge devices, test the corresponding ISP next hop:

```text
PL-WAR-GW-01:     ping 10.255.0.5
ES-MAD-GW-01:     ping 10.255.0.9
ES-SEV-WHR-GW-01: ping 10.255.0.13
```

On `INTERNET-ISP`:

```text
show ip interface brief
show ip route
```

Goal: demonstrate that the /30 underlay links match the canonical baseline.

Save under:

```text
evidence/transport/underlay/
```

## 6. Branch / service reachability

First record endpoint IP configuration, then run ICMP tests between only those service networks that are actually configured in the running snapshot.

For VPCS endpoints:

```text
show ip
ping <destination-ip>
```

Do not infer service VPN addressing from the thesis if it is absent from the running edge configuration.

Save under:

```text
evidence/reachability/
```

## 7. ASAv baseline

On `DE-FRA-FW-01`:

```text
show version
show interface ip brief
show route
show access-list
show nat
```

Goal: distinguish what the ASAv actually implements from security functions only proposed in the thesis.

Current embedded startup evidence confirms interfaces/routing but does not justify claiming Cisco ISE/SGT microsegmentation or a 3.8-second quarantine workflow.

Save under:

```text
evidence/security/asav/
```

## 8. Policy evidence

Before claiming a centralized SD-WAN policy, save both the configured policy and proof that it is active/applied.

Useful verification depends on the running controller state. At minimum collect:

```text
show running-config policy
show omp routes
```

and the relevant controller-side policy status/output available in the running release.

A policy definition in an old text snapshot alone is not evidence that it was activated in the exported lab.

Save under:

```text
evidence/policy/
```

## 9. Failover test — blocked until topology supports it

The thesis reports approximately 850 ms SD-WAN failover. The current exported `.unl` does not provide a reproducible two-transport Sevilla edge scenario.

Do not reproduce or publish the 850 ms value as a verified public-lab measurement until all of the following are true:

1. two independent transports are visible on the tested WAN Edge;
2. both transports have active TLOC/BFD state;
3. SLA/path policy is documented;
4. continuous traffic is running before failure;
5. one transport is deliberately degraded/disabled;
6. timestamps or packet-level output show detection and recovery;
7. the calculation method for 850 ms is preserved.

When implemented, save under:

```text
evidence/failover/
```

## 10. ZTP — separate thesis result from public reproduction

The thesis test protocol reports a 22-minute onboarding result. The current public repository does not yet contain sufficient onboarding evidence to reproduce that result.

Required future evidence:

- device state before onboarding;
- serial/chassis authorization state with sensitive identifiers redacted if needed;
- Validator/vBond contact;
- Manager/vManage onboarding state;
- template/config attachment;
- start/end timestamps;
- final control connection state.

Save under:

```text
evidence/ztp/
```

## 11. Security isolation — separate thesis result from public reproduction

The thesis reports a 3.8-second isolation scenario involving ISE/SGT concepts. Cisco ISE is not a node in the published `.unl` snapshot.

Therefore, keep 3.8 s labeled as a thesis-reported case-study result unless a separate reproducible ISE/SGT lab and raw evidence are added.

Save any future reproduction under:

```text
evidence/security/zero-trust/
```

## Final acceptance criteria

A result may be promoted from **reported** to **verified** only when:

- raw output exists;
- the topology/config state is known;
- the test method is documented;
- no secrets are exposed;
- another engineer could follow the same procedure;
- the conclusion is no stronger than the evidence supports.
