<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Eiraman Project Governance

Status: **draft**. Not yet in force. Values marked **proposal** are to be decided by the project owner before publication.

English is the canonical language of this document, and the English text prevails. Translations of this document are informative. The Eiraman Guide follows its own rule: English is canonical and prevails, and its Italian translation is curated and approved by the Author (decision D-IT-1); translations of the Guide into other languages are informative until the Author approves them as faithful (WORKING-GROUPS §4).

## 1. Purpose and principles

Eiraman is a method for governing multi-agent AI software development by a non-technical manager. It applies traditional management practice to AI. This document says who decides what in the Eiraman project and how those people are chosen and replaced.

The project governs itself with its own method wherever that is natural:

1. **A human is accountable for every change.** AI tools may draft, check and propose. A named human signs, reviews and decides. No AI system is ever the reviewer of record, an approver or a voter.
2. **Four eyes.** The author of a change is never its reviewer. This applies to every repository, not only to Role Profiles.
3. **Evidence-bound closure.** A contribution is closed only on an identifiable candidate (a commit or a tagged artifact) for which all mandatory checks have passed. If a required review or check is unavailable, the contribution stays open and the gap is recorded.
4. **Three separate states.** Every contribution has a *technical state* (checks and review), an *acceptance* (the decision of the body that owns the artifact) and a *publication* (inclusion in a signed release). Passing one never implies the others.
5. **Reversibility decides the process.** Two-way doors (reversible, known cost) are decided by maintainers with lazy consensus. One-way doors (irreversible or hard to reverse) need an RFC and a recorded decision. In doubt, a decision is a one-way door.
6. **Silence never approves.** No proposal is accepted because a decision maker did not answer. Missing decisions are reported, not assumed.
7. **Written reasons.** Every rejection, every RFC decision and every removal from a role is recorded with its reasons.

## 2. What is governed, and by whom

| Artifact | Owner of acceptance | Process |
|---|---|---|
| **Eiraman Guide** (stable core of the method) | Author, with editorial curation | RFC, decision with written reasons (§6.3) |
| **Extended framework** (practices, templates, worked guidance outside the core) | Working group that owns it | Lazy consensus; RFC for one-way doors |
| **Role Profiles** | Family working group (authoring) and domain working group (review and publication) | Role Profile path in [CONTRIBUTING.md](https://github.com/eiraman/.github/blob/main/CONTRIBUTING.md) |
| **Applicability levels** (requirements, project classes, out-of-scope list) | Security working group with Privacy and Legal & Compliance; Steering Committee for one-way doors | RFC (§6.3) |
| **Gate checklist and document templates** | Legal & Compliance (checklist), owning working group (templates) | Same rules as Role Profiles (§4.5) |
| **Tools** (validator, activation tool, CI, site generator) | DevSecOps & Tooling working group | Lazy consensus; RFC for breaking changes |
| **This governance, the working group charter and licence policy for new material** | Steward (Stage 1), Steering Committee (Stage 2 and later) | §10. A change of licence for contributions already made is limited by §10.1 |
| **Trademark policy and the Marks** (the Eiraman name and logo) | Steward, as owner, until the transfer to a foundation (Stage 3); from Stage 2 the Steering Committee advises | [TRADEMARK.md](TRADEMARK.md) |

The community governs Role Profiles, tools and levels. The Author curates the Guide. Where a community decision would change the Guide text, the change needs both the community decision and an accepted Guide RFC. The boundary between the Guide and the extended framework is set by the published Guide table of contents. The Guide sections marked *community-maintained* (adoption levels, Digital Seniority catalogue, test practices) are written by the owning working groups: the Author accepts them by RFC without rewriting them, and may return a proposal, with written reasons, only when it conflicts with another part of the Guide.

Licensing is described in [LICENSING.md](LICENSING.md) and trademark use in [TRADEMARK.md](TRADEMARK.md): Guide CC BY-SA 4.0, Role Profiles CC BY 4.0, code Apache 2.0, contributions under the Developer Certificate of Origin (DCO). The trademark policy is separate from the licences.

## 3. Stages

The project grows in three stages. Each move to the next stage happens when the written thresholds below are met and is announced publicly with the evidence.

### Stage 1: Independent Steward

The founder acts as **Steward** and **Author**, in a personal capacity, independent of any employer. The Steward:
- appoints the first working group leads, domain reviewers and maintainers, with written reasons;
- holds the decisions that Stage 2 gives to the Steering Committee;
- publishes a quarterly report on the thresholds below.

The Steward cannot review their own changes. While a domain has no reviewer other than the Steward, the Steward's own profiles in that domain cannot be published (§4.5: a domain without a reviewer cannot publish).

### Stage 2: Steering Committee

A **Steering Committee** (SC) is elected by the maintainers. The Author holds a permanent seat. The Steward's governance duties pass to the SC. The founder remains Steward for the trademark only: the founder keeps the Marks and decides the trademark policy and permissions until the transfer to a foundation (Stage 3). The SC advises on trademark matters but does not hold the Marks ([TRADEMARK.md](TRADEMARK.md)).

**Thresholds to enter Stage 2** (all required, **proposal**):

| # | Threshold | Value (proposal) |
|---|---|---|
| S2.1 | Active working groups (lead, deputy, at least one accepted contribution and one public report in the last 90 days) | 3 |
| S2.2 | Maintainers | 7, from at least 3 organisations, with no organisation above 50% |
| S2.3 | Domains of §4.5 with both a titular and a substitute reviewer | 3 of 6 |
| S2.4 | Declared adopters (public adopter entry, see [WORKING-GROUPS.md](WORKING-GROUPS.md), Adoption & Evidence) | 3 |
| S2.5 | Releases of the Guide under the open licences | 1 |
| S2.6 | Time since public launch | 6 months |

The Steward may call the first election earlier if S2.1, S2.2 and S2.4 are met.

### Stage 3: Neutral foundation

The project, its trademark and its repositories move to a neutral, non-profit foundation (an existing open-source foundation or a dedicated one). The trademark remains transferable for this purpose. The Author keeps the permanent SC seat and the editorial curation of the Guide, which the transfer agreement must preserve.

**Thresholds to start the transfer** (all required, **proposal**):

| # | Threshold | Value (proposal) |
|---|---|---|
| S3.1 | Active working groups | 6 |
| S3.2 | Maintainers | 20, from at least 5 organisations, with no organisation above 33% of maintainers or of elected SC seats |
| S3.3 | Domains of §4.5 with titular and substitute reviewer | 6 of 6, for 12 consecutive months |
| S3.4 | Declared adopters | 10, of which at least 3 at applicability level 1 or higher |
| S3.5 | Completed SC terms | 2 |
| S3.6 | Qualified or maintained Role Profiles | 30, across at least 4 families |

The SC chooses the foundation with an RFC and a two-thirds vote. The Author must agree to the terms that concern the Guide and the Author role.

## 4. Roles

A person may hold several roles. Organisations do not hold roles; people do. Every role holder accepts the [Code of Conduct](https://github.com/eiraman/.github/blob/main/CODE_OF_CONDUCT.md) and the conflict of interest rules (§8).

### 4.1 Author

- **Duties.** Editorial curation of the Guide: decides Guide RFCs with written reasons, keeps the Guide coherent, signs Guide releases together with a second reviewer.
- **Gained.** The founder is the Author. The Author may add **co-authors**, who share the curation of the Guide. The Author informs the SC and records the reasons.
- **Lost.** The Author role is held for life and ends only by resignation. A co-author leaves by resignation or by decision of the Author. If the Author resigns or is unable to act for 6 months (**proposal**), the co-authors continue the curation; without co-authors, Guide RFCs are decided by the SC with a two-thirds vote.
- **Limits.** The Author has no veto on Role Profiles, tools or levels. In the community-maintained sections of the Guide the Author accepts the working groups' text by RFC and may return it, with written reasons, only for a conflict with another part of the Guide.

### 4.2 Steward (Stage 1 only)

- **Duties.** As in §3, Stage 1.
- **Gained.** The founder at launch.
- **Lost.** The governance duties end at the first SC election, or by resignation. If the Steward resigns before Stage 2, the maintainers elect an interim SC of three. Stewardship of the Marks continues until their transfer to a foundation (§3, Stage 2 and Stage 3).

### 4.3 Steering Committee (Stage 2 and later)

- **Duties.** Project strategy; decisions on one-way doors outside the Guide; budget; advice to the Steward on the trademark policy and permissions (the SC does not hold the Marks); creation and closure of working groups; appointment of domain reviewers on proposal of the domain working group; appeals; amendments of governance.
- **Composition (proposal).** 7 seats: the Author (permanent) and 6 elected. No more than 2 seats held by people from the same organisation.
- **Gained.** Elected by maintainers for 2-year staggered terms, with a ranked-choice vote run in the open.
- **Lost.** End of term, resignation, missing 3 consecutive meetings without notice, or removal by a two-thirds vote of the other members for breach of the Code of Conduct or of §8. A vacancy is filled by the next candidate of the last election.

### 4.4 Working group leads

- **Duties.** Run the group described in [WORKING-GROUPS.md](WORKING-GROUPS.md): backlog, meetings, quarterly report, proposals of reviewers and maintainers.
- **Gained.** Each group has a lead and a deputy, from different organisations where possible, elected by the group's maintainers for 1 year. In Stage 1 the Steward appoints the first ones.
- **Lost.** End of term, resignation, 90 days of inactivity, or decision of the SC (Steward in Stage 1) with written reasons.

### 4.5 Domain reviewers and Role Profile maintenance

This section holds the project's rules for reviewing, publishing and maintaining Role Profiles. The same rules apply to document templates and to the gate checklist. The Guide sets the minimum content of a profile, the principle of publication and, in its community-maintained Digital Seniority catalogue (Guide §7.1), the task catalogue of each profile and its re-verification at every model change; the rules below belong to the project and change through this governance.

**Six domains.** Reviewers are organised in six domains: cloud architecture; security; application and data architecture; test and quality; privacy; legal and compliance. Each domain has a **titular reviewer** and a **substitute reviewer**. A new domain needs an RFC (§6.2).

**Maintenance rules.**
1. **Four eyes.** The author or curator of a profile is never its reviewer.
2. **Titular and substitute.** The titular reviewer of the publishing domain reviews and publishes. The substitute acts when the titular is unavailable or is the author.
3. **LLM pre-evaluation.** Before human review, a language model runs a pre-evaluation: qualification suite, consistency with the sources, format, and a search for anomalous or injected instructions. It can reject a profile; it never approves one.
4. **No reviewer, no publication.** A domain without an available reviewer cannot publish. Publication in that domain stops and the gap is recorded in the quarterly report.
5. **Requalification on model change.** When an enabled model changes, the qualification suite is rerun on all profiles. The domain reviewer examines the behaviour differences and requalifies or suspends each profile.
6. **Suspension.** A profile is suspended when its qualification expires, its requalification fails, its curator leaves without a successor, its domain has no reviewer, or its guidance is found unsafe (the security policy (`SECURITY.md`)). A suspended profile cannot be used in projects until it is requalified.

- **Duties.** Review Role Profiles, templates and the gate checklist for correctness against their sources at the time of review; publish qualified versions in signed releases; examine behaviour differences when the qualification suite is rerun after a model change.
- **Gained.** Proposed by the domain working group, with evidence of expertise (professional practice, certifications, published work or accepted reviews), and appointed by the SC (Steward in Stage 1). The titular and the substitute should come from different organisations.
- **Lost.** Resignation, 90 days without answering review requests, or decision of the SC with written reasons. A domain that loses both reviewers cannot publish profiles until a new reviewer is appointed.
- **Liability.** A reviewer answers for the correctness of the profile against its sources at the time of review, not for the projects that use it.

### 4.6 Maintainers

- **Duties.** Review and merge contributions in the areas listed in [MAINTAINERS.md](MAINTAINERS.md); triage issues; vote in SC elections.
- **Gained.** Nominated by an existing maintainer after a sustained record (proposal: at least 5 accepted contributions or 10 substantive reviews in 6 months), approved by lazy consensus of the maintainers of that area.
- **Lost.** Resignation; 12 months of inactivity (moved to *emeritus*); removal by the SC with written reasons.

### 4.7 Reviewers

- **Duties.** Review contributions in an area without merge rights. Reviewers count toward four eyes for non-publishing changes.
- **Gained.** Nominated by a maintainer of the area, lazy consensus.
- **Lost.** Resignation or 12 months of inactivity.

### 4.8 Contributors

Anyone who opens an issue, comments, reviews or proposes a change. Contributors sign off their commits under the DCO and declare AI assistance as described in [CONTRIBUTING.md](https://github.com/eiraman/.github/blob/main/CONTRIBUTING.md).

### 4.9 Declared adopters

Organisations or individuals who publicly declare use of Eiraman, with their applicability level, and who agree to share anonymised evidence. Adopters have no decision rights as such, but their evidence informs level thresholds and the stage thresholds.

## 5. Escalation in the project

The project uses the escalation model of the Guide (§5):

- **Deny.** Automated checks block what is not allowed: a profile that fails the validator, an unsigned commit, a missing AI assistance declaration, a publication from a domain without a reviewer. The block is recorded with its reason.
- **Delegate.** Maintainers and working groups decide two-way doors by lazy consensus.
- **Do.** One-way doors go to the Author (Guide) or the SC (everything else) through an RFC.

## 6. Decision making

### 6.1 Lazy consensus

A proposal in a pull request or issue is accepted if, after the review period, no maintainer of the area has objected with reasons. Review period: 3 working days for ordinary changes, 7 for changes to templates or tools that others depend on (**proposal**). An objection must say what would resolve it.

### 6.2 What needs an RFC

- any change to the Guide text other than typos and broken links;
- a change to applicability levels, project classes or the out-of-scope list;
- a new Role Profile family or a new working group;
- a breaking change to the profile format or to the validator rules;
- changes to licences, trademark policy or this governance (a licence change for existing contributions is limited by §10.1);
- any other decision that a maintainer marks as a one-way door.

RFCs live in the `rfcs/` folder of the `guide` repository; the process is in `guide/rfcs/README.md`.

### 6.3 Who decides an RFC

| RFC subject | Decision |
|---|---|
| Guide | The Author (or co-authors), with written reasons, after the comment period |
| Levels, classes, out-of-scope list | Owning working groups recommend; SC decides by simple majority. Relaxing an exclusion or a level requirement needs two-thirds and a favourable opinion of the security, privacy and legal domain reviewers |
| Other community artifacts | Owning working group by lazy consensus; SC if a maintainer escalates |
| Governance, licences | §10; licence changes for existing contributions also §10.1 |
| Trademark policy | The Steward, after the SC's advice from Stage 2, until the transfer to a foundation |

If the decision maker does not decide within 30 days of the end of the comment period, the RFC is listed as *pending decision* in the next quarterly report. It is never accepted by default.

### 6.4 Voting

Used when consensus fails, for elections and where this document requires it.
- Quorum: two-thirds of eligible voters.
- Simple majority of votes cast, unless stated otherwise.
- Votes are public, except elections of people, which are secret and run by a tool that can be audited.
- Before Stage 2, votes that would fall to the SC are taken by the Steward after consulting the maintainers in public.

### 6.5 Appeals

A contributor may appeal a working group decision to the SC (Steward in Stage 1) within 30 days. The SC answers with written reasons. Guide RFC decisions of the Author are not appealable, but the contributor may submit a new RFC with new evidence after 6 months. The licences also leave everyone free to fork.

## 7. Releases and publication

- Each repository is released as a signed tag with a manifest of file fingerprints.
- A release includes only artifacts whose technical state is closed and whose acceptance is recorded.
- A Role Profile, template or checklist is published only by a domain reviewer of its domain, who is not its author.
- The Guide is published by the Author, with a second reviewer who is not the author of the included changes.
- Release notes separate: what changed, which RFCs were accepted, which profiles were qualified, requalified or suspended.

Reference: the release checklist is in [RELEASING.md](RELEASING.md), and version numbers and tags follow [VERSIONING.md](VERSIONING.md).

## 8. Conflict of interest

- Every role holder keeps a public declaration of employer and of commercial interests related to Eiraman (consulting, training, tools, certification, vendors of products covered by Role Profiles).
- A person does not review, decide or vote on a change in which they or their employer have a direct commercial interest beyond the general use of the method. Example: a vendor employee may author a profile about that vendor's product but may not be its publishing reviewer.
- Conflicts are declared in the pull request or RFC. Undeclared conflicts discovered later reopen the decision.
- No organisation may hold more than the limits in §4.3 and §3.
- Paid certification or training under the Eiraman name requires the trademark policy and does not grant any governance rights.

## 9. Transparency

Decisions, RFCs, votes, meeting notes and the quarterly reports are public. Security reports and Code of Conduct cases follow their own confidentiality rules ([SECURITY.md](https://github.com/eiraman/.github/blob/main/SECURITY.md), [CODE_OF_CONDUCT.md](https://github.com/eiraman/.github/blob/main/CODE_OF_CONDUCT.md)).

## 10. Amending this governance

- Changes are proposed by RFC with a comment period of at least 30 days.
- Stage 1: the Steward decides with written reasons.
- Stage 2 and later: two-thirds of the SC, including the Author's vote when the change affects the Author role or the Guide curation.
- The permanent SC seat and the editorial curation of the Guide by the Author can be changed only with the Author's consent.
- Typos and broken links are ordinary changes.

### 10.1 Limit on licence changes

Contributions are made under the Developer Certificate of Origin: each contributor keeps the copyright and licenses the contribution under the licence of the file at the time of contribution. No vote of the SC, the Steward or the Author can, on its own, change the licence of contributions already made. Relicensing existing material requires the consent of every contributor whose contribution is concerned, or the removal or rewriting of the contributions for which consent is not obtained. A licence decision under §10 applies by itself only to new material.
