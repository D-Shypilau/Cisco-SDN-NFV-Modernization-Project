# Public Portfolio Publication Checklist

This checklist tracks the work required before publishing a clean `v1.0` portfolio release of the bachelor thesis engineering project.

> **Publication rule:** the full bachelor thesis text/PDF is private and must **not** be committed to this public repository. The thesis is used only as the internal source for validating the public engineering materials.

## 1. Architecture consistency

- [x] Choose one final architecture as the source of truth for the public engineering project.
- [x] Reconcile the public README, EVE-NG `.unl`, machine-readable inventory and canonical configuration baseline.
- [x] Verify Frankfurt, Warsaw, Madrid and Sevilla naming in the public baseline.
- [x] Verify public `site-id` values.
- [x] Verify public `system-ip`, underlay IP addresses and transport colors for the branch Edge nodes.
- [x] Verify the actual number of Madrid WAN Edge and ASAv nodes in the exported `.unl`.

## 2. Software versions

- [ ] Record the exact EVE-NG edition used for the historical lab snapshot if it can be recovered reliably.
- [x] Record the Cisco SD-WAN image version visible in the exported topology (`20.6.2`).
- [x] Record the ASAv version visible in the exported topology (`9.9.1`).
- [x] Add a compatibility note explaining that historical lab images are preserved for academic reproducibility rather than recommended as current production software.
- [x] Document current Cisco Catalyst SD-WAN / Catalyst Center naming alongside historical project terminology.

See [`HISTORICAL_SOFTWARE_COMPATIBILITY.md`](./HISTORICAL_SOFTWARE_COMPATIBILITY.md).

## 3. Configuration publication

- [x] Build sanitized canonical branch/underlay/security extracts from the same public EVE-NG baseline.
- [x] Remove password hashes, credentials and secret-bearing startup content from the public `.unl`.
- [x] Add Madrid configuration baseline.
- [x] Organize canonical configurations into controller/edge/security/underlay sections.
- [x] Update configuration documentation to reflect completed `.unl` sanitization.
- [ ] Replace the controller limitation with real same-state exports only if a runnable lab becomes available.

## 4. Verification evidence

The repository contains a verification runbook and clearly separated simulated/expected examples.

- [x] document expected control connections;
- [x] document expected OMP/TLOC state;
- [x] document expected BFD state;
- [x] document expected underlay state;
- [x] mark all generated examples as `SIMULATED — NOT CAPTURED FROM A RUNNING LAB`;
- [ ] collect genuine runtime captures if the lab becomes executable in the future;
- [ ] reproduce failover/security/ZTP measurements only if the required topology and test conditions become available.

Each measured headline metric should remain traceable as:

```text
Claim → Test method → Raw result → Calculation → Conclusion
```

## 5. Thesis-derived metrics

The defense materials report technical values including 850 ms failover, 3.8 s security isolation and 22-minute ZTP onboarding. These remain explicitly **thesis-reported** because the current public snapshot does not reproduce their complete test conditions.

Economic reconciliation is documented in [`../analytics/ECONOMIC_MODEL.md`](../analytics/ECONOMIC_MODEL.md).

- [x] distinguish measured/simulated technical evidence from thesis-reported values;
- [x] reconcile OPEX arithmetic using €430,000 and €262,000 annual operating-cost inputs;
- [x] reconcile annual economic effect using the explicit €168,000 OPEX saving plus €247,000 avoided-loss assumption;
- [x] define one public ROI formula and calculate the resulting range;
- [x] define one public simple-payback calculation and calculate the resulting range;
- [x] retain €422,000/year, 28% ROI and 1.4-year payback only as legacy thesis-reported values;
- [ ] define the deployment-time baseline explicitly before publishing any deployment acceleration factor;
- [x] avoid presenting academic case-study figures as generic Cisco product benchmarks.

## 6. Presentation publication

Public structure:

```text
docs/
└── presentation/
    ├── NetCore_SDN_NFV_Public_GitHub_Final.pdf
    └── README.md
```

- [x] Do **not** publish the full thesis PDF, source document or complete thesis text.
- [x] Use the private thesis only to verify repository documentation and evidence.
- [x] Remove the old oversized presentation PPTX from the cleaned public structure.
- [x] Prepare and visually review the final public 11-page PDF locally.
- [x] Remove/correct visible placeholder, numbering and outdated KPI artifacts in the public presentation.
- [x] Upload the reviewed PDF through GitHub's normal binary-safe web upload.
- [x] Verify the GitHub PDF size (`2,773,845` bytes) and Git blob SHA-1 (`66d3cc13f194733969b9760fad43fdee958b41fd`) against the locally reviewed PDF.

## 7. README / portfolio quality

- [x] Introduce the bachelor thesis engineering project clearly.
- [x] Show the network topology near the top.
- [x] Explain the current repository directories.
- [x] Add responsible-use and proprietary-image notice.
- [x] State that the full thesis is not part of the public repository.
- [x] Document the reconciled economic model and distinguish legacy thesis values.
- [x] Document limitations of the virtual lab.
- [x] Add historical software compatibility/lifecycle guidance.
- [x] Complete the final content/navigation review for the current Markdown structure.
- [x] Remove stale references to the old `topology/` layout and pre-sanitization status from current documentation.
- [x] Complete and record the pre-merge repository review in [`PRE_MERGE_REVIEW.md`](./PRE_MERGE_REVIEW.md).

## 8. Optional engineering improvements

These are useful portfolio enhancements but should not be presented as defended thesis work unless they were actually part of it:

- [ ] Python scripts using Cisco SD-WAN Manager APIs;
- [ ] configuration consistency checker;
- [ ] GitHub Actions validation for Markdown/XML/secrets;
- [ ] Ansible-based configuration/verification helpers;
- [x] machine-readable inventory (`inventory.yaml`).

## 9. Final release

Before creating `v1.0`:

- [x] no thesis PDF/full text in the repository;
- [x] no known credential hashes or secrets in the public `.unl`/canonical configuration baseline;
- [x] one documented public topology baseline;
- [x] public presentation content reviewed locally;
- [x] public presentation PDF present in GitHub and binary identity verified against the reviewed local PDF;
- [x] economic claims traceable to the reconciled model or explicitly labeled legacy/thesis-reported;
- [x] current Markdown navigation/content reviewed against the cleaned repository tree;
- [x] README structure matches the current branch contents;
- [x] keep `DNA Center` terminology in the GitHub repository description/project framing;
- [x] pre-merge content/security review completed;
- [ ] move PR #1 out of Draft only after explicit user approval;
- [ ] merge into `main` only after explicit user approval;
- [ ] tag the reviewed state as `v1.0-thesis-portfolio` after the approved merge.
