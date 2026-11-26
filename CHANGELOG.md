<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Changelog

All notable changes to the Eiraman community documents are documented in this file. The format is based
on [Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/), and versions follow
[VERSIONING.md](VERSIONING.md).

## [Unreleased]

## [0.4.0] - 2026-11-26

Scope: Change Request CR-007 of the method project, implementing RFC 0002
(`guide/rfcs/0002-governo-family.md`), alternative B, accepted by the Steward, who in Stage 1 is also the
Author, on 2026-11-26 (Do-S18). The decision was taken before the end of the thirty-day comment period of
GOVERNANCE §10, a deviation recorded in the RFC. Version bump: MINOR, because a working group and its rules
are added (VERSIONING §2.1).

### Added

- `WORKING-GROUPS.md` §3: the family group **Governance & Assurance**, owner of the whole `governo/` family
  (the family file and the seven profiles), with its scope, artifacts, reviewer rule (it never publishes;
  each `revisore-<domain>` is co-reviewed and published by the reviewers of record of its domain;
  `revisore-ai` and the family file by Test & Quality, provisionally; changes to FAMIGLIA §A–§C also need lazy
  consensus of the six domain groups; four eyes across both groups) and entry criteria.
- `WORKING-GROUPS.md` §2: each domain group owns the co-review and publication of its AI reviewer profile in
  `governo/`; Test & Quality also `revisore-ai` and `governo/FAMIGLIA.md`, provisionally.
- `WORKING-GROUPS.md` §5: open point, no domain of GOVERNANCE §4.5 owns the method's oversight roles.
- `MAINTAINERS.md`: a "Working group leads" row for Governance & Assurance and a "Maintainers by area" row
  for `Role Profiles / governo`, both placeholders.

### Changed

- `PATHWAYS.md`: the existing families include Governance (Governance & Assurance); the registry count is 48
  profiles in 8 families (it said 40 in 7).
- `VERSIONING.md` version table, to the versions released together with this one (Waves GOV-01 and CONS-01,
  Change Request CR-010): The Eiraman Guide `1.0.0-rc.3`, Extended Framework `0.2.0`, per-profile versions of
  registry `0.6.0` (`0.2.0` for 45 profiles and the two templates, `0.3.0` for three), AI Coordinator profile
  `0.5.0`, Digital Seniority map `0.2.0`, registry `0.6.0`, tools `0.3.1`, site `0.8.0`, kit `0.8.0`,
  community documents `0.4.0`. The Guide row still said `1.0.0-rc.2` after the Guide release of 26 November.
- `VERSIONING.md` §5 and §6: the field `metodo` of the profiles names the Guide version each profile follows,
  since registry 0.6.0; the known deviation on that field is closed.

## [0.3.0] - 2026-11-26

Scope: Change Requests CR-005 and CR-006 of the method project. Version bump: MINOR, because
`RELEASING.md` adds obligations (VERSIONING §2.1).

### Added

- `RELEASING.md`, step 4 (now "Run the diff report and the CI checks locally"): the AI Coordinator MUST run
  the checks of the repository's `compliance.yml` locally on the candidate commit before the scope review,
  and again before the tag (step 7): secrets, local paths, e-mail addresses, the deny-list through the local
  deny file, and REUSE where the workflow has it, plus the DCO sign-off and the repository's other test
  workflows. Outputs are saved with the candidate; a failing check blocks the release; a check that cannot
  run locally (for example `reuse` or `trufflehog` not installed) is recorded as not run, with the reason,
  and goes to the reviewer and to the Human Manager as a point not verified.
- `RELEASING.md`, step 5: the independent reviewer, or the agent preparing the review, MUST re-run the
  local CI checks on the candidate commit and compare them with the AI Coordinator's record. The roles
  table and the checklist rows of steps 4, 5 and 7 say the same.
- `VERSIONING.md` §1, notes: a change in `guide` that leaves the released texts unchanged (CI workflows,
  repository metadata) does not change the Guide version and is not tagged; it waits under `[Unreleased]`.
  In repositories whose version source is `CHANGELOG.md`, such a change is a PATCH.

### Changed

- `VERSIONING.md` version table, to the versions of this release (Wave REL-07): Extended Framework `0.1.2`,
  per-profile versions of registry `0.4.1`, AI Coordinator profile `0.4.2`, registry `0.4.1`, tools `0.2.3`,
  site and kit `0.7.0`, community documents `0.3.0`, organisation defaults `0.2.1`.
- `RELEASING.md`: a check recorded as not run does not block the tag if the CI runs it on the pushed commit;
  diverging results between the AI Coordinator and the reviewer block the tag (Do-S17).

### Fixed

- CI, `compliance.yml`: the local-path check removes http(s) URLs from the matched lines and matches
  again, so a path segment inside a URL (such as `/home/` in an official ISO URL) is no longer flagged.
  The block is the one of `role-profiles` v0.4.1 (the whole workflow file is now identical to that one). Change Requests CR-005 and CR-006 of the
  method project.

## [0.2.1] - 2026-11-26

### Changed

- `VERSIONING.md` version table: The Eiraman Guide `1.0.0-rc.2`, Role Profiles registry `0.2.0`, AI Coordinator
  profile `0.4.0`, community documents `0.2.1`, and the per-profile versions after the registry release `0.2.0`. Version strings only; no
  rule changes.

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

[Unreleased]: https://github.com/eiraman/community/compare/v0.4.0...main
[0.4.0]: https://github.com/eiraman/community/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/eiraman/community/compare/v0.2.1...v0.3.0
[0.2.1]: https://github.com/eiraman/community/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/eiraman/community/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/eiraman/community/releases/tag/v0.1.0
