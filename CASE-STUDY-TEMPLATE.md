<!--
SPDX-FileCopyrightText: 2026 Paolo Ungari and contributors
SPDX-License-Identifier: CC-BY-4.0
-->

# Eiraman Case Study Template

Status: **draft**. Owner: Adoption & Evidence working group.

Use this template to share how Eiraman worked on a real project. Anonymised case studies calibrate the open thresholds of the applicability levels (Spec 0.3 §10, "Punti aperti"). They also count toward the stage thresholds of the project (GOVERNANCE §3).

Submit it with the *Adopter case* issue form. A Privacy reviewer checks every case derived from a real project before it is accepted.

**Writing rules.**
- Fill in every field. If a value was not measured, write **"unknown, evidence needed"**. Never estimate silently, and never write zero for an unmeasured cost.
- Numbers state their unit and their denominator.
- Facts state their basis: *log*, *project file*, *manager's record* or *estimate*.

---

## Anonymisation rules (apply before writing)

The submitter is responsible for anonymisation. The Privacy reviewer verifies it.

1. **No client or employer names.** Use a neutral label ("Organisation A", "a mid-size retailer"). Do not name products, brands or internal systems that identify the organisation.
2. **No personal data.** No names, emails, user IDs, handles, photos, voices or job titles that identify a person. Refer to people by role: *Human Manager*, *business owner*, *external pen tester*.
3. **No secrets.** No credentials, tokens, keys, connection strings, internal URLs, IP addresses, account or subscription IDs, or local file paths.
4. **No re-identification by combination.** Generalise details that together identify the organisation: exact dates become month and year, exact headcounts become ranges, exact locations become regions, rare technologies become their category.
5. **Quotes and logs** are paraphrased or redacted. Replace redacted content with `[redacted: <kind>]`.
6. **Costs** may be given as ranges or as Unit Cost if absolute figures are confidential. State which.
7. **Incidents** are described by type and impact, never in a form that helps an attacker. An unresolved vulnerability goes to SECURITY.md, not into a case study.
8. **Rights.** You confirm you may share the case under your organisation's rules. Once accepted, the case is published under the licence of the `community` repository.

---

## 1. Identification

| Field | Value |
|---|---|
| Case label | <neutral label, e.g. "Case 2027-03 · internal reporting tool"> |
| Sector | <category, e.g. retail, public administration, education> |
| Organisation size | <range> |
| Period | <from month/year to month/year> |
| Eiraman version | <Guide version; Role Profiles release; tools version> |
| Submitter role | <e.g. Human Manager, Coordinator of the adoption> |

## 2. Project class and level

| Field | Value |
|---|---|
| Project class (0, 1 or 2) | |
| Qualified level of the adoption (0, 1 or 2) | |
| Gate result | <class assigned; requirements triggered (e.g. AI Act Art. 50 transparency); exclusion criteria checked> |
| Gate runs | <at opening, per Wave, at mandate changes: how many> |
| Class changes during the project | <none, or from-to, why, and the Human Manager's choice> |
| Level changes | <step-up with dossier, or automatic step-down and the cause> |
| Partial application | <full method, or the partial conformity declaration: rules applied and not applied (Spec 0.3 §11)> |

## 3. Mandate

| Field | Value |
|---|---|
| Objective and success criteria | |
| Deliverables in scope | |
| Delegations (what AI roles decide alone) | |
| Reservations (what always reaches the Human Manager) | |
| Data classes per provider | <which providers allowed for which data class> |
| Budget and drift budget | |
| Pre-authorised containment actions | |
| Mandate revisions | <number and reason> |

## 4. Waves

| Wave | Objective | Work Packages (planned / closed / open) | Duration | Outcome |
|---|---|---|---|---|
| 1 | | | | |

Roles used, with Digital Seniority levels: <Role Profile id and version; state (draft/qualified); SD levels used>

## 5. Escalations by type

| Type | Count | Notes |
|---|---|---|
| **Deny** (blocked by the environment) | | <main reasons; any attempt to bypass> |
| **Delegate** (two-way doors decided by AI roles) | | <share recorded as micro-decisions> |
| **Do**, ordinary | | <median time to answer> |
| **Do**, urgent | | |
| Do reminders and missed deadlines | | <packages that left a Wave for a missing decision> |
| Mandatory negative test (hostile input to recorded Deny) | <passed / failed / not run> | |

**Calibration sample (rule E6).** Size of the sample of autonomous decisions reviewed by the Human Manager (about 20 suggested):

| Measure | Numerator / denominator | Rate |
|---|---|---|
| Under-escalation (reserved decisions not raised / all reserved decisions) | | |
| Over-escalation (Do that fell within delegations / all Do) | | |
| Classifier disagreements (rule E4) raised to the manager | | |

## 6. Human interventions

Every time a human acted outside the expected path of the method.

| # | Who (role) | What | Why | Could the method have avoided it? |
|---|---|---|---|---|
| 1 | | | | |

## 7. Cost

| Item | Value | Basis |
|---|---|---|
| AI engines (by engine) | | |
| Unit Cost per Work Package (by engine and SD level) | | |
| Human time (Human Manager; reviewers; others) | <hours> | |
| External services (pen test, certified providers) | | |
| Infrastructure | | |
| Total, with unknown items counted | <"complete" or "incomplete: N items unknown"> | |

## 8. Deliverables

| Deliverable | Class | Accepted / rejected / reworked | Technical state at acceptance | Reason for rejection or rework |
|---|---|---|---|---|
| | | | | |

Technical state and business acceptance are reported separately. A deliverable accepted with open findings says so.

## 9. Incidents

| # | Type (security, privacy, availability, cost, quality) | Severity | Detected by (guard, test, reviewer, user) | Containment | Time to contain | Postmortem |
|---|---|---|---|---|---|---|
| | | | | | | |

"None" is a valid answer only if incident detection was in place. Otherwise write "unknown, evidence needed".

## 10. Lessons and return to the method

| Lesson | Origin (data, application, environment, method) | Reproducible case | Proposal | Issue or RFC |
|---|---|---|---|---|
| | | | | |

What would you do differently? What should the method change (Spec 0.3 §11, "Ritorno al metodo")?

## 11. Submitter confirmations

- [ ] All anonymisation rules applied
- [ ] I have the right to share this case under my organisation's rules
- [ ] Unmeasured values are marked "unknown, evidence needed"
- [ ] AI assistance in writing this case is declared in the pull request (CONTRIBUTING §3)
