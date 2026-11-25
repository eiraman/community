<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Eiraman Working Groups Charter

Status: **draft**. Values marked **proposal** are to be decided.

Working groups (WGs) do the work of the community. Roles, elections and decision rules are in [GOVERNANCE.md](GOVERNANCE.md). This charter says what each group owns.

## 1. Common rules

- **Lead and deputy.** Every group has a lead and a deputy (GOVERNANCE §4.4). A group is *active* when it has both, at least one accepted contribution and one public report in the last 90 days.
- **Four eyes.** The author of a change is never its reviewer, in every group.
- **Reviewer rule.** Each group states who must review what it owns. Where a group publishes Role Profiles, templates or checklists, publication is by a domain reviewer of the relevant domain (see §2 and GOVERNANCE §4.5), never by the author.
- **Evidence-bound closure.** A contribution is closed on an identifiable candidate with all mandatory checks passed. A missing review or check keeps it open.
- **Entry criteria.** Anyone may join a group's discussions. Entry criteria below apply to becoming a reviewer or maintainer in that group.
- **Reports.** Each active group publishes a short quarterly report: work accepted, profiles qualified, requalified or suspended, open decisions, health.
- **Creation and closure.** New groups are created by RFC. A group inactive for 6 months (**proposal**) is put on hold by the SC (Steward in Stage 1) and its artifacts move to a named group.

Groups are of three kinds:
- **Domain groups** (§2) provide the titular and substitute reviewers of the six domains of GOVERNANCE §4.5 and own cross-cutting rules of their domain.
- **Family groups** (§3) author and maintain the Role Profiles of one family.
- **Cross-cutting groups** (§4) own tooling, evidence and education.

## 2. Domain groups (GOVERNANCE §4.5)

Each domain group has exactly one **titular reviewer** and one **substitute reviewer**, preferably from different organisations. A domain without a reviewer cannot publish profiles. When both are unavailable, publications in that domain stop and the gap is recorded in the quarterly report.

| Group | Scope | Artifacts owned | Reviewer rule | Entry criteria (reviewer) |
|---|---|---|---|---|
| **Cloud Architecture** | Architecture of cloud solutions across providers; reference architectures; cost-aware design | Review and publication of cloud architect, operations and FinOps profiles; cloud parts of templates | Titular or substitute publishes; a vendor employee does not publish profiles of that vendor's products (GOVERNANCE §8) | Professional practice in cloud architecture, evidence of at least one accepted review in the group |
| **Security** | Secure development, agent security, applicability levels above 0 | Requirements of applicability levels (with Privacy and Legal); security parts of profiles; security engineer profiles; the deliberately-vulnerable test suite of the level requirements in the community-maintained sections of the Guide (§14) | Titular or substitute; changes that relax a level requirement also need Privacy and Legal reviewers and an SC vote (GOVERNANCE §6.3) | Professional security practice (for example penetration testing, secure architecture, incident response); accepted reviews |
| **Application & Data Architecture** | Application structure, composable architecture, data platforms, databases | Review and publication of developer, data engineering, DBA and analytics profiles; architecture document templates | Titular or substitute | Professional practice in software or data architecture; accepted reviews |
| **Test & Quality** | Testing strategy, qualification suites, DevSecOps quality gates | Rules for qualification suites; review of tester profiles; quality parts of all profiles; requalification after model changes | Titular or substitute; reviews the suite of every profile before its first qualification | Professional practice in testing or quality engineering; accepted reviews |
| **Privacy** | Personal data protection in projects and in Role Profiles | Privacy parts of levels and of the gate checklist; DPIA screening rules; privacy guidance in profiles | Titular or substitute; mandatory co-review of any change touching project classes or personal data | Professional practice in data protection (for example DPO, privacy counsel, privacy engineering); accepted reviews |
| **Legal & Compliance** | Regulatory and licensing aspects of the method | The **gate checklist** (Guide §14), its exclusion criteria and requirements; legal parts of templates; review of licence and DCO questions with the Steward or SC | Titular or substitute; checklist releases also need a Privacy reviewer. The checklist never replaces legal advice | Legal or compliance practice relevant to software and AI regulation; accepted reviews |

## 3. Family groups (Role Profiles)

Each family group authors and maintains the Role Profiles of one family, including its `FAMIGLIA` file of common rules (to be renamed `FAMILY.md` in the English registry). Family groups do not publish: they hand qualified candidates to the domain group(s) in the table. The domain mapping is a **proposal**.

| Group | Scope | Artifacts owned | Reviewer rule (publishing domain) | Entry criteria (maintainer) |
|---|---|---|---|---|
| **Azure** | Azure roles: architect, developer, release engineer, security engineer, DBA, incident and problem manager, cloud operations | Azure family file and profiles, their qualification suites | Cloud Architecture; Security for the security engineer; Application & Data for developer and DBA | Accepted profile contribution plus practice on the platform |
| **AWS** | AWS roles: architect, developer, DevOps engineer, security engineer, database specialist, operations | AWS family file and profiles, suites | As Azure | As Azure |
| **Databricks** | Data engineer, platform administrator, data governance steward, ML engineer, analytics engineer | Databricks family file and profiles, suites | Application & Data Architecture; Privacy for the governance steward | Accepted profile contribution plus platform practice |
| **FinOps** | FinOps practitioner, cost allocation, rate optimisation, FinOps for AI, forecast and budget | FinOps family file and profiles, suites; Unit Cost guidance shared with DevSecOps & Tooling | Cloud Architecture (no FinOps domain exists in GOVERNANCE §4.5, see open points) | Accepted profile contribution plus FinOps practice |
| **Functional Analysis** | Functional analyst, Design Thinking facilitator, simulated user, functional tester, technical writer | Family file and profiles, suites; functional document templates | Test & Quality; Application & Data for the analyst | Accepted profile contribution plus analysis practice |
| **Web Design** | Web designer, UX designer, accessibility specialist, UX writer, frontend developer | Family file and profiles, suites | Application & Data Architecture; Test & Quality for accessibility | Accepted profile contribution plus design or accessibility practice |
| **Development** | Language developers (Python, TypeScript, Java, .NET, Go, SQL, shell and IaC), shared by cloud profiles | Family file and profiles, suites | Application & Data Architecture; Security for IaC and shell | Accepted profile contribution plus language practice |

A new family is created by RFC with: scope, first three profiles planned, a lead and deputy, and the publishing domain.

## 4. Cross-cutting groups

| Group | Scope | Artifacts owned | Reviewer rule | Entry criteria (maintainer) |
|---|---|---|---|---|
| **DevSecOps & Tooling** | Deterministic tools of the method and the project's own pipeline | Profile validator, activation tool, Digital Seniority map, CI, release signing and manifests, site generator; mandatory deterministic tools listed in profiles (integration) | Two maintainers of the group, one not the author; Security reviewer for changes to signing, secrets handling or CI permissions | Accepted code contributions; knowledge of secure CI |
| **Adoption & Evidence** | Adopters, case studies, measurement | Adopter register; case study template; anonymised evidence for level thresholds (under-escalation, vulnerability suite detection, operation periods); stage threshold report | Two maintainers; Privacy reviewer for any evidence derived from real projects | Declared adopter or researcher with an accepted case study or analysis |
| **Translation & Education** | Translations of the Guide and profiles; training materials | Translations (English canonical, translations informative); glossary; training curricula under the trademark policy | Two native-speaker reviewers per language, one not the translator; the Author approves Guide translations as faithful | Accepted translation or training contribution |

Researchers contribute through Adoption & Evidence. Trainers contribute through Translation & Education.

## 5. Open points

- GOVERNANCE §4.5 lists six domains. FinOps, UX and accessibility have no domain of their own; they are mapped above to existing domains. A new domain needs an RFC (GOVERNANCE §6.2).
- The English registry needs English file names (`PROFILE.md`, `profile.json`, `FAMILY.md`) and the validator needs the new states (draft, qualified, maintained, suspended). Owner: DevSecOps & Tooling.
