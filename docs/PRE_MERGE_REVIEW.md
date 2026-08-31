# Pre-Merge Review — PR #1

This review records the final repository check for branch `portfolio-cleanup` before any merge into `main`.

## Review result

**Status: PASS WITH ONE PUBLICATION BLOCKER**

The cleaned engineering content is internally consistent enough for review. The remaining publication blocker is the final presentation PDF: it has been prepared and visually reviewed locally, but is not yet committed because the available repository write path does not support a verified binary-safe upload.

PR #1 must remain **Draft** and unmerged until the presentation upload decision is completed.

## Branch / merge baseline

At review time:

- base branch: `main`;
- working branch: `portfolio-cleanup`;
- branch relationship: `portfolio-cleanup` is ahead of `main` and not behind it;
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

The repository intentionally keeps **Cisco DNA Center** terminology for the defended academic project. Current naming may be mentioned for context, but the public project description does not need to replace `DNA Center`.

## Presentation review

A final public deck has been prepared locally as:

```text
NetCore_SDN_NFV_Public_GitHub_Final.pdf
```

Local validation completed:

- PDF format: valid PDF 1.7;
- pages: 11;
- size: approximately 2.7 MB;
- all pages rendered for visual inspection;
- visible placeholder/page-number artifacts corrected;
- economic KPI slide aligned with the reconciled model;
- thesis-only technical metrics labeled appropriately;
- Cisco DNA Center terminology retained.

The PDF is **not yet in the repository**. Do not substitute a truncated base64/text upload for a binary-safe file transfer.

## Remaining release items

The following are not hidden defects; they are explicit remaining limitations or publication tasks:

1. upload the reviewed presentation PDF through a verified binary-safe GitHub path;
2. optionally recover the exact historical EVE-NG edition if a reliable source becomes available;
3. keep runtime-evidence items pending unless the lab becomes executable;
4. keep PR #1 Draft until the final publication decision;
5. merge and create `v1.0-thesis-portfolio` only after explicit approval.

## Recommendation

Do **not** merge yet. Once the final PDF is present and its GitHub blob size/openability are verified, perform one short final check of the presentation link and then the branch can be considered ready for the user's explicit merge approval.
