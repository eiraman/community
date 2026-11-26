<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Versioning

Every Eiraman artifact has a version and a changelog. This document says where each version is written,
what a change of each number means, how releases are tagged and how versions refer to each other. The
release procedure is in [RELEASING.md](RELEASING.md). Status: **draft**, adopted with the first tagged
releases.

All versions follow [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) (`MAJOR.MINOR.PATCH`,
with an optional pre-release label). Every repository has a `CHANGELOG.md` in the
[Keep a Changelog 1.1](https://keepachangelog.com/en/1.1.0/) format, with an `[Unreleased]` section at the
top. A CI check (`.github/workflows/changelog.yml`) fails a pull request that does not change
`CHANGELOG.md`, unless a maintainer adds the label `no-changelog`.

## 1. Artifacts and version sources

The *version source* is the one place where the version is written. At release time the latest released
heading of the repository's `CHANGELOG.md` must equal it (RELEASING.md, step 2).

| Artifact | Repository | Version source | Current version |
|---|---|---|---|
| The Eiraman Guide | `guide` | Title block of `EIRAMAN-GUIDE.md` ("Version …") | `1.0.0-rc.3` |
| Historical specification 0.3 | `guide`, `history/` | Frozen copy, non-normative; no further versions | `0.3` |
| Extended Framework | `framework` | `CHANGELOG.md` | `0.2.1` |
| Each Role Profile | `role-profiles` | Field `versione` of `profilo.json`; the `Versione` line of `PROFILO.md` repeats it and must match | `0.2.0` (44 profiles, plus the templates business-analyst and user-persona), `0.2.1` (revisore-ai), `0.3.0` (analista-funzionale, utente-simulato), `0.3.1` (facilitatore-design-thinking) |
| AI Coordinator profile | `role-profiles`, `controllore/` | `Versione` line of `CONTROLLORE.md` | `0.5.1` |
| Digital Seniority map | `role-profiles`, `_seniority/` | Field `versione` of `seniority.json` | `0.2.0` |
| Role Profiles registry, as a whole | `role-profiles` | `CHANGELOG.md` | `0.6.1` |
| Tools | `tools` | `__version__` in each tool, printed by `--version`; one version for the repository | `0.3.2` |
| Website eiraman.tech | `site` | `version` in `manifest.json`, set by `SITE_VERSION` in `generator/build.py` | `0.8.1` |
| Kit (`kit/eiraman-kit.zip`) | `site` | `kit.version` in `manifest.json`, set by `KIT_VERSION` in `generator/build.py` | `0.8.1` |
| Community documents | `community` | `CHANGELOG.md` | `0.4.1` |
| Organisation defaults | `.github` | `CHANGELOG.md` | `0.2.1` |

Notes:

- **Guide.** The first release candidate was published as "1.0-rc"; normalised to SemVer it is
  `1.0.0-rc.1`. Records written before, such as `AUTHOR-RATIFICATION.md`, still say "v1.0-rc" and mean
  the same version.
- **AI Coordinator profile.** Its number, 0.3.0, was set when it followed the specification 0.3. From now
  on it changes by the profile rules below, independently of the Guide.
- **Changes outside the versioned text.** In `guide`, whose version source is the title block of
  `EIRAMAN-GUIDE.md`, a change that leaves the released texts unchanged, such as a CI workflow or repository
  metadata, does not change the Guide version and is not tagged: it is listed under `[Unreleased]` in the
  guide `CHANGELOG.md` and released with the next Guide version. In the repositories whose version source
  is `CHANGELOG.md` (`framework`, `community`, `.github`, `role-profiles`), the repository is the artifact,
  so such a change is a PATCH of the repository.
- **Kit.** Its own line starts at 0.4.0: the kit's licence notice already calls the earlier copies
  "versions up to 0.3.x", which were served with site 0.3.x. From 0.4.0 on, the kit changes only when its
  content changes, whatever happens to the site pages.

## 2. What each number means

### 2.1 Normative texts

The Guide, the Extended Framework, `GOVERNANCE.md` and the other rule-setting documents of `community`,
and `CONTRIBUTING.md` of `.github`. An *obligation* is a rule carrying MUST, MUST NOT, SHOULD, SHOULD NOT or
MAY, or, in documents without those key words, a rule stated as binding.

| Bump | When |
|---|---|
| MAJOR | An obligation is removed or reversed, or its scope is narrowed so that something that conformed before no longer conforms, or something required before is no longer required |
| MINOR | An obligation is added or broadened; a new section or practice is added |
| PATCH | Editorial change with no change of meaning: typos, wording, links, numbering, formatting, translation fixes |

A change of RFC 2119 key word (for example SHOULD to MUST) adds or broadens an obligation (MINOR); the
reverse (MUST to SHOULD) removes one (MAJOR). Changes to the Guide text still need an RFC
(GOVERNANCE §6.2): the version rule decides the number, not whether the change is allowed.

### 2.2 Role Profiles and the registry

The same logic, applied to a profile's rules (allowed and forbidden actions, reserved Do, communication
rules), declared limits and task catalogue:

| Bump | When |
|---|---|
| MAJOR | A rule or limit is removed or reversed; a task leaves the catalogue or changes its ID; a deliverable a task promised is no longer produced |
| MINOR | A rule, limit or task is added or broadened; the Digital Seniority level of a task changes; a source of competence is added; an engine or Mode and Role entry is added |
| PATCH | Editorial changes, corrected source references with the same meaning, fixes that restore the stated intent |

The **qualification state** (draft, not qualified; qualified; maintained; suspended) is not a version. A
change of state alone does not bump the version; it is recorded in the profile and in the release notes.
Every new version of a profile, whatever its number, is published by a domain reviewer under
GOVERNANCE §4.5.

The **registry** version takes the largest bump among the changes it releases: removing a profile, or a
change to `_modello/` or `seniority.json` that makes existing profiles fail the validator, is MAJOR;
adding a profile or a family, or any profile's MINOR, is MINOR; otherwise PATCH. The Digital Seniority map
follows the profile rules for its own number.

**Per-profile change history.** The profile template (`_modello/`) has no change-history section. Adding
one would change the format every profile follows, which is a format change for the DevSecOps & Tooling
group. Until then, per-profile versions and their changes are recorded in the registry `CHANGELOG.md`,
in the "Profile versions" table of each release.

### 2.3 Code

The tools follow standard SemVer. The public interface is: command-line arguments, exit codes, output
formats (including `--json`), files and environment variables read, and the registry layout expected.
MAJOR breaks it, MINOR adds to it compatibly, PATCH fixes bugs. All tools of the `tools` repository share
one version.

### 2.4 Site and kit

| Bump | When |
|---|---|
| MINOR | Content changes: pages, texts, images, kit content, a bundled artifact with a new MINOR or MAJOR |
| PATCH | Fixes: typos, broken links, layout or hosting fixes, a bundled artifact with a new PATCH |

MAJOR is not used while the site and the kit are at `0.y.z`. A change to the metadata of `manifest.json`
alone, with no other served file changed, is a PATCH of the site; the kit keeps its version when its bytes
do not change.

### 2.5 Community documents and organisation defaults

`community` and `.github` follow 2.1 for documents that set rules and PATCH or MINOR for the others
(templates, READMEs, lists of maintainers): MINOR when a template gains or loses a field, PATCH otherwise.

### 2.6 Versions below 1.0.0

Most artifacts are at `0.y.z`, the initial development stage. While at `0.y.z`, a change that would be
MAJOR bumps MINOR, and the changelog marks it as **breaking**; everything else bumps PATCH or MINOR as
above. An artifact moves to `1.0.0` when its owner declares it stable; the Guide is published by the Author
with a second reviewer (GOVERNANCE §7).

## 3. Pre-release labels

| Label | Meaning |
|---|---|
| `-rc.N` | Release candidate: complete, under review, not in force. Numbered from 1; a new candidate of the same version increments `N` |
| `-beta.N` | Feature-complete draft, open to public comment |
| `-alpha.N` | Partial draft, for early feedback |

A pre-release never counts as "in force". `1.0.0-rc.1` < `1.0.0-rc.2` < `1.0.0`, as in SemVer.

## 4. Tags

**Scheme: `v<version>` in each repository**, for example `v1.0.0-rc.1` in `guide`, `v0.1.0` in `tools`,
`v0.4.0` in `site`. Outside the repository, cite an artifact as `<repository>@<tag>`, for example
`eiraman/guide@v1.0.0-rc.1`.

Why this scheme rather than prefixed tags such as `guide-v1.0.0-rc.1`:

- each repository holds one primary artifact with its own release cadence, so the repository name
  already says which artifact a tag belongs to; a prefix would repeat it;
- `v<version>` is what GitHub Releases, `git describe` and most release tooling expect;
- the organisation's issue templates already cite versions this way (`role-profiles/... @ v0.1.0`).

Prefixed tags would be needed only if several artifacts with independent versions shared one repository
and were tagged separately. Where that happens, the secondary artifacts are **not** tagged: individual
Role Profiles, the AI Coordinator profile and the Digital Seniority map are released with a registry
tag, and the kit with a site tag. Their versions are read from their version source at that tag.

Tags are signed, as GOVERNANCE §7 requires, made on the exact commit the scope review examined, and
accompanied by the manifest of file fingerprints. Until the project signing key exists they are annotated
but unsigned (§6, Known deviations). A published tag is never moved or deleted; a mistake is fixed by a
new version. The releases of 25 November 2026 were published as commits without tags; each changelog
gives their commit.

## 5. How versions refer to each other

| From | To | Where |
|---|---|---|
| Kit | Guide, specification, registry, AI Coordinator profile, tools | `kit.bundled` in the site `manifest.json`, written by the build from the version sources |
| Site | Kit | `kit.version` in `manifest.json` |
| `role-profiles` CI | Tools | `TOOLS_REF` in `validate-profiles.yml`, the full commit SHA of a tools release |
| `tools` and `site` CI | Registry | `PROFILES_REF` in `tests.yml` and `site-build.yml`, the full commit SHA of a registry release |
| Each Role Profile | Method | Field `metodo` of `profilo.json` (since registry 0.6.0: "Eiraman 0.3" and the Guide version the profile follows, today 1.0.0-rc.3) |
| Extended Framework | Guide | The Guide version it is written against, stated in its `CHANGELOG.md` for each release |
| Compatibility claims | Guide or profile format | A specific version, as TRADEMARK.md requires |

Example, the site manifest for 0.4.1 as built from the public repository:

```json
"version": "0.4.1",
"kit": {
  "path": "kit/eiraman-kit.zip",
  "version": "0.4.0",
  "bundled": {"guide": null, "specification": null, "registry": "0.1.1",
              "ai_coordinator_profile": "0.3.0", "tools": null}
}
```

`null` means the kit does not contain that artifact: the kit ships the AI Coordinator profile and the
registry, but neither the Guide nor the tools. `specification` is `"0.3"` when the historical
specification is supplied to the build. `"unknown"` would mean the artifact is in the kit but its version
source was missing in the checkout used.

When a pinned SHA moves to a new release, the pull request names the released version in a comment next
to the SHA and in the changelog.

## 6. Known deviations

| Deviation | Correction |
|---|---|
| The site was redeployed on 25 November 2026 with new content under the label 0.3.0, several times before the launch and once at the launch | The launch content is version 0.4.0; the earlier republications are listed under 0.3.0 in the site `CHANGELOG.md` |
| The Guide was published as "1.0-rc" | Normalised to `1.0.0-rc.1` |
| No release of 25 November 2026 was tagged | Each changelog gives the published commit; the tag of that version is applied retroactively to it (Guide excepted: `v1.0.0-rc.1` goes on its 26 November 2026 release commit) |
| Tags are annotated but not signed, while GOVERNANCE §7 requires signed tags with a manifest | Closed when the signing key is set up by the Steward; from then on every tag is signed |
| The `metodo` field of the profiles named only "Eiraman 0.3" | Closed with registry 0.6.0: every profile names the Guide version it follows alongside the specification 0.3 |
