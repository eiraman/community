<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Eiraman Contributor Pathways

Status: **draft**. Not yet in force. It depends on the governance drafts and follows their working group and role names.

Eiraman is a method for governing multi-agent AI software development by a non-technical manager. It applies traditional management practice to AI. This page tells you where to start, given what you know.

Each pathway gives:
- the **entry point** (what to read and where to work);
- the **working group** (see [WORKING-GROUPS.md](WORKING-GROUPS.md));
- three **starter issues**, taken from real open points (IDs refer to Starter-issues.md);
- the **quality criterion** that closes a contribution.

Every pathway ends in the same progression to reviewer and maintainer (§9).

## How to read the references

- *Spec 0.3 §n* is the Italian working specification, the historical source until the English Eiraman Guide v1.0 replaces it. Guide section numbers will be added when the Guide table of contents is published.
- *GOV*, *CON*, *WG*, *SEC* are [GOVERNANCE.md](GOVERNANCE.md), [CONTRIBUTING.md](https://github.com/eiraman/.github/blob/main/CONTRIBUTING.md), [WORKING-GROUPS.md](WORKING-GROUPS.md) and [SECURITY.md](https://github.com/eiraman/.github/blob/main/SECURITY.md).
- *Registry* is the Role Profile registry (repository `role-profiles`). It currently has 47 profiles in 8 families, all in state *draft* ("bozza non qualificata"), and the folder names are still in Italian. The English names (`PROFILE.md`, `profile.json`, `FAMILY.md`) are an open point owned by DevSecOps & Tooling (WG §5).
- **Applicability levels are 0, 1 and 2** (Spec 0.3 §10). Level 0 is personal use, level 1 an internal team, level 2 external users. "Raising applicability" means making levels 1 and 2 reachable with evidence and keeping level 0 safe.

## Rules that apply to every pathway

1. **Issue first**, then a pull request with one logical change (CON §1).
2. **Sign off** every commit under the DCO with `git commit -s`. An AI system cannot sign off (CON §2).
3. **Declare AI assistance** in the pull request: `none`, `review`, `partial` or `substantial`, plus the accountable human (CON §3).
4. **Four eyes.** You never review your own change. AI review tools may comment but never count as a reviewer (GOV §1).
5. **Evidence-bound closure.** A contribution closes on an identifiable commit with all mandatory checks passed. A missing check or review keeps it open, with the reason recorded (GOV §1, p. 3).
6. **Three states.** Technical state, acceptance and publication are separate. A merged change is not yet a published one (CON §1).
7. **One-way doors need an RFC** (GOV §6.2). New families, level changes, breaking format changes and Guide text are always RFCs.
8. **No private content.** No client names, credentials, local paths or personal data in any artifact (Registry rule 4). Unsafe guidance and tool vulnerabilities go to [SECURITY.md](https://github.com/eiraman/.github/blob/main/SECURITY.md), never to public issues.
9. **Declare conflicts of interest** (GOV §8). A vendor employee may author a profile about that vendor's product, but may not be its publishing reviewer.

## Choose your pathway

| You are | Pathway | Working group |
|---|---|---|
| A domain expert who wants to write or improve specialist agent roles | [1. Role Profile author](#1-role-profile-author) | A family group, reviewed by a domain group |
| A security professional | [2. Security expert](#2-security-expert-applicability-levels-02) | Security, with Privacy and Legal & Compliance |
| A developer of tools, CI or guards | [3. DevSecOps developer](#3-devsecops-developer) | DevSecOps & Tooling |
| An organisation or person using Eiraman on a real project | [4. Adopter](#4-adopter) | Adoption & Evidence |
| A translator | [5. Translator](#5-translator) | Translation & Education |
| A trainer or educator | [6. Trainer or educator](#6-trainer-or-educator) | Translation & Education |
| A researcher | [7. Researcher](#7-researcher) | Adoption & Evidence |
| A manager without technical background | [8. Non-technical manager as test user](#8-non-technical-manager-as-test-user) | Adoption & Evidence |

---

## 1. Role Profile author

Role Profiles hold the specialist competence of the method. An agent becomes an architect, a developer or a security engineer by loading a qualified profile. The manager therefore does not need specialists on every project (Spec 0.3 §10, "Principio").

**Entry point.**
- Read Spec 0.3 §9 (contents of a profile and maintenance rules), the Registry README (generation rules 1–6) and CON §4 (path and profile states).
- Copy the template folder `_modello/` into `<family>/<profile-id>/` and run the validator before asking for review.
- For an **existing family** (Azure, AWS, Databricks, FinOps, Functional Analysis, Web Design, Development, Governance (Governance & Assurance)), open a *new Role Profile* or *profile change* issue in that family group.
- For a **new family**, open an *RFC proposal*. WG §3 asks for: scope, the first three profiles planned, a lead and a deputy, and the publishing domain. Candidate families:

| Candidate family | Likely publishing domain (proposal) | Points to settle in the RFC |
|---|---|---|
| **GCP** | Cloud Architecture; Security for the security engineer | Mirror of the AWS and Azure families: guard, delegation matrix, tags, regions |
| **SAP** | Application & Data Architecture | Transport and change management as the deterministic guard; licensing limits of the platform; vendor conflict of interest (GOV §8) |
| **Mainframe** | Application & Data Architecture; Test & Quality | Language profiles (COBOL, JCL, PL/I) next to the Development family; batch scheduling as a one-way door |
| **Regulated data** (classification, retention, records, data quality) | Privacy, with Legal & Compliance | Must stay inside classes 0–2. Special category, judicial and children's data, large-scale processing and mandatory DPIA are **out of scope at any level** (Spec 0.3 §10). The family helps projects recognise these cases and stop; it does not open them |
| Others (Kubernetes platform, Salesforce, observability, ITSM) | Per RFC | Same RFC fields |

**Working group.** The family group authors and maintains. The domain group in WG §3 reviews and publishes. A domain without a titular or substitute reviewer cannot publish (GOV §4.5).

**Starter issues.**
- **S01** · RFC: create the GCP family. Source: WG §3 (new families by RFC); GOV §6.2.
- **S02** · Azure family: check the competence areas against the current exam study guides and replace "Azure AD" with "Microsoft Entra ID". Source: Registry `azure/FAMIGLIA.md` §9, which records that the starting material is from the 2021–2022 editions ("unknown, evidence needed").
- **S03** · Declare the publishing domain in `qualificazione.revisore` for the 9 Web Design and Functional Analysis profiles that only say "to be assigned". Align the 5 FinOps profiles that name a "FinOps domain", which does not exist in GOV §4.5, to Cloud Architecture. Source: Registry `profilo.json` files; WG §3 table and §5; Spec 0.3 §9.

**Quality criterion that closes a contribution.**
- The validator passes on the folder, and the Section 10 catalogue is regenerated by the activation tool.
- Every rule cites a precise source (clause, section, page). A rule without one is marked "profile convention". Uncalibrated thresholds are "to be calibrated" and unknowns are "unknown, evidence needed" (Registry rules 2–3).
- The qualification suite has at least 5 known-answer cases. At least one is a hostile instruction that must produce a recorded Deny (Spec 0.3 §7, mandatory negative test). Results are attached for every enabled engine.
- The LLM pre-evaluation did not reject it, or a domain reviewer overruled the rejection in writing (CON §4.1, step 6).
- A family maintainer who is not the author reviewed it. The profile becomes *qualified* only when a domain reviewer who is not the author publishes it with curator, reviewer, qualification date and expiry.

---

## 2. Security expert (applicability levels 0–2)

Eiraman lets a non-technical manager run AI agents only on projects whose class does not exceed the adopter's qualified level. Today only level 0 is defined in practice. Levels 1 and 2 have requirements but no calibrated thresholds and no evidence base (Spec 0.3 §10, "Punti aperti"). Security experts make the levels trustworthy.

**Entry point.**
- Read Spec 0.3 §7 (agent execution and security), §10 (classes, out-of-scope list, gate, requirements per level, step-up and automatic step-down) and §3 (Deny, Delegate, Do; pre-authorised containment).
- Read SEC §3: unsafe guidance in profiles is a security issue, reported privately.
- Work in the `framework` repository (detailed levels, gate checklist). Changes to level requirements, classes or the out-of-scope list are RFCs decided by the SC on recommendation of Security, Privacy and Legal & Compliance. Relaxing a requirement needs two-thirds and a favourable opinion of the three domain reviewers (GOV §6.3).

**Working group.** Security, with Privacy and Legal & Compliance as co-reviewers.

**Areas of work.**
- **Threat model of agents.** Roles, tools, network destinations, readable data, irreversible actions, prompt injection, tool misuse, excessive agency, supply chain of models and profiles. Baseline: OWASP Top 10 for LLM and agentic applications, as Spec 0.3 §7 requires.
- **Mapping to external frameworks**, informative and never normative:
  - NIST SSDF (SP 800-218), practice groups PO, PS, PW and RV;
  - NIST AI RMF 1.0, functions Govern, Map, Measure and Manage, and its Generative AI profile;
  - ISO/IEC 42001 (AI management system), clauses 4–10 and Annex A controls;
  - EU AI Act: Art. 5 (prohibited practices) and Art. 6 with Annex III (high risk), both out of scope; Art. 50 (transparency), a gate requirement.
- **Evidence for level 1**: the deliberately vulnerable test suite and its detection threshold.
- **Gate checklist** (with Legal & Compliance and Privacy). It blocks level 0 itself.

**Starter issues.**
- **S04** · Threat model template for the "Agents" section of the Security Risk Posture: per role, the allowed tools, network destinations, readable data and irreversible actions, mapped to OWASP Top 10 for LLM and agentic applications. Source: Spec 0.3 §7, "Sicurezza degli agenti e tracciabilità".
- **S05** · Informative mapping of level 0–2 requirements to NIST SSDF, NIST AI RMF, ISO/IEC 42001 and the EU AI Act, with gaps listed. Source: Spec 0.3 §10, "Requisiti per livello"; GOV §2 (levels owned by Security).
- **S06** · Design the deliberately vulnerable test suite and propose its detection threshold for the first step up to level 1. Source: Spec 0.3 §10, level 1 evidence and "Punti aperti" row 1; WG §2 (Security owns the suite).

Next: **S25**, the first version of the gate checklist (Spec 0.3 §10, "Punti aperti" row 3).

**Quality criterion that closes a contribution.**
- Every requirement or mapping row cites the clause of its source and the version of the standard.
- Each proposed requirement is testable: it states the evidence that proves it and who produces it (AI Coordinator, external service, Human Manager).
- Mappings are marked *informative*. A change to a level goes through an RFC with co-review by Privacy and Legal & Compliance.
- Nothing in the contribution relaxes an exclusion or a level requirement without the vote required by GOV §6.3.
- Any exploitable weakness found in existing guidance went through SEC §3, not a public issue.

---

## 3. DevSecOps developer

The method relies on deterministic tools: the environment, not the agent, enforces a Deny (Spec 0.3 §3). Today the project has a profile validator, an activation tool that writes the catalogue and configuration files, and a manager view. CI is designed but not implemented, and the guard each cloud family requires has no reference implementation.

**Entry point.**
- Read Spec 0.3 §3 (Deny), §6 ("DevSecOps e test"), §7 (execution records: run ID, profile hash, exact model ID, configuration, Unit Cost, SBOM) and the Registry README.
- Read the family files that require a guard: `azure/FAMIGLIA.md` §2, `databricks/FAMIGLIA.md` F8 and `aws/FAMIGLIA.md`.
- Work in the `tools` repository (code under Apache 2.0). Security-sensitive changes (signing, secrets, CI permissions) also need a Security reviewer (WG §4).

**Working group.** DevSecOps & Tooling.

**Starter issues.**
- **S07** · Validator: support the English file names (`PROFILE.md`, `profile.json`, `FAMILY.md`) and the four profile states, *draft*, *qualified*, *maintained* and *suspended*, with automatic suspension when `qualificazione.scadenza` has passed. Source: WG §5; CON §4.2.
- **S08** · Unit tests and fixtures for the validator and the activation tool. The repository has no test suite for its own tools. Source: Repository plan §4 ("Test and static analysis" for `tools`); CON §1, step 4.
- **S09** · Reference implementation of the deterministic guard for one cloud CLI. Required: dry-run mode, inputs (role, environment, cost estimate, approved Do reference), delegation matrix, an append-only log and a recorded reason for each Deny. Source: `azure/FAMIGLIA.md` §2; `databricks/FAMIGLIA.md` F8; Spec 0.3 §3 and §7.

Next:
- a qualification suite runner (the validator only counts cases, it does not execute them);
- the CI workflows of the Repository plan §4 (DCO, REUSE, validator, secrets, links, reproducible site build), with actions pinned by hash;
- a check that each profile references its family file.

**Quality criterion that closes a contribution.**
- Tests cover the change, including a negative case. CI is green on the final commit.
- No new dependency without a recorded licence and version pin. No secrets, no organisation-specific terms in code (generic patterns only).
- Breaking changes to the profile format or validator rules have an accepted RFC (GOV §6.2).
- Two maintainers of the group reviewed it, one not the author. Changes to signing, secrets handling or CI permissions also have a Security reviewer.
- A guard is documented as **a trace and an alarm, not an access control**: the real control stays on the platform side (RBAC, IAM, policies, budgets), as the family files require.

---

## 4. Adopter

Adopters make the method mature. Their anonymised evidence calibrates the level thresholds and counts toward the stage thresholds of the project (GOV §3: S2.4 and S3.4).

**Entry point.**
- Read Spec 0.3 §10 (pick your class and level; most adopters start at level 0) and §11 (project card, partial application, return to method).
- Open an *adopter case* issue to register. A declared adopter states the level and agrees to share anonymised evidence (GOV §4.9).
- Use the [case study template](CASE-STUDY-TEMPLATE.md). Remove personal data and client names before submitting.

**Working group.** Adoption & Evidence. A Privacy reviewer reviews any evidence derived from a real project.

**Starter issues.**
- **S10** · Publish a level 0 case study with the case study template. Source: WG §4 (case study template, adopter register); GOV §4.9.
- **S11** · Contribute an escalation sample: about 20 autonomous decisions reviewed by the manager, giving the under- and over-escalation counts. Source: Spec 0.3 §3, rule E6; §10, "Punti aperti" row 1.
- **S12** · Turn one retrospective finding into a return-to-method proposal: reproducible case, rule applied, outcome, cost, and origin (data, application, environment or method). Source: Spec 0.3 §11, "Ritorno al metodo".

**Quality criterion that closes a contribution.**
- The case study has every mandatory field filled in, or marked "unknown, evidence needed". No invented numbers.
- It passes the anonymisation rules of the template, confirmed by a Privacy reviewer.
- The contributor confirms the right to share the evidence under the rules of their organisation.
- Two maintainers of Adoption & Evidence accepted it, one not the contributor.
- A product that embeds only parts of the method carries a partial conformity declaration (Spec 0.3 §11).

---

## 5. Translator

English is canonical from Guide v1.0. Italian is a curated translation, and the Italian Spec 0.3 remains the historical source. Most material is still in Italian, so the first job is to bring it into English.

**Entry point.**
- Start from the glossary, then the Role Profile template, then the family files.
- Work in `guide` (translations of the Guide) or `role-profiles` (profiles and family files).
- Guide translations are derivatives under CC BY-SA 4.0; profiles are under CC BY 4.0.

**Working group.** Translation & Education.

**Starter issues.**
- **S13** · Italian–English glossary of core terms: Deny/Delegate/Do, one-way and two-way doors, Wave, Work Package, Digital Seniority, AI Coordinator, Human Manager, Security Risk Posture, Unit Cost, drift budget. Source: WG §4 (glossary owned by the group).
- **S14** · English version of the profile template `_modello/PROFILO.md`, keeping the section order. Renaming JSON keys is a format change, so coordinate it with S07. Source: WG §5; Registry README.
- **S15** · English `FAMILY.md` for the Development family (`sviluppo/FAMIGLIA.md`). Source: WG §3 (`FAMIGLIA` to be renamed `FAMILY.md`).

**Quality criterion that closes a contribution.**
- Glossary terms are used consistently. A new term is added to the glossary in the same pull request.
- Meaning is preserved, including every source citation and every "to be calibrated" or "unknown" marker.
- Two native-speaker reviewers of the target language reviewed it, one not the translator. For the Guide, the Author also approves the translation as faithful (WG §4).
- Translations are labelled informative. The English text prevails.

---

## 6. Trainer or educator

**Entry point.**
- Read Spec 0.3 §1–§3 (principle: traditional management applied to AI; responsibilities; escalation), §5 (Waves) and §10 (gate).
- Read the trademark policy before using the Eiraman name in a course. Paid training under the name requires the policy and grants no governance rights (GOV §8).
- Work in the `community` repository (curricula) or in `framework` (exercises tied to templates).

**Working group.** Translation & Education.

**Starter issues.**
- **S16** · Module "Escalation 3D for managers": Deny, Delegate, Do, reversibility as the criterion, "silence never approves", with three exercises and an answer key. Source: Spec 0.3 §3.
- **S17** · Exercise set on the applicability gate: ten fictional projects to classify into class 0, 1 or 2, or out of scope, with an answer key reviewed by Privacy and Legal & Compliance. Source: Spec 0.3 §10, "Classi di progetto" and "Fuori perimetro".
- **S18** · Workshop outline "Write your first Role Profile": template, sources, suite, validator, four eyes. Source: Spec 0.3 §9; Registry rules 1–6; CON §4.1.

**Quality criterion that closes a contribution.**
- Learning objectives are mapped to sections of the Guide (Spec 0.3 until v1.0). No rule is invented or changed in training material.
- Exercises have answer keys that cite the section that justifies each answer.
- No claim of certification or official endorsement unless the trademark policy allows it.
- Two reviewers of the group accepted it, one not the author. Answer keys on classes, privacy or law were co-reviewed by the relevant domain.

---

## 7. Researcher

Several thresholds of the method are explicitly uncalibrated. Researchers turn adopter evidence into numbers the community can decide on.

**Entry point.**
- Read Spec 0.3 §3 (rules E4–E6), §7 (traceability: LLM output is not deterministically reproducible), §9 (requalification after model changes) and §10, "Punti aperti".
- Datasets come from adopters through Adoption & Evidence and are anonymised before analysis.

**Working group.** Adoption & Evidence (WG §4: researchers contribute through it).

**Starter issues.**
- **S19** · Measurement protocol for under- and over-escalation across adopters, with an anonymised dataset schema and a sampling method. Source: Spec 0.3 §3, rule E6; §10, "Punti aperti" row 1.
- **S20** · Metric for "behaviour differences" when a qualification suite is rerun after a model change, so a reviewer can requalify or suspend on evidence. Source: Spec 0.3 §9 (maintenance rules); §7 (profile hash and exact model ID per run).
- **S21** · Method to calibrate Unit Cost per engine and Digital Seniority level. 198 Unit Cost values in the Registry are "to be calibrated". Source: Registry `profilo.json` (`unit_cost`); `_seniority/SENIORITY.md` point 6; Spec 0.3 §9.

Next: local versus external LLM request strategies on the same load (quality, latency, cost, data constraints), Spec 0.3 §6 bis; agreement rates of the escalation classifier built on a different model, Spec 0.3 §3, E4.

**Quality criterion that closes a contribution.**
- The protocol is written before the analysis. Data sources, sample sizes and limitations are stated.
- Data and analysis scripts are shareable and contain no personal data. The Privacy reviewer approved the dataset schema.
- Results are a **proposal** to the owning group. A threshold becomes binding only through the decision path in GOV §6.3.
- Two maintainers of Adoption & Evidence accepted it, one not the author. Conflicts of interest (funding, vendors) are declared.

---

## 8. Non-technical manager as test user

The method is written for you. If you cannot use it without technical help, that is a defect of the method, not of you.

**Entry point.**
- Read Spec 0.3 §1 (what Eiraman is), §2 (who answers for what) and §3 (what reaches you as a Do).
- Pick one task and do it as a manager would. Write down where you got stuck, what word you did not understand, and what decision you could not take.
- Report with a *bug in tools* issue (for the manager view) or an *adopter case* issue. No technical skill is needed.

**Working group.** Adoption & Evidence, with Translation & Education for wording.

**Starter issues.**
- **S22** · Walk through the manager path with the Manager View and report the friction: open a project, grant the mandate, decide an exception, consult evidence, accept the result. Source: Spec 0.3 §10, "Punti aperti" row 4 (interface for the Human Manager); §11 ("Il metodo come progetto", Manager View).
- **S23** · Read a sample Do and say whether impact, options, recommendation, evidence, deadline and the effect of no answer are clear without technical knowledge. Source: Spec 0.3 §3, "Do".
- **S24** · Plain-language check of the level 0 manager documents: project card, decision cards, governance cycle review, installation and use manual. Source: Spec 0.3 §10, "Livello 0".

**Quality criterion that closes a contribution.**
- The report names the task, the step, what you expected and what happened. A screenshot or quote is enough as evidence; remove any personal data.
- Each finding is classified as *wording*, *missing information* or *missing decision support*.
- A maintainer reproduced or confirmed the finding and linked it to a follow-up issue. The finding closes when the follow-up is accepted, not when the report is read.

---

## 9. Progression to reviewer and maintainer

The same ladder applies to every pathway (GOV §4). Numbers marked **proposal** are still to be decided.

| Step | How you get there | What you gain | How it ends |
|---|---|---|---|
| **Contributor** | Open an issue, comment, review or propose a change, with DCO sign-off and AI assistance declaration | Listed in release notes | — |
| **Reviewer** of an area | Nominated by a maintainer of the area after substantive reviews; lazy consensus (GOV §4.7) | Your review counts toward four eyes for non-publishing changes | Resignation or 12 months of inactivity |
| **Maintainer** of an area | Nominated by a maintainer after a sustained record, for example at least 5 accepted contributions or 10 substantive reviews in 6 months (**proposal**); lazy consensus of the area's maintainers; meet the group's entry criteria (WG §2–§4) | Merge rights in the area (MAINTAINERS.md, CODEOWNERS); vote in SC elections | Resignation; 12 months of inactivity (emeritus); removal by the SC with written reasons |
| **Domain reviewer** (titular or substitute) | Proposed by the domain group with evidence of expertise (professional practice, certifications, published work or accepted reviews); appointed by the Steward in Stage 1, later the SC (GOV §4.5) | Publishes Role Profiles, templates and the gate checklist of the domain in signed releases | Resignation; 90 days without answering review requests; SC decision with reasons |
| **Working group lead or deputy** | Elected by the group's maintainers for 1 year; the Steward appoints the first ones (GOV §4.4) | Runs the backlog and the quarterly report; proposes reviewers and maintainers | End of term, resignation, 90 days of inactivity |
| **Steering Committee member** | Elected by maintainers from Stage 2 (GOV §3, §4.3) | Strategy, one-way doors outside the Guide, appeals | End of term, resignation, removal |

Typical ladders per pathway:
- **Role Profile author:** family reviewer, then family maintainer, then domain reviewer of the publishing domain.
- **Security expert:** Security reviewer, then Security domain reviewer. Privacy and Legal & Compliance follow the same ladder in their domains.
- **DevSecOps developer:** DevSecOps & Tooling reviewer, then maintainer of `tools` or `site`.
- **Adopter, researcher, manager test user:** Adoption & Evidence reviewer, then maintainer (the entry criterion is a declared adopter or researcher with an accepted case study or analysis).
- **Translator, trainer:** Translation & Education reviewer for a language or curriculum, then maintainer.

Every role holder keeps a public declaration of employer and commercial interests (GOV §8). Domain reviewers answer for the correctness of what they publish against its sources at the time of review, not for the projects that use it (Spec 0.3 §9).

## 10. Open points

- Guide section numbers replace Spec 0.3 references when the Guide table of contents is published (package GUIDE-CORE).
- Candidate families (GCP, SAP, mainframe, regulated data) and their publishing domains are proposals until an RFC is accepted.
- Repository names (`guide`, `framework`, `role-profiles`, `tools`, `site`, `community`) follow the repository plan and are not created yet.
