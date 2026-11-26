<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Changelog

All notable changes to the Eiraman community documents are documented in this file. The format is based
on [Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/), and versions follow
[VERSIONING.md](VERSIONING.md).

## [Unreleased]

## [0.2.0] - 2026-11-26

### Added

- `VERSIONING.md`: artifacts and their version sources, SemVer rules per artifact type, pre-release
  labels, the tag scheme `v<version>` per repository, and how versions refer to each other.
- `RELEASING.md`: the release checklist, with the diff report and the independent scope review.
- A reference line to both documents at the end of GOVERNANCE §7, and their rows in `README.md`. No
  governance rule changes.
- This changelog, and the CI workflow `changelog.yml`.

## [0.1.0] - 2026-11-25

First public release, published as commit `3420555` of `github.com/eiraman/community` during the
restricted launch of 25 November 2026. It was not tagged; the version number was assigned afterwards
(VERSIONING.md). The tag `v0.1.0` will be applied retroactively to that commit. All documents are drafts, not yet in force.

### Added

- `GOVERNANCE.md`: three stages (Independent Steward, Steering Committee, neutral foundation) with public
  thresholds, roles (Author, Steward, Steering Committee, working group leads, domain reviewers, maintainers,
  reviewers, contributors, declared adopters), the Role Profile maintenance rules, decision making and
  RFCs, releases, conflict of interest, and the limit on licence changes.
- `WORKING-GROUPS.md`, `MAINTAINERS.md` (placeholders), `PATHWAYS.md` (a path for each kind of
  contributor), `CASE-STUDY-TEMPLATE.md`, `cases/` and `meetings/`.
- `LICENSING.md` (which licence covers which material, attribution "The Eiraman Guide by Paolo Ungari and
  contributors") and `TRADEMARK.md` (use of the Eiraman name and logo).
- CI: compliance checks (DCO and AI declaration, REUSE, secrets and deny-list) and the Markdown link check.

### Notes

- The documents come from the drafts of the Open Framework work of 25 November 2026, reviewed
  independently before publication. From this release, this repository is their source; the earlier
  drafts are no longer kept aligned.
- At the launch, the link check of this repository first failed because the `.github` repository did not
  exist yet; it passed when re-run.

[Unreleased]: https://github.com/eiraman/community/compare/v0.2.0...main
[0.2.0]: https://github.com/eiraman/community/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/eiraman/community/releases/tag/v0.1.0
