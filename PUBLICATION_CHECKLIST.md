# Public Portfolio Publication Checklist

This checklist tracks the work required before publishing a clean `v1.0` portfolio release of the bachelor thesis project.

## 1. Architecture consistency

- [ ] Choose one final architecture as the source of truth.
- [ ] Reconcile `README.md`, `topology/NetCore_SDN_Project.unl`, `topology/nodes_description.txt`, configuration exports, thesis text and presentation.
- [ ] Verify that Frankfurt, Warsaw, Madrid and Sevilla use the same names everywhere.
- [ ] Verify that all `site-id` values are consistent everywhere.
- [ ] Verify all `system-ip`, underlay IP addresses and transport colors.
- [ ] Verify the actual number of Madrid WAN Edge and ASAv nodes.

## 2. Software versions

- [ ] Record the exact EVE-NG edition used for the final lab snapshot.
- [ ] Record exact Cisco SD-WAN image versions used by every node.
- [ ] Record exact ASAv version.
- [ ] Explain in the documentation when legacy lab images are used for educational compatibility.

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

## 5. Thesis metrics

The defense presentation currently reports:

- ROI: 28%;
- payback: 1.4 years;
- OPEX reduction: 40%;
- failover: 850 ms;
- threat blocking: 3.8 s;
- ZTP deployment: 0.5 h;
- deployment baseline: 120 h;
- time saving: 99.6%;
- annual economic effect: €422,000.

Before final publication:

- [ ] link every value to its calculation/test source;
- [ ] distinguish measured laboratory values from calculated business-case values;
- [ ] avoid presenting case-study figures as generic vendor benchmarks.

## 6. Thesis and presentation

Recommended final structure:

```text
docs/
├── thesis/
│   ├── Bachelor_Thesis_Dzmitry_Shypilau.pdf
│   └── README.md
└── presentation/
    ├── Thesis_Defense_Presentation.pdf
    ├── Thesis_Defense_Presentation.odp
    └── README.md
```

- [ ] Use ASCII/English file names for public GitHub paths.
- [ ] Keep editable source (`.odt` / `.odp`) when useful.
- [ ] Add PDF versions so documents can be opened easily in a browser.
- [ ] Keep original university formatting intact in the PDF thesis.

## 7. README / portfolio quality

- [x] Introduce the thesis and project purpose clearly.
- [x] Show the network topology near the top.
- [x] Explain repository directories.
- [x] Add responsible-use and proprietary-image notice.
- [ ] Add screenshots of key verification results.
- [ ] Add a final `Reproduction` guide once configs are reconciled.
- [ ] Add a short section describing limitations of the virtual lab.

## 8. Optional engineering improvements

These are useful portfolio enhancements but should not be presented as thesis work unless they were actually part of the defended project:

- [ ] Python scripts using Cisco SD-WAN Manager APIs;
- [ ] configuration consistency checker;
- [ ] GitHub Actions validation for Markdown/XML/secrets;
- [ ] Ansible-based configuration/verification helpers;
- [ ] machine-readable inventory (`inventory.yaml`).

## 9. Final release

Before creating `v1.0`:

- [ ] no credentials or sensitive material;
- [ ] one consistent topology;
- [ ] thesis PDF present;
- [ ] presentation PDF present;
- [ ] claims traceable to evidence;
- [ ] all links in README work;
- [ ] repository description matches actual content;
- [ ] tag the reviewed state as `v1.0-thesis-portfolio`.
