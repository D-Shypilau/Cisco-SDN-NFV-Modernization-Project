# Historical Software Compatibility Note

This repository preserves the software versions and product names recovered from the defended academic laboratory. They are retained for **historical reproducibility and portfolio traceability**, not as a recommendation for a new production deployment.

## Versions preserved by the EVE-NG snapshot

The exported lab identifies the following main software/image families:

- Cisco SD-WAN / Viptela control and vEdge components: **20.6.2**;
- Cisco ASAv: **9.9(1)**;
- Cisco IOSv underlay image family: **15.9(3)M4**;
- Cisco IOSvL2 image family: `viosl2-adventerprisek9-m.ssa.high_iron_20200929`.

Cisco appliance images are proprietary and are intentionally not distributed in this repository.

## Cisco SD-WAN 20.6.x lifecycle

Cisco announced end-of-life milestones for SD-WAN Release 20.6.x. According to Cisco's official notice:

- end of software maintenance releases: **March 30, 2024**;
- end of vulnerability/security support: **September 30, 2024**;
- last date of support: **March 30, 2026**.

Therefore the project's **20.6.2** images must be treated as historical lab software. They are useful for understanding the defended topology and configuration syntax, but this repository does not recommend deploying 20.6.2 in a new production environment.

Official Cisco references:

- [Cisco SD-WAN Release 20.6.x release notes](https://www.cisco.com/c/en/us/td/docs/routers/sdwan/release/notes/vedge-20-6/sd-wan-rel-notes-20-6.html)
- [End-of-Sale and End-of-Life Announcement for SD-WAN Release 20.6.x](https://www.cisco.com/c/en/us/products/collateral/routers/sd-wan/viptela-software-release-20-6-v-eol.html)
- [Cisco Catalyst SD-WAN support/documentation landing page](https://www.cisco.com/c/en/us/support/routers/sd-wan/series.html)

## Product naming changes

The thesis and recovered lab use the historical names **Cisco SD-WAN**, **vManage**, **vBond** and **vSmart**.

Cisco's current documentation uses the Cisco Catalyst SD-WAN branding. Beginning with Cisco Catalyst SD-WAN Release **20.12.1** / IOS XE SD-WAN **17.12.1a**, Cisco documents these naming changes:

- `vManage` → **Cisco Catalyst SD-WAN Manager**;
- `vBond` → **Cisco Catalyst SD-WAN Validator**;
- `vSmart` → **Cisco Catalyst SD-WAN Controller**;
- Cisco SD-WAN → **Cisco Catalyst SD-WAN**.

The repository may use both old and current names when that improves traceability between the defended thesis and modern Cisco documentation.

Official reference:

- [Cisco Catalyst SD-WAN — Read Me First](https://www.cisco.com/c/en/us/td/docs/routers/sdwan/17-x/systems-interfaces/systems-interfaces-guide-17-x/read-me-first.html)

## Cisco DNA Center naming

The academic design uses the name **Cisco DNA Center**. Cisco documents the name change from Cisco DNA Center to **Catalyst Center** as a new/changed feature in **Catalyst Center 2.3.7.4**, while stating that the capability and functionality remain the same in that branding transition.

For historical sections, `Cisco DNA Center` is preserved. For current terminology, the repository uses `Cisco Catalyst Center (formerly Cisco DNA Center)` where useful.

Official reference:

- [Cisco Catalyst Center 2.3.7.x release notes](https://www.cisco.com/c/en/us/td/docs/cloud-systems-management/network-automation-and-management/catalyst-center/2-3-7/release_notes/b_cisco_catalyst_center_237_release_notes.html)

## ASAv 9.9 lifecycle

The EVE-NG snapshot uses **ASAv 9.9(1)**. Cisco's end-of-life notice for ASA/ASAv 9.9(x) lists **May 31, 2023** as the last date of support.

The ASAv version in this project is therefore retained only to match the recovered historical laboratory. It should not be interpreted as current security-software guidance.

Official reference:

- [Cisco ASA/ASAv 9.9(x) end-of-life announcement](https://www.cisco.com/c/en/us/products/collateral/security/asa-firepower-services/eos-eol-notice-c51-743169.pdf)

## Reproduction guidance

If reproducing the historical lab:

1. use only properly licensed Cisco images;
2. expect behavior, resource requirements and command output to differ across releases;
3. do not assume that a newer controller/Edge/ASAv image is a drop-in replacement for the versions captured by this `.unl`;
4. consult Cisco's current compatibility matrices and recommended-software guidance before combining versions;
5. treat the sanitized configs in `configs/canonical/` as documentation of this portfolio baseline, not as production-ready deployment templates.

No current-production upgrade path is claimed by this repository. A production design should be rebuilt and validated against currently supported Cisco releases, current compatibility matrices and the organization's own requirements.
