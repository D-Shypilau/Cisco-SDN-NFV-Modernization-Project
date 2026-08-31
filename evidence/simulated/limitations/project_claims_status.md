# Project Claims — Reproduction Status

> This file separates defended/project-reported values from what the current public EVE-NG snapshot can actually reproduce.

## Failover: ~850 ms

**Status:** THESIS-REPORTED / SIMULATED-NOT-TESTABLE

The current exported `.unl` gives each branch WAN Edge one visible ISP-facing transport path. A same-site MPLS/Internet/LTE failover measurement cannot be reproduced from that topology without adding a second transport and defining the failure method/timers.

Therefore no synthetic raw log is generated that claims an 850 ms measured switchover.

## ZTP onboarding: 22 min / target <30 min

**Status:** THESIS-REPORTED / SIMULATED-NOT-TESTABLE

The current `.unl` contains embedded startup configurations on the WAN Edge nodes and does not include a complete controller onboarding evidence trail. This does not constitute a reproducible zero-touch provisioning test.

Therefore `22 min` remains a project-reported value, not runtime evidence from the public lab.

## Security isolation: 3.8 s

**Status:** THESIS-REPORTED / SIMULATED-NOT-TESTABLE

The exported lab contains a Frankfurt ASAv and endpoint roles, but no Cisco ISE node, no demonstrated SGT enforcement path and no raw timed isolation event. The embedded ASAv state is largely baseline/default configuration and does not prove the defended Zero Trust timing scenario.

Therefore `3.8 s` is not generated as a fake command result.

## OPEX reduction: ~40%

**Status:** THESIS-REPORTED / BUSINESS-MODEL VALUE

This is an economic/model result, not a device-command result. It should be supported by a consistent cost model rather than network CLI output.

## ROI: 28% and payback: 1.4 years

**Status:** THESIS-REPORTED / RECONCILIATION REQUIRED

These values require one consistent cash-flow model before final release because other project figures (investment range, avoided loss and annual benefit) can imply materially different payback periods depending on which assumptions are used.

## Annual economic effect: ~EUR 422,000

**Status:** THESIS-REPORTED / CALCULATED VALUE

This value is preserved as part of the defended case study, but should be presented as a business-case calculation rather than measured network telemetry.

## What is safe to show as simulated expected state

The repository can show clearly labeled expected-state examples for:

- ISP/underlay interfaces and routes;
- WAN Edge system/site/transport identity;
- expected vSmart/vManage control connections;
- expected OMP peer/TLOC state;
- expected BFD session topology.

Those examples are contained under `evidence/simulated/` and are explicitly not raw captures.
