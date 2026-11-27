<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Changelog

All notable changes to the Eiraman community documents are documented in this file. The format is based
on [Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/), and versions follow
[VERSIONING.md](VERSIONING.md).

## [Unreleased]

## [0.6.0] - 2026-11-27

Scope: Change Request CR-030 of the method project, work package WP-30D (community part), after decision D-IT-1
of the Human Manager (CR-029). **Breaking:** the Italian translation of the Guide no longer needs the two
native-speaker reviewers, so an obligation is removed (VERSIONING §2.1). While the artifact is at `0.y.z`, a
change that would be MAJOR bumps MINOR (VERSIONING §2.6), hence the version bump: MINOR. A new artifact
version scheme is added. The rule for translations into other languages is unchanged. Applies from the next release of the `guide`
repository, which carries the translation.

### Added

- `VERSIONING.md`: the Italian translation of the Guide as an artifact (table row and note in section 1),
  with the scheme `<Guide version>+it.N` (SemVer build metadata; revisions ordered by `N` by convention;
  restarts at `+it.1` for each Guide version; no tag of its own); the translation in the table of references
  (section 5); the per-artifact changelogs of the registry from 0.11.0 (D-VER-2, section 2.2).

### Changed

- `PATHWAYS.md`: every operative reference to the specification 0.3 now cites the section of the Guide
  1.0.0-rc.5; the convention "How to read the references" and the open point on numbering are rewritten.
  Where the Guide has no counterpart (open points of the levels, the interface for the Human Manager,
  strategies for local and external requests) the text says so.
- `PATHWAYS.md` §5, `WORKING-GROUPS.md` §4, `GOVERNANCE.md` (language note): English is canonical and
  prevails; the Italian translation of the Guide is curated and approved by the Author (D-IT-1);
  translations into other languages follow the rule of two native-speaker reviewers and are informative
  until the Author approves them as faithful.
- `VERSIONING.md` section 5 and example: the field `metodo` of the profiles is "The Eiraman Guide
  <version>[; §…]"; the manifest records `guide_commit`, `guide_version` and `kit.bundled.guide`/`guide_it`,
  and the kit no longer carries the specification 0.3.
- `LICENSING.md`, `TRADEMARK.md`: "Guide v1.0" becomes "the Eiraman Guide" or the version 1.0.0-rc.5.
- `CASE-STUDY-TEMPLATE.md`: references to the specification 0.3 replaced by sections of the Guide.

## [0.5.0] - 2026-11-27

Scope: Change Request CR-026 of the method project (community part). Version bump: MINOR, because
`RELEASING.md` adds a mandatory check to the release procedure (VERSIONING §2.1; as in 0.3.0). It applies from
site `0.10.2`, the release that introduces `profiles.ref`, the registry check of the build and the manifest
fields `registry_commit` and `publishable`; publish this release after site `0.10.2`.

### Changed

- `RELEASING.md`, step 2: for the site the pinned registry reference is `profiles.ref`, with the registry
  version in a comment; `PROFILES_REF` remains in the tests of `tools`, `TOOLS_REF` is unchanged.
- `RELEASING.md`, step 8: the registry given to the site build is a detached worktree at the commit in
  `profiles.ref`; another checkout makes the build fail; a build with `EIRAMAN_PROFILES_UNPINNED=1` is never
  published.
- `VERSIONING.md` section 5: the reference from `site` to the registry is `profiles.ref`, read by the CI and
  by the generator; `PROFILES_REF` stays the reference of `tools`.
- `VERSIONING.md` version table: site `0.10.2` (was `0.10.0`), community documents `0.5.0` (was `0.4.3`).

### Added

- `RELEASING.md`, step 9: for the site, the online manifest `registry_commit` must equal the SHA in
  `profiles.ref` of the tagged commit and `publishable` must be `true`.

## [0.4.3] - 2026-11-27

Scope: Change Request CR-025 of the method project. Version bump: PATCH, the version table only; documentation
alignment, no policy change.

### Changed

- `VERSIONING.md` version table, aligned to the versions released in the sibling repositories: Guide
  `1.0.0-rc.5` (was `1.0.0-rc.3`), registry `0.10.0` (was `0.8.0`), AI Coordinator profile `0.12.0` (was
  `0.7.0`), site `0.10.0` (was `0.9.0`), community documents `0.4.3` (was `0.4.2`). Extended Framework `0.2.1`,
  Digital Seniority map `0.2.0`, tools `0.3.2`, kit `0.9.0` and `.github` `0.2.1` were already correct.
- `VERSIONING.md`, Role Profiles row: the distribution of profile versions follows the registry `0.10.0`
  (35 profiles at `0.2.0`, 8 at `0.3.0`, 5 at `0.4.0`, facilitatore-design-thinking at `0.7.0`) and names the
  three templates with their versions.
- `VERSIONING.md`, section 5 (table, row "Each Role Profile"): the `metodo` field now cites the Guide versions `1.0.0-rc.3` and `1.0.0-rc.5`,
  both named by the profiles of registry `0.10.0`.
- `PATHWAYS.md`: the registry profile count is 49 (was 48), as in registry `0.10.0`.

### Added

- `VERSIONING.md` version table: row for the local engines map (`_seniority/motori-locali.json`, `0.1.0`),
  introduced by registry `0.10.0` and not listed before.

## [0.4.2] - 2026-11-26

Scope: Change Requests CR-011 and CR-012 of the method project. Version bump: PATCH, the version table only.

### Changed

- `VERSIONING.md` version table: registry `0.8.0` with its per-profile versions (`0.3.0` for revisore-ai,
  `0.5.0` for facilitatore-design-thinking), AI Coordinator profile `0.7.0`, site `0.9.0`, kit `0.9.0`,
  community documents `0.4.2`. Registry `0.7.0` was published between `0.6.1` and `0.8.0` and was never
  listed here. Order of publication: this release goes last, after the releases it lists.

## [0.4.1] - 2026-11-26

Scope: Change Request CR-010 of the method project. Version bump: PATCH, the version table only.

### Changed

- `VERSIONING.md` version table, to the PATCH releases that follow the independent re-review of Wave CONS-01:
  Extended Framework `0.2.1`, registry `0.6.1` with its per-profile versions (`0.2.1` for revisore-ai, `0.3.1`
  for facilitatore-design-thinking), AI Coordinator profile `0.5.1`, tools `0.3.2`, site `0.8.1`, kit `0.8.1`,
  community documents `0.4.1`. Order of publication: this release goes last, after the releases it lists.

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

[Unreleased]: https://github.com/eiraman/community/compare/v0.6.0...main
[0.6.0]: https://github.com/eiraman/community/compare/v0.5.0...v0.6.0
[0.5.0]: https://github.com/eiraman/community/compare/v0.4.3...v0.5.0
[0.4.3]: https://github.com/eiraman/community/compare/v0.4.2...v0.4.3
[0.4.2]: https://github.com/eiraman/community/compare/v0.4.1...v0.4.2
[0.4.1]: https://github.com/eiraman/community/compare/v0.4.0...v0.4.1
[0.4.0]: https://github.com/eiraman/community/compare/v0.3.0...v0.4.0
[0.3.0]: https://github.com/eiraman/community/compare/v0.2.1...v0.3.0
[0.2.1]: https://github.com/eiraman/community/compare/v0.2.0...v0.2.1
[0.2.0]: https://github.com/eiraman/community/compare/v0.1.0...v0.2.0
[0.1.0]: https://github.com/eiraman/community/releases/tag/v0.1.0
