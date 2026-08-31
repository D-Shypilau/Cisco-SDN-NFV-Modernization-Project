# Public Portfolio Publication Checklist

This checklist tracks the work required before publishing a clean `v1.0` portfolio release of the bachelor thesis engineering project.

> **Publication rule:** the full bachelor thesis text/PDF is private and must **not** be committed to this public repository. The thesis is used only as the internal source for validating the public engineering materials.

## 1. Architecture consistency

- [ ] Choose one final architecture as the source of truth for the public engineering project.
- [ ] Reconcile `README.md`, `topology/NetCore_SDN_Project.unl`, `topology/nodes_description.txt`, configuration exports and defense presentation.
- [ ] Verify that Frankfurt, Warsaw, Madrid and Sevilla use the same names everywhere.
- [ ] Verify that all `site-id` values are consistent everywhere.
- [ ] Verify all `system-ip`, underlay IP addresses and transport colors.
- [ ] Verify the actual number of Madrid WAN Edge and ASAv nodes.

## 2. Software versions

- [ ] Record the exact EVE-NG edition used for the final lab snapshot.
- [ ] Record exact Cisco SD-WAN image versions used by every node.
- [ ] Record exact ASAv version.
- [ ] Explain when legacy lab images are used for educational compatibility.

## 3. Configuration publication

- [ ] Export configurations from the same final EVE-NG snapshot.
- [ ] Remove or redact password hashes, credentials, tokens and private keys.
- [ ] Add missing Madrid configuration exports if Madrid is part of the final topology.
- [ ] Organize configurations into `controllers/`, `edges/` and `security/`.

## 4. Verification evidence

Create a human-readable `evidence/` directory containing, where available:

- [ ] control connections;
- [ ] OMP peer / route verification;
- [ ] BFD state;
- [ ] branch reachability tests;
- [ ] failover measurements;
- [ ] policy verification;
- [ ] WMS/segmentation validation;
- [ ] ASAv/security validation;
- [ ] ZTP/deployment timing evidence.

Each headline metric should be traceable as:

```text
Claim → Test method → Raw result → Calculation → Conclusion
```

## 5. Thesis-derived metrics

The defense materials report:

- ROI: 28%;
- payback: 1.4 years;
- OPEX reduction: 40%;
- failover: 850 ms;
- threat blocking: 3.8 s;
- ZTP deployment: measured 22 min / target <30 min;
- deployment baseline used in the thesis: up to 120 h;
- annual economic effect: approximately €422,000.

Before final publication:

- [ ] link every public value to a calculation/test source that can be published safely;
- [ ] distinguish measured laboratory values from calculated business-case values;
- [ ] reconcile ROI, payback and annual-savings assumptions into one financial model;
- [ ] define the deployment-time baseline explicitly before publishing an acceleration factor;
- [ ] avoid presenting academic case-study figures as generic Cisco product benchmarks.

## 6. Presentation publication

Recommended public structure:

```text
docs/
└── presentation/
    ├── Thesis_Defense_Presentation.pdf
    ├── Thesis_Defense_Presentation.odp
    └── README.md
```

- [ ] Do **not** publish the full thesis PDF, source document or complete thesis text.
- [ ] Use the private thesis only to verify the repository documentation and evidence.
- [ ] Use ASCII/English file names for public GitHub paths.
- [ ] Keep the editable presentation source (`.odp`) when useful.
- [ ] Add a PDF presentation so it can be opened easily in a browser.
- [ ] Remove broken placeholders, numbering artifacts and internal editing marks from the public presentation.

## 7. README / portfolio quality

- [x] Introduce the bachelor thesis engineering project clearly.
- [x] Show the network topology near the top.
- [x] Explain repository directories.
- [x] Add responsible-use and proprietary-image notice.
- [x] State that the full thesis is not part of the public repository.
- [ ] Add screenshots of key verification results.
- [ ] Add a final reproduction guide once configs are reconciled.
- [ ] Add a short section describing limitations of the virtual lab.

## 8. Optional engineering improvements

These are useful portfolio enhancements but should not be presented as defended thesis work unless they were actually part of it:

- [ ] Python scripts using Cisco SD-WAN Manager APIs;
- [ ] configuration consistency checker;
- [ ] GitHub Actions validation for Markdown/XML/secrets;
- [ ] Ansible-based configuration/verification helpers;
- [ ] machine-readable inventory (`inventory.yaml`).

## 9. Final release

Before creating `v1.0`:

- [ ] no thesis PDF/full text in the repository;
- [ ] no credentials or sensitive material;
- [ ] one consistent topology;
- [ ] public presentation reviewed and present;
- [ ] claims traceable to publishable evidence;
- [ ] all links in README work;
- [ ] repository description matches actual content;
- [ ] tag the reviewed state as `v1.0-thesis-portfolio`.
