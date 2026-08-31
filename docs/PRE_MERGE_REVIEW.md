# Pre-Merge Review — PR #1

This review records the final repository check for branch `portfolio-cleanup` before any merge into `main`.

## Review result

**Status: PASS — READY FOR EXPLICIT USER APPROVAL**

The cleaned engineering content is internally consistent enough for final review. The previously remaining publication blocker — the final presentation PDF — has now been uploaded to GitHub through the normal web interface and binary-verified against the locally reviewed file.

PR #1 remains **Draft** and unmerged only because moving it out of Draft / merging requires the user's explicit approval.

## Branch / merge baseline

At review time:

- base branch: `main`;
- working branch: `portfolio-cleanup`;
- no merge has been performed;
- no final release tag has been created.

## Repository structure

Reviewed current public layout:

```text
README.md
SECURITY.md
analytics/
configs/
docs/
evidence/
lab/eve-ng/
```

The former monolithic `NetCore_SDN_Project/` presentation/topology layout is removed by the PR. Historical configuration exports are intentionally preserved under `configs/snapshots/` and are documented as non-canonical.

## Security review

Checked publication controls:

- full bachelor thesis PDF/source/text is not part of the cleaned public structure;
- proprietary Cisco virtual appliance images are not included;
- `.gitignore` blocks common image, key, certificate, environment and credential-file patterns;
- canonical configuration extracts intentionally omit usernames, password hashes, private keys and certificates;
- embedded startup-config payloads in the public `lab/eve-ng/NetCore_SDN_Project.unl` were decoded and checked for common secret-bearing markers;
- no `password`, `secret`, `username`, `private-key`, `enable password` or equivalent credential marker remains in the sanitized embedded payloads reviewed;
- historical text snapshots reviewed during the audit contain old lab addressing/configuration values but no published authentication credentials.

The historical snapshots remain non-canonical because their organization name, addressing/site mapping and transport values differ from the current public `.unl` baseline.

## Architecture consistency review

The public source-of-truth chain is now:

```text
sanitized .unl
→ inventory.yaml
→ ARCHITECTURE_BASELINE.md
→ configs/canonical/
→ verification / simulated evidence
```

Canonical branch baseline remains:

- Warsaw: system IP `1.1.1.5`, site `200`, WAN `10.255.0.6/30`, color `mpls`;
- Madrid: system IP `1.1.1.9`, site `300`, WAN `10.255.0.10/30`, color `biz-internet`;
- Sevilla: system IP `1.1.1.13`, site `400`, WAN `10.255.0.14/30`, color `public-internet`;
- organization: `NetCore_Solutions_2026`;
- Edge Validator/vBond reference: `192.168.1.3`.

Complete same-state controller startup configurations are still unavailable and are intentionally not fabricated.

## Evidence review

The repository correctly separates:

- runtime evidence — not currently available;
- simulated / expected evidence — explicitly marked `SIMULATED — NOT CAPTURED FROM A RUNNING LAB`;
- thesis-reported results — historical defended metrics not reproduced by the current public topology.

The public repository does not claim that simulated CLI output is raw device evidence.

The `850 ms` failover, `22 min` ZTP and `3.8 s` security-isolation values remain thesis-reported because the required reproducible test conditions are not present in the current public lab snapshot.

## Economic KPI review

The public model is internally reconciled in `analytics/ECONOMIC_MODEL.md`:

- annual OPEX baseline: `€430,000`;
- optimized annual OPEX: `€262,000`;
- annual OPEX saving: `€168,000`;
- OPEX reduction: `39.1%` (`~40%` rounded);
- avoided-loss assumption: `€247,000/year`;
- gross annual economic effect: `€415,000/year`;
- investment range: `€180,000–€220,000`;
- simple full-effect payback: `0.43–0.53 years`;
- simple first-year ROI: `88.6%–130.6%`.

Legacy thesis values `€422,000/year`, `28% ROI` and `1.4-year payback` are retained only when explicitly labeled historical/thesis-reported.

## Software compatibility review

Historical project software is documented rather than presented as current production guidance. `docs/HISTORICAL_SOFTWARE_COMPATIBILITY.md` records the recovered Cisco SD-WAN 20.6.2 and ASAv 9.9(1) context.

The repository intentionally keeps **Cisco DNA Center** terminology for the defended academic project.

## Presentation review

The final public deck is published at:

```text
docs/presentation/NetCore_SDN_NFV_Public_GitHub_Final.pdf
```

Validation completed:

- PDF format: PDF 1.7;
- pages: 11;
- GitHub size: `2,773,845` bytes;
- Git blob SHA-1: `66d3cc13f194733969b9760fad43fdee958b41fd`;
- local reviewed file has the same size and Git blob SHA-1;
- all pages were rendered for visual inspection before upload;
- visible placeholder/page-number artifacts were corrected;
- economic KPI slide is aligned with the reconciled model;
- thesis-only technical metrics are labeled appropriately;
- Cisco DNA Center terminology is retained.

Because Git computes the blob hash from the exact file bytes, the matching Git blob SHA-1 proves the GitHub PDF is byte-for-byte identical to the locally reviewed final PDF.

## Remaining release items

The only release-gating actions left are procedural:

1. explicit user approval to move PR #1 out of Draft;
2. explicit user approval to merge `portfolio-cleanup` into `main`;
3. create `v1.0-thesis-portfolio` after the reviewed merge.

Optional / future items such as exact EVE-NG edition recovery and genuine runtime evidence remain documented limitations, not merge blockers.

## Recommendation

The repository is ready for the user's explicit approval to move PR #1 from Draft to Ready for review. Do not merge automatically; merge only after a separate explicit approval.
