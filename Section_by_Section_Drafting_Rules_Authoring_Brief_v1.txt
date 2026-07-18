# Section-by-Section Drafting Rules — Authoring Brief v1

Status: Handoff brief for Microsoft 365 Copilot  
Companion control document: `LP_Investment_Memo_Template_Schema_v1.md`  
Primary objective: Use approved historical investment memos and their corresponding source packages to produce a detailed, evidence-based `Section-by-Section Drafting Rules` document for an LP-side investment memo drafting agent.

## 1. What this assignment is

The companion `Memo Template Schema` defines **what the final memo must contain**: the section order, required and conditional sections, standard fields, and internal information slots.

This assignment must produce a second control document explaining **how the agent should complete every section**. For each section, the finished rules must tell the production agent:

- What business question the section answers.
- Which source types and folders it should search.
- Which search terms, document labels, and metadata are useful.
- What facts, claims, observations, and analytical elements it must extract.
- How it should normalize names, dates, percentages, currencies, roles, and legal terms.
- What to do when sources conflict or contain different versions.
- How to distinguish current-fund facts from predecessor-fund history.
- How to distinguish GP assertions from FM observations and LP-side conclusions.
- How to convert extracted evidence into the expected memo format and tone.
- What to do when information is missing or confidence is low.
- What quality-control tests must pass before the section is considered complete.

The resulting rules should operate like a detailed training and operating manual for an analyst or AI agent. They are not a summary of the sample memos and must not import sample-fund facts into future memos.

## 2. Required input materials

Microsoft 365 Copilot should be connected only to folders and files authorized by the user. Before drafting rules, confirm access to the following categories.

### A. Control documents

- `LP_Investment_Memo_Template_Schema_v1.md`
- This `Section-by-Section Drafting Rules — Authoring Brief v1`
- Current approved FM memo template, preferably in editable Word format
- Any FM investment-writing or formatting guidelines
- Any internal glossary defining FM entities, investment vehicles, fund terms, or approval terminology

### B. Approved historical outputs

Use a curated set of high-quality, approved final investment memos. Ideally include different GPs and strategies so the rules capture true structural commonalities rather than one manager's facts.

For every historical memo, record:

- GP / firm name.
- Fund / opportunity name.
- Memo date.
- Strategy type.
- Whether the memo is final and approved.
- Which sections are present or absent.
- Whether the memo contains reviewer edits or tracked changes.

### C. Corresponding historical source packages

Whenever possible, each approved memo should be paired with the source folder from which it was prepared, including:

- Meeting notes.
- Teams meeting recaps or transcripts.
- Calendar records, where appropriate.
- Email follow-ups containing substantive diligence information.
- DDQ and supplemental DDQ responses.
- PPM and fundraising presentation.
- LPA, draft LPA, term sheet, side letter, subscription documents, and legal summaries.
- Fund model, performance schedules, portfolio materials, and track-record files.
- Organizational charts, biographies, team rosters, and key-person materials.
- Strategy, value-creation, operating-team, and investment-process materials.
- FM internal records identifying the investment entity, legal vehicle, contact, approvals, or relationship history.

### D. Current deal package for later testing

Do not use the current deal to invent methodology. After the rules are drafted from approved historical examples, use one current or held-out historical deal package to test whether the rules can be applied without relying on memorized facts.

## 3. Important data-boundary rules

- Historical memos are examples of structure, tone, selection, and analytical depth. They are not authoritative sources for a new fund's facts.
- Current-deal facts must come from the user-identified current-deal folder and approved internal records.
- Do not mix information among GPs, fund vintages, parallel vehicles, co-investments, or predecessor funds.
- Do not use public web information unless the user explicitly authorizes it. If web information is authorized, label it separately and do not let it override current confidential legal or diligence documents.
- Respect existing Microsoft 365 permissions and sensitivity restrictions.
- Never infer missing legal names, email addresses, legal entities, percentages, dates, approval thresholds, or attendee lists.
- Do not treat a calendar invitation as proof of actual attendance without corroboration.
- Do not treat a GP statement or marketing claim as an independently established fact.

## 4. Required research workflow

### Phase 1 — Access and corpus inventory

Before writing any drafting rule:

1. Confirm that both control documents are accessible.
2. List every connected historical memo and source package.
3. Identify which historical memo is paired with which source folder.
4. Identify missing source packages, duplicate versions, draft memos, and potentially outdated files.
5. Confirm which memos are approved examples and which should be excluded.
6. Produce a short `Corpus Readiness Report`.

Do not proceed silently if the historical memos cannot be paired with their underlying documents. Rules derived only from final memos would describe output style but not reliable retrieval behavior.

### Phase 2 — Reverse-map each historical memo to its sources

For each required memo section:

1. Break the final section into its component facts and analytical statements.
2. Locate the likely underlying source for each component.
3. Record the exact document name, document type, date / version, and page / section / meeting locator when available.
4. Classify each component as:
   - Documented fact.
   - GP statement or representation.
   - FM meeting observation.
   - Calculation.
   - LP-side inference or assessment.
5. Identify which facts consistently appear in the same type of source across multiple deals.
6. Identify statements that cannot be traced to source materials and flag them rather than using them to create a rule.

### Phase 3 — Discover common drafting patterns

Across multiple approved memos, determine:

- Which information slots appear consistently.
- Which slots vary by strategy or GP.
- Which sections are always required.
- Which headings or sub-sections are conditional.
- Common sentence patterns and table formats.
- Typical level of compression and detail.
- How FM writers distinguish facts, GP statements, observations, and assessments.
- Common reviewer corrections, if tracked changes or comments are available.
- Common failure modes, omissions, inconsistencies, or unsupported conclusions.

### Phase 4 — Draft rules section by section

Draft one section at a time using the standard rule template in Section 5 of this brief. Do not write a single broad instruction such as `review all files and summarize`; the rules must be operational and testable.

### Phase 5 — Validate rules against historical deals

For at least two historical source packages:

1. Apply the drafted rules without using the final memo as a factual source.
2. Produce an evidence map or draft section.
3. Compare the result with the approved final memo.
4. Identify:
   - Missing facts.
   - Incorrect facts.
   - Unsupported additions.
   - Structural differences.
   - Tone or analytical differences.
   - Information that could not be located.
5. Revise the rules based on the results.

### Phase 6 — Finalize the rules document

The completed document should be titled:

`LP Investment Memo — Section-by-Section Drafting Rules v1`

It must include a version date, corpus used for calibration, known limitations, unresolved questions, and a recommended test plan.

## 5. Standard rule template for every memo section

Use the following exact structure for every section.

### `[SECTION NAME]`

#### A. Section objective

Explain the LP-side business purpose of the section and the decision question it supports.

#### B. Required output structure

Define:

- Required heading.
- Table, paragraph, bullets, or repeated-record format.
- Required field order.
- Required versus conditional sub-sections.
- Expected level of detail.

#### C. Preferred sources

Provide a source-priority list:

1. Primary / authoritative source types.
2. Secondary corroborating source types.
3. Internal FM sources.
4. Sources that may provide leads but should not be treated as authoritative.
5. Sources that should not be used for the section.

Where the corpus supports it, include common folder names, document names, table labels, section headings, and search keywords.

#### D. Information to extract

List every required information slot from the Template Schema. For each slot define:

- Exact value, summarized finding, or analytical conclusion expected.
- Whether it is a fact, GP statement, observation, calculation, or inference.
- Whether an as-of date is required.
- Whether multiple sources are required.

#### E. Retrieval and matching logic

Explain how the agent should:

- Identify the correct GP, fund, vehicle, vintage, and date scope.
- Search likely documents.
- Match names across abbreviations and legal names.
- Match meeting records across notes, calendars, emails, and transcripts.
- Distinguish current strategy from predecessor-fund history.
- Avoid cross-deal contamination.

#### F. Source hierarchy and conflict rules

Define section-specific priority when values conflict. Include:

- Final versus draft documents.
- Executed legal documents versus marketing presentations.
- Newer versus older DDQ or organizational materials.
- Direct meeting notes versus calendar invitations.
- Internal FM legal/entity records versus GP materials.
- What conflicts may be resolved under the rule and which must be escalated to the user.

#### G. Normalization rules

Define standards for:

- Dates.
- Names and titles.
- Currencies and number formats.
- Percentages and basis points.
- Fund sizes, hard caps, and commitment amounts.
- Fee rates and calculation bases.
- Years of experience versus years at the firm.
- Current versus former roles.
- Control / minority terminology.
- IRR and MOIC labels, including gross versus net.

#### H. Drafting logic and sentence pattern

Explain how evidence becomes memo prose. Include:

- Recommended narrative sequence.
- Standard sentence or table-row patterns.
- What may be compressed.
- What qualifiers must be preserved.
- How to label GP statements.
- How to express LP-side analysis without overstating certainty.

#### I. Missing information behavior

Define what the agent must do when:

- A required fact is not located.
- The latest version is unclear.
- Documents conflict.
- Evidence is only a GP assertion.
- The section is required but poorly documented.
- A conditional section does not meet its inclusion trigger.

#### J. Section-specific prohibited behaviors

Examples:

- Do not infer email addresses.
- Do not convert an invitation list into confirmed attendance.
- Do not report a management-fee percentage without its base.
- Do not treat target allocation as actual allocation.
- Do not attribute all EBITDA growth to GP actions without evidence.

#### K. Quality-control checklist

Create binary or clearly testable checks. Every rule should allow an analyst to decide whether the section passes or fails.

#### L. Evidence-grounded examples

Where approved, provide:

- One good example pattern.
- One common failure pattern.
- Explanation of why the good example complies with the rule.

Do not copy confidential names or figures into a reusable methodology document unless the user approves; anonymize examples where appropriate.

## 6. Sections that require drafting rules

Draft complete rules for all of the following.

1. Document Title.
2. Core Investment Information.
3. Onsite Meetings and Subsequent Due Diligence.
4. Fund Terms Summary.
5. Investment Manager — Firm.
6. Investment Manager — Team.
7. Key Persons.
8. Strategy.
9. Summary of Changes to Strategy.
10. Value Creation.
11. Investment Process and Decision Making.
12. Summary of Process Changes.

Also create rules for the following conditional sub-sections when the corpus supports them:

- Management Fee Discounts.
- Team Changes.
- Operations / Portfolio Enhancement Team.
- Investment Committee / Governance.
- Strategy-specific portfolio-company selection criteria.
- Value-creation evidence table or case-study summary.

## 7. Initial provisional guidance by section

The following guidance is a starting hypothesis derived from the sample memos. Microsoft 365 Copilot must verify and refine it against the actual connected corpus.

### Document Title and Core Investment Information

Likely source families:

- FM internal approval or deal-intake record.
- Current term sheet, subscription document, or LPA.
- Current GP contact / relationship record.

High-risk distinctions:

- Firm name versus fund name.
- Investment opportunity versus legal subscription vehicle.
- GP entity versus investment manager.
- FM investing entity versus GP-side entity.
- Memo date versus source date or last-meeting date.

### Onsite Meetings and Subsequent Due Diligence

Likely source families:

- Final FM meeting notes.
- Teams recap or transcript.
- FM CRM / activity history.
- Calendar record.
- Substantive follow-up email.

Expected repeated record:

`Date → interaction title → FM attendees → GP attendees and roles → format → purpose → key diligence topics / follow-up significance`

Likely sentence pattern:

`On [date], [FM attendees] met with [GP attendees and roles] [format] to discuss [purpose and material topics].`

Key controls:

- Chronological order.
- One record per substantive interaction.
- Deduplicate the same event across notes, calendar, and email.
- Do not assume invited attendees actually attended.
- Include virtual meetings, calls, webinars, updates, and Q&A sessions when substantive.

### Fund Terms Summary

Likely source families:

- Executed or latest legal document.
- Latest LPA or LPA summary.
- Current term sheet.
- PPM.
- Side letter or negotiated economics.
- FM legal review.
- Fundraising deck only for clearly identified indicative terms.

Key controls:

- Fee rate must include calculation base and applicable period.
- Target size and hard cap must remain distinct.
- Investment period and fund term must remain distinct.
- Preserve consent and approval standards.
- Preserve current draft / final status.
- Distinguish `Key Man` legal terms from `Key Persons` biographies.
- `Reasonableness of Fees` requires an FM or LP-side assessment; it is not a GP fact.

### Firm

Likely source families:

- Current DDQ.
- Organizational overview.
- PPM.
- GP website or presentation only if authorized and current.
- FM relationship history and prior approved memo for historical leads, subject to re-verification.

Expected content:

- Founding and history.
- AUM with as-of date.
- Platforms and strategies.
- Offices and scale.
- Leadership / ownership.
- Material strategic or organizational evolution relevant to the current fund.

### Team

Likely source families:

- Current DDQ and team appendix.
- Organization chart.
- Current roster.
- Key-person schedule.
- Meeting notes regarding succession, capacity, turnover, and decision making.

Expected content:

- Dedicated team size and seniority mix.
- Senior experience and firm tenure.
- Offices and sector organization.
- Day-to-day fund leadership.
- IC composition and decision rights.
- Broader operating and support resources.
- Material team changes and succession issues.

### Key Persons

Likely source families:

- Current biographies.
- Current DDQ.
- Team roster and organization chart.
- LPA key-person schedule.
- Meeting notes that clarify actual fund responsibilities.

Expected biography sequence:

`Current title and fund role → tenure / relevant experience → prior roles → relevant investments / sector / geography → education`

Key controls:

- Use current titles.
- Select people based on relevance to the current fund rather than overall seniority alone.
- Do not assume everyone named in a biography section is legally named in the key-person clause.

### Strategy

Likely source families:

- Current PPM and fundraising presentation.
- DDQ strategy responses.
- Portfolio construction model.
- Track-record and prior-fund portfolio files.
- Meeting notes.

Expected information slots:

- Target number of investments.
- Control / minority orientation.
- Company size and equity-check range.
- Geography.
- Sectors and allocations.
- Target company characteristics.
- Sourcing and entry rationale.
- Underwriting and return drivers.
- Co-investment use.
- Fund-level and investment-level return objectives.
- Actual prior-fund evidence and execution risks.

Key controls:

- Target strategy is not the same as historical actual behavior.
- GP market statistics and claimed sourcing advantage must be attributed.
- Gross versus net returns must be labeled.
- Strategy should explain what the fund buys and why; detailed operating levers belong in Value Creation.

### Summary of Changes to Strategy

Likely source families:

- Current and predecessor-fund PPM / DDQ comparison.
- Prior-fund portfolio composition.
- Meeting notes describing lessons learned or formal changes.
- Internal FM analysis.

Required comparison:

`Prior approach → current approach → reason → evidence of implementation → LP implication`

Include only material, supported changes. Omit the section when no trigger is met.

### Value Creation

Likely source families:

- Value-creation presentation.
- Operating-team materials.
- DDQ operating-resource section.
- Portfolio-company case studies.
- Performance bridge and KPI files.
- Meeting notes with operating professionals.

Expected information slots:

- Operating model and resources.
- Timing of involvement.
- Repeatable levers.
- Implementation ownership and monitoring.
- Dated portfolio evidence.
- Organic versus inorganic attribution.
- Limitations, failed cases, and execution dependence.

Key controls:

- An operating team is not itself proof of value creation.
- Growth should not be fully attributed to GP initiatives without evidence.
- Preserve measurement dates and distinguish organic / inorganic results.

### Investment Process and Decision Making

Likely source families:

- DDQ investment-process responses.
- IC materials or governance summary.
- PPM.
- Meeting notes.
- Operating-team and portfolio-review materials.

Expected chronological stages:

`Sourcing → initial screening → diligence → value-creation plan → IC review → final approval → post-close plan → portfolio monitoring`

Rules should identify real decision rights, approval stages, voting / consensus mechanics, independent challenge, and escalation controls rather than merely describing the process as rigorous.

### Summary of Process Changes

Likely source families:

- Current versus prior DDQ / governance comparison.
- Meeting notes describing process reforms.
- IC or portfolio-review changes.
- Examples showing the new process in use.

Required comparison:

`Prior weakness → current control → reason → example / evidence → LP assessment`

Include only material changes. General current-process description belongs in `Investment Process and Decision Making`.

## 8. Required final deliverables from Microsoft 365 Copilot

Microsoft 365 Copilot should return the following in order:

1. `Corpus Readiness Report`
   - Files and folders accessed.
   - Historical memo / source-package pairings.
   - Missing or ambiguous inputs.
   - Proposed exclusions.
2. `Cross-Memo Section Map`
   - Sections found in each approved memo.
   - Common and conditional structures.
   - Section aliases.
3. `Source-to-Section Mapping Table`
   - Which source types consistently support which memo fields.
4. `LP Investment Memo — Section-by-Section Drafting Rules v1`
   - Complete rules using the standard template.
5. `Validation Report`
   - Historical deals tested.
   - Accuracy / completeness findings.
   - Unsupported statements or information gaps.
   - Rules revised after testing.
6. `Open Questions for FM`
   - Only decisions that cannot be resolved from the corpus.

## 9. Acceptance criteria

The drafting-rules document is ready only when:

- Every required section has a complete rule set.
- Each rule identifies actual source types observed in the connected materials.
- Each material information slot in the Template Schema is covered.
- Source conflicts and missing-information behavior are explicit.
- Historical examples are not used as current-fund facts.
- Legal terms retain bases, periods, triggers, consent standards, and version status.
- Meeting records distinguish actual attendance from invitations.
- Strategy rules distinguish stated strategy from historical execution.
- Value-creation rules distinguish GP claims from attributable evidence.
- Conditional sections have explicit inclusion and omission tests.
- Quality checks are binary or otherwise testable.
- At least two historical source packages have been used for validation.
- The document identifies limitations and unresolved FM policy choices.

## 10. Copy-paste prompts for Microsoft 365 Copilot

Use the prompts sequentially. Do not ask Copilot to create the final rules in the first message.

### Prompt 1 — Establish access and scope

```text
You are helping FM Investments design an LP-side investment memo drafting agent.

Treat the attached files “LP Investment Memo Template Schema v1” and “Section-by-Section Drafting Rules — Authoring Brief v1” as controlling methodology documents. Historical memos are examples of structure, tone, selection, and analytical depth only. Never use facts from one historical fund as facts for another fund.

For this first step, do not draft the Section-by-Section Drafting Rules and do not draft an investment memo.

Instead:
1. Confirm that you can access both control documents.
2. Inventory the SharePoint / OneDrive folders and files I have connected for this project.
3. Identify each approved historical final memo and its corresponding source package.
4. Categorize source files into meeting records, DDQ, PPM / presentation, LPA / term sheet / legal, performance, team / biographies, strategy, value creation, investment process, and FM internal records.
5. Identify drafts, duplicate versions, missing source packages, files with unclear dates, and files that may belong to another GP or fund.
6. Return a Corpus Readiness Report and a short list of access or scope issues that must be resolved before you derive drafting rules.

Do not guess when file ownership, fund scope, approval status, or version is unclear.
```

### Prompt 2 — Build the cross-memo and source map

```text
Using only the approved historical memos and source packages confirmed in the Corpus Readiness Report, build:

1. A Cross-Memo Section Map showing which canonical and conditional sections appear in each memo.
2. A Source-to-Section Mapping Table showing which source documents support each field or information slot in the Template Schema.
3. For each mapped statement, classify it as documented fact, GP statement, FM observation, calculation, or LP-side inference.
4. Identify statements in final memos that cannot be traced to the connected sources.
5. Identify recurring source conflicts, version problems, and reviewer corrections.

Do not draft the final rules yet. Cite the actual file name, date / version, and page, section, slide, meeting date, or other locator whenever available.
```

### Prompt 3 — Draft the Section-by-Section Drafting Rules

```text
Now draft “LP Investment Memo — Section-by-Section Drafting Rules v1” using the exact standard rule template in the Authoring Brief.

Write complete rules for every section in the Template Schema. Ground the rules in patterns observed across multiple approved memos and their source packages. Do not turn one GP’s fund-specific facts into a general rule.

For every section include:
- Section objective
- Required output structure
- Preferred sources in priority order
- Information to extract
- Retrieval and matching logic
- Source hierarchy and conflict rules
- Normalization rules
- Drafting logic and sentence / table patterns
- Missing-information behavior
- Prohibited behaviors
- Testable quality-control checklist
- Anonymized good and bad examples where useful

Explicitly distinguish facts, GP statements, FM observations, calculations, and LP-side inferences. Include precise inclusion and omission tests for conditional sections.

At the end, list unresolved FM policy decisions separately. Do not silently make those decisions.
```

### Prompt 4 — Validate the rules

```text
Validate the drafted rules against at least two historical source packages that were not used as the primary examples for writing each rule.

For each test deal:
1. Apply the rules to create a section-level evidence map without using the approved final memo as a factual source.
2. Compare the evidence map and resulting draft structure with the approved final memo.
3. Identify missing facts, incorrect facts, unsupported additions, cross-fund contamination, structural differences, tone differences, and unresolved conflicts.
4. Revise the drafting rules where the failure reflects an unclear or incomplete rule.
5. Produce a Validation Report showing what changed and what still requires human review.

Do not claim a successful validation merely because the wording resembles the historical memo. Accuracy, traceability, completeness, and correct source use are the primary criteria.
```

### Prompt 5 — Prepare the production-agent package

```text
Using the finalized Template Schema and validated Section-by-Section Drafting Rules, prepare a concise proposed instruction set for a Microsoft 365 Copilot investment memo drafting agent.

The instruction set must fit within the Agent Builder instruction limit and should reference, not reproduce, the two control documents. It must define:
- The agent’s LP-side purpose
- The requirement to work on one identified fund / deal folder at a time
- Evidence-first workflow
- Required versus conditional sections
- No-guessing and no-cross-fund-contamination rules
- Fact / GP statement / FM observation / LP inference distinctions
- Conflict and missing-information behavior
- Drafting and final audit workflow

Also propose four starter prompts:
1. Build an evidence map for a fund.
2. Identify missing or conflicting information.
3. Draft the memo after evidence review.
4. Audit a draft memo against source materials.

Do not publish or share the agent. Return the proposed configuration for human review.
```

## 11. Recommended Microsoft 365 Copilot setup sequence

1. Create or open a private test agent.
2. Add the two control documents as knowledge sources.
3. Add a small, curated calibration library rather than the entire historical archive.
4. Begin with two or three approved historical memo / source-package pairs.
5. Add the relevant SharePoint folders at the most specific practical level.
6. Verify that Copilot can actually retrieve content from the folders before requesting rules.
7. Run Prompts 1 through 4 sequentially.
8. Have an FM analyst review and approve the resulting drafting rules.
9. Upload the finalized rules as a new control document.
10. Only then run Prompt 5 to create the concise production-agent instructions.

## 12. Recommended calibration-folder structure

```text
Investment Memo Agent Calibration/
  00_Control Documents/
    LP_Investment_Memo_Template_Schema_v1.md
    Section_by_Section_Drafting_Rules_Authoring_Brief_v1.md

  01_Approved Historical Examples/
    Deal_01/
      00_Final Approved Memo/
      01_Meeting Records/
      02_DDQ and PPM/
      03_Legal and Terms/
      04_Performance/
      05_Firm Team and Bios/
      06_Strategy and Value Creation/
      07_Investment Process/
      08_FM Internal Records/

    Deal_02/
      [same structure]

  02_Held-Out Validation Deals/
    Deal_03/
      [source package plus approved final memo stored separately]

  03_Draft Outputs for Review/
```

The most important organizational principle is the explicit pairing between each historical final memo and its own source package. This allows Copilot to learn retrieval and transformation rules without mixing facts across funds.
