<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
DRAFT · not yet published · subject to legal review
-->

# Licensing

Eiraman is made of three kinds of material, each under its own licence. The Eiraman name and logo are not licensed by any of them; see [TRADEMARK.md](TRADEMARK.md).

| What | Where (repository or path) | Licence | SPDX identifier |
|---|---|---|---|
| Eiraman Guide, its translations and texts derived from it | `guide/`, `framework/` | Creative Commons Attribution-ShareAlike 4.0 International | `CC-BY-SA-4.0` |
| Role Profiles: `PROFILO.md`, `profilo.json`, `FAMIGLIA.md`, `_modello/`, `_seniority/`, registry `README.md` | `role-profiles/` | Creative Commons Attribution 4.0 International | `CC-BY-4.0` |
| Code: validators, profile tools, Manager View, CLI, site generator, CI templates | `tools/`, `site/` (code) | Apache License 2.0 | `Apache-2.0` |
| Website text (currently `site/generator/content.py`) | `site/` | Creative Commons Attribution-ShareAlike 4.0 International, until the text is separated from the code | `CC-BY-SA-4.0` |
| Community documents: governance, contributing, code of conduct, case studies | `community/`, `.github/` | Creative Commons Attribution 4.0 International *(proposal, to be confirmed)* | `CC-BY-4.0` |
| Historical Italian specification 0.3, non-normative, superseded by the Eiraman Guide | `guide/history/` | Creative Commons Attribution-ShareAlike 4.0 International (earlier copies remain under CC BY-NC-ND 4.0, see "Licence transition") | `CC-BY-SA-4.0` |
| Eiraman name, logo and visual identity | `site/brand/` (provenance in `site/brand/PROVENANCE.md`) | Not licensed by any of the licences above: trademark, governed by [TRADEMARK.md](TRADEMARK.md) | `LicenseRef-Eiraman-Trademark` |

Every file states its own licence in an SPDX header or in `REUSE.toml`, following the [REUSE Specification 3.3](https://reuse.software/spec-3.3/). If this table and a file header disagree, the file header applies. Full licence texts are in the `LICENSES/` directory.

## Licence texts

The copies in `LICENSES/` are taken, at release time, from these canonical sources:

- CC BY-SA 4.0: https://creativecommons.org/licenses/by-sa/4.0/legalcode
- CC BY 4.0: https://creativecommons.org/licenses/by/4.0/legalcode
- Apache License 2.0: https://www.apache.org/licenses/LICENSE-2.0
- CC BY-NC-ND 4.0 (copies distributed up to 0.3.x only): https://creativecommons.org/licenses/by-nc-nd/4.0/legalcode
- `LicenseRef-Eiraman-Trademark`: a short notice in `site/LICENSES/LicenseRef-Eiraman-Trademark.txt` that points to [TRADEMARK.md](TRADEMARK.md)
- SPDX License List: https://spdx.org/licenses/

## How to attribute

**Guide (CC BY-SA 4.0).** The attribution is "The Eiraman Guide by Paolo Ungari and contributors"; copyright lines read "2026 Paolo Ungari and contributors". Give the title, author, source and licence, and say whether you changed it. If you share an adapted version, you must license your adaptation under CC BY-SA 4.0 (or a later version, or a licence Creative Commons has declared compatible).

> *The Eiraman Guide* 1.0.0-rc.5 by Paolo Ungari and contributors, https://eiraman.tech, licensed under CC BY-SA 4.0 (https://creativecommons.org/licenses/by-sa/4.0/). Changes: translated into French and shortened.

**Role Profiles (CC BY 4.0).** Give the profile name and version, author, source and licence, and say whether you changed it. You may choose the terms for your own changes in an adaptation, and you are not required to share it. If you share it, keep the attribution, and do not choose terms that prevent recipients from complying with CC BY 4.0 for the original material (CC BY 4.0, section 3(a)(4)); you may not add terms or technical measures that restrict their rights in the original (section 2(a)(5)(B)).

> Based on the Eiraman Role Profile *FinOps Practitioner* v0.1.0 by Paolo Ungari and contributors, https://eiraman.tech, licensed under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Modified.

**Code (Apache 2.0).** Keep the `LICENSE` and `NOTICE` files and the SPDX headers, and mark the files you changed (Apache License 2.0, section 4).

Where the medium allows only a short line (a slide, a prompt, a printed card), a link to a page that holds the full attribution may be reasonable: section 3(a)(2) of the CC 4.0 licences allows the conditions to be met in any reasonable manner based on the medium, and gives a link as an example.

## What the licences do not cover

- **Trademarks.** None of these licences grants any right to use the Eiraman name or logo (CC 4.0 section 2(b)(2); Apache 2.0 section 6). Statements such as "based on the Eiraman Guide" are fine when accurate; see [TRADEMARK.md](TRADEMARK.md) for everything else.
- **Patents.** The CC licences do not license patent rights. The Apache License 2.0 contains its own patent licence for the code only.
- **Third-party material.** Standards, frameworks and products named in the Guide and in the Role Profiles belong to their owners and are referenced, not reproduced. They keep their own terms. See "Third-party material" below.
- **Endorsement.** Using Eiraman material does not imply endorsement by the Eiraman project or its maintainers.

## Third-party material

The Guide and the Role Profiles cite external standards and documentation by title, section and link. Short paraphrases describe how a role applies them. The text of those works is not included and must be obtained from the publishers under their terms. Third-party names are used only to identify the referenced works. Their use does not imply any affiliation with or endorsement by their owners.

- TOGAF® is a registered trademark of The Open Group.
- ITIL® is a registered trademark of AXELOS Limited (PeopleCert group).
- BABOK® is a registered trademark of the International Institute of Business Analysis.
- Scrum@Scale® is a registered trademark of Scrum Inc. The Scrum Guide is by Ken Schwaber and Jeff Sutherland.
- AWS, Microsoft Azure, Databricks, FinOps Foundation, OWASP and the names of AI models and tools are trademarks of their respective owners.

*Each trademark statement above must be checked against the owner's current guidelines before release.*

Any third-party file that is ever included is listed here with its source, licence and attribution, and carries its own SPDX header.

## Licence transition

Until version 0.3.x, Eiraman was distributed under different licences:

| Material | Licence up to 0.3.x | Licence from version __X__ (first public release) |
|---|---|---|
| Texts, specification | CC BY-NC-ND 4.0 | CC BY-SA 4.0 |
| Role Profiles | CC BY-NC-ND 4.0 | CC BY 4.0 |
| Scripts | MIT | Apache 2.0 |

Copies already distributed under CC BY-NC-ND 4.0 or MIT (the website, the downloadable kit and specifications 0.1 to 0.3) remain available to their holders under those licences. CC BY-NC-ND 4.0 states that the licence is irrevocable (section 2(a)(1)). The MIT licence has no express irrevocability clause; the project does not intend to withdraw the permissions it granted under MIT. The new licences apply to versions published from __X__ onward. If you hold an earlier copy and want the broader rights, use the current version.

## Contributions

Contributions are accepted under the licence of the file they modify, with a Developer Certificate of Origin sign-off on every commit. See `CONTRIBUTING.md`. Contributors keep their copyright.

## Disclaimer

The Guide, the Role Profiles and the code are provided "as is", without warranties, as stated in each licence. They are not legal, security, financial or compliance advice.
