<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Releasing

The release checklist for every Eiraman repository. Version rules and tag scheme are in
[VERSIONING.md](VERSIONING.md). Status: **draft**, adopted with the first tagged releases.

A release has three separate states, as every contribution does (GOVERNANCE §1): the **technical state**
closes with steps 1–5, the **acceptance** with step 6, the **publication** with steps 7–9. Closing one never
implies the next.

## Who does what

| Role | In this checklist |
|---|---|
| **AI Coordinator** | Prepares the release: scope, version, changelog, diff report, local CI checks, tag, publication and verification. May be a person in the same role. Never approves its own release |
| **Independent reviewer** | Re-runs the local CI checks, checks the scope of the release and signs it off (step 5). A named person who is not the author of the changes in the release and works without the authors' discussion. No AI system is ever the reviewer of record (GOVERNANCE §1, principle 1). While the project has no reviewers, the Human Manager signs the review off. An AI agent other than the executors MAY prepare the review, with its independence recorded; its findings go to the person who signs |
| **Human Manager** | Gives the Do to publish (step 6). In Stage 1 this is the Steward. Where GOVERNANCE §7 names a publisher, that person's approval is part of the Do: the Author with a second reviewer for the Guide, a domain reviewer for Role Profiles, templates and the gate checklist |

## Checklist

| Step | Who | Done when |
|---|---|---|
| 1. Decide the scope | AI Coordinator, with the owner of the artifact | The list of merged changes to release is written down, with the previous release it starts from |
| 2. Bump the version | AI Coordinator | The version source (VERSIONING §1) carries the new version, chosen by the rules of VERSIONING §2 |
| 3. Write the changelog entry | AI Coordinator | `[Unreleased]` becomes `[x.y.z] - YYYY-MM-DD`, a new empty `[Unreleased]` is on top, and the entry equals the version source |
| 4. Run the diff report and the CI checks locally | AI Coordinator | `tools/release_diff.py` has run from the previous tag to the candidate commit; the checks of the repository's `compliance.yml` have run locally on the candidate commit and passed, or the ones that could not run are recorded; both outputs are saved with the candidate |
| 5. Independent scope review | Independent reviewer (a person; the Human Manager while no reviewers exist) | The local CI checks have been re-run independently on the candidate commit; every item of the report maps to a changelog entry or an approved decision; outcome signed by the reviewer of record |
| 6. Do | Human Manager | Explicit approval to publish this candidate commit, recorded with the date |
| 7. Tag | AI Coordinator | Tag `v<version>` on the reviewed commit, whose local CI checks passed |
| 8. Publish | AI Coordinator | Tag pushed, release notes published, artifact deployed where it has a deployment |
| 9. Verify | AI Coordinator | What is online matches what was reviewed, checked from outside |

### Step 1. Decide the scope

- Start from the previous release tag. For the first tagged release of a repository, start from the
  published commit named in its `CHANGELOG.md`.
- One release per repository. A release that spans repositories (for example a site release that updates
  the kit) lists the versions of the other repositories it depends on.

### Step 2. Bump the version

- Apply VERSIONING §2 to the largest change in scope. For `0.y.z` artifacts, see VERSIONING §2.6.
- Update every place that repeats the version: for a Role Profile, both `profilo.json` and `PROFILO.md`;
  for the tools, `__version__` in every tool (a test checks this); for the site, `SITE_VERSION` and, if the
  kit changed, `KIT_VERSION`.
- Update pinned references that the release changes (`TOOLS_REF`, `PROFILES_REF`), with the released
  version in a comment next to the SHA.

### Step 3. Write the changelog entry

- Group changes under Added, Changed, Deprecated, Removed, Fixed and Security.
- Every removal, every changed obligation (RFC 2119 key word added, removed or changed) and every breaking
  change has its own line. For `0.y.z`, breaking changes are marked **breaking**.
- Name the RFCs accepted, and the profiles qualified, requalified or suspended (GOVERNANCE §7).
- Write only what happened. If something is uncertain, say so.

### Step 4. Run the diff report and the CI checks locally

```sh
python3 tools/release_diff.py <repo> <previous-tag> <candidate-commit> > release-diff.txt
python3 tools/release_diff.py <repo> <previous-tag> <candidate-commit> --json > release-diff.json
```

Use the full commit SHA of the candidate, not a branch, so that the report, the review and the tag refer
to the same commit. If the report says that removed lines were capped, run it again with a higher
`--max-lines` so that the reviewer sees every removed line.

**Local CI checks.** Before the scope review, and again before the tag, the AI Coordinator MUST run locally,
on the candidate commit, the checks that the repository's `.github/workflows/compliance.yml` runs, with the
same patterns and the same exclusions as the workflow of that commit:

| Check | How it runs locally |
|---|---|
| Secrets | `trufflehog git file://. --results=verified,unknown`, with the version pinned in the workflow |
| Local paths | The `LOCAL_PATHS` command of the workflow: `git grep` of the patterns, http(s) URLs removed, matched again |
| E-mail addresses | The `git grep` of the workflow, keeping only addresses other than the placeholders it allows |
| Deny-list | `git grep -lIiE -f <patterns>`, with the patterns of the local deny file (`.eiraman-deny.local`, or the path in `EIRAMAN_DENY_FILE`) without comments and blank lines; only file names are printed, never the terms |
| REUSE | `reuse lint`, where the workflow has the REUSE job |

The DCO sign-off of the commits since the previous tag is checked as well; the AI declaration of the pull
request has no local equivalent. Any other workflow of the repository that tests the candidate (for example
the unit tests of `tools` or the two builds of `site`) also runs locally.

The output of each check is saved with the candidate, beside the diff report, with the commit SHA and the
date. A failing check blocks the release as it would block a merge. If a check cannot run locally, for
example because `reuse` or `trufflehog` is not installed, the record names the check, the reason and the
substitute used, if any; that check counts as not run, not as passed, and is listed among the points not
verified that go to the reviewer and to the Human Manager with the Do (step 6).

### Step 5. Independent scope review

The reviewer receives the diff report, the changelog entry, the list of approved decisions in scope (RFCs,
recorded Do) and the candidate commit SHA, and nothing else from the authors. An AI agent MAY prepare the
mapping below; the human reviewer of record checks it and signs the outcome. The reviewer, or the agent that
prepares the review, MUST first re-run the local CI checks of step 4 on the candidate commit, independently of
the AI Coordinator's record, and compare the two results. The reviewer then checks that the release contains
only the changes needed and that nothing is lost between versions:

1. Every file added, removed or renamed maps to a changelog entry or an approved decision.
2. Every modified file maps to a changelog entry or an approved decision.
3. Every removed Markdown heading and every removed JSON key maps to an entry.
4. In normative files (VERSIONING §2.1), every change in the RFC 2119 key word counts maps to an entry, and
   the version bump matches it (an obligation removed or reversed means MAJOR, or **breaking** in `0.y.z`).
5. Every removed line maps to an entry. Lines that only carry a version string are listed by the reviewer
   as such.
6. The version source and the latest changelog heading agree.

**Any deletion that does not map to an entry or decision blocks the release.** An unmapped addition or
modification goes back to the AI Coordinator, who either adds the missing entry or takes the change out of
the release; the review then runs again on the new candidate. The reviewer of record signs the outcome (PASS,
PASS WITH CORRECTIONS, FAIL) with the candidate SHA, the items checked, their independence and, if an AI
agent prepared the review, which agent. If no human can sign the review, the release stays open with the
reason recorded; it is not published "pending review".

### Step 6. Do

The AI Coordinator brings the Human Manager the candidate SHA, the version, the changelog entry and the
review outcome, with what publication will change and what is not verified. Without an explicit Do the
release stops here. A Do covers this candidate only; a new candidate needs a new Do.

### Step 7. Tag

```sh
git tag -s v<version> <reviewed-sha> -m "<artifact> <version>"
```

GOVERNANCE §7 requires a signed tag with a manifest of file fingerprints; attach the manifest to the
release. Until the Steward sets up the signing key, tags are annotated (`-a`) and unsigned, a known
deviation recorded in VERSIONING §6. The tag goes on the commit that was reviewed and approved, never on
a later one. Immediately before tagging, the AI Coordinator MUST re-run the local CI checks of step 4 on that
commit; if any fails, there is no tag. For a release published before tagging started, the tag goes retroactively on the published
commit named in the changelog. A published tag is never
moved or deleted.

### Step 8. Publish

- Push the tag and create the release notes from the changelog entry.
- Deploy where the artifact has a deployment. For the site: build twice from the tagged commit, with the
  same inputs; the two manifests must be identical; upload the changed files and the manifest.
- Publication follows the scope of the Do. Anything else waits for its own release.

### Step 9. Verify

- The remote tag points at the reviewed SHA (`git ls-remote --tags origin v<version>`).
- For the site: download every file listed in the online `manifest.json` over HTTPS and compare its SHA-256
  with the manifest; all must match. The manifest `version` and `kit.version` are the released ones, and
  the kit fingerprint in the start prompt equals the fingerprint of the served zip.
- Record the outcome, with the three states kept separate: technical state, acceptance, publication. If
  verification fails, the AI Coordinator reports it to the Human Manager and restores the previous
  release, or fixes it in a new PATCH release.
