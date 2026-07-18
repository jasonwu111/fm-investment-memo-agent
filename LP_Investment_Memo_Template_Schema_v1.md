# LP Investment Memo Template Schema v1

Status: Working draft based on the BC Partners Fund XII and H.I.G. Europe Middle Market Fund II sample memos  
Intended output language: English  
Primary audience: FM Investments / LP-side investment professionals and decision makers  
Document purpose: Define what the memo must contain, the order of the content, the internal information slots within each section, and the inclusion logic for conditional sections.

## 1. Scope and design principles

This schema is the structural contract for the future Microsoft 365 Copilot agent. It defines **what the agent must produce**. It is not yet the complete instruction set governing source search, source priority, conflict resolution, analytical tone, or final quality assurance; those will be documented separately in the Section-by-Section Drafting Rules and Source Hierarchy.

The memo is an LP-side underwriting document, not a GP marketing summary. It should identify the proposed fund and legal vehicle, summarize the diligence completed, document material fund terms, assess the GP and relevant team, explain the strategy and value-creation model, and surface material changes or process developments when supported by the reviewed materials.

Global structural rules:

- Preserve the canonical section order in this schema unless the approved FM template requires a different order.
- Required sections must always be addressed before a final memo can be produced.
- Conditional sections must be omitted when their inclusion trigger is not met. Do not create empty conditional headings.
- Do not use facts from a historical memo as facts for the current fund. Historical memos may be used only to understand structure, tone, and expected analytical depth.
- Keep the current fund, predecessor funds, parallel funds, co-investments, and legal subscription vehicle distinct.
- Maintain an internal evidence record for every material fact, even if citations are removed from the clean memo.
- When a required fact is missing or conflicting, flag it during evidence review rather than guessing.

## 2. Canonical memo outline

1. Document Title
2. Core Investment Information
3. Onsite Meetings and Subsequent Due Diligence
4. Fund Terms Summary
5. Investment Manager
   - Firm
   - Team
   - Team Changes, if material
   - Operations / Portfolio Enhancement Resources, if material
   - Investment Committee / Governance, if material
6. Key Persons
7. Strategy
8. Summary of Changes to Strategy, conditional
9. Value Creation
10. Investment Process and Decision Making
11. Summary of Process Changes, conditional

Canonical heading aliases observed in the sample memos:

- `Value-Add Capabilities` should map to the canonical `Value Creation` section.
- `Investment Manager` may be used as an umbrella heading for `Firm` and `Team`.
- `Onsite Meetings and Subsequent Due Diligence` includes in-person meetings, virtual meetings, webinars, update calls, and other substantive diligence interactions; it is not limited to literal onsite meetings.

## 3. Document Title

### Required output pattern

`FM INVESTMENTS – [SHORT FUND / OPPORTUNITY NAME] – Investment Recommendation`

### Required fields

| Field | Requirement | Definition |
|---|---|---|
| `short_fund_name` | Required | Concise, recognizable opportunity name used in the title. It may be shorter than the full legal fund name. |
| `document_type` | Fixed | `Investment Recommendation`, unless FM specifies another approved document type. |

### Validation rules

- The title must refer to the current investment opportunity, not the GP platform generally.
- The title does not replace the full legal names in Core Investment Information or Fund Terms Summary.

## 4. Core Investment Information

### Required rendering order

1. **Firm Name:** `[firm_name]`
2. **Firm Point of Contact:** `[contact_name] ([contact_email])`
3. **Investment Opportunity:** `[investment_opportunity]`
4. **Investment Vehicle Name:** `[investment_vehicle_legal_name]`
5. **FM Global Investing Entity:** `[fm_investing_entity]`
6. **Date:** `[memo_as_of_date]`

### Field definitions

| Field | Requirement | Expected content | Important distinction |
|---|---|---|---|
| `firm_name` | Required | Current legal or approved display name of the GP / investment manager. | Do not substitute the fund name. |
| `contact_name` | Required | Primary GP relationship, investor-relations, fundraising, or diligence contact for the opportunity. | Use the designated current contact, not merely the most frequently mentioned person. |
| `contact_email` | Required when available | Current business email address. | Do not infer an email pattern. |
| `investment_opportunity` | Required | Economic fund opportunity being evaluated. | Distinct from the legal subscription vehicle. |
| `investment_vehicle_legal_name` | Required | Exact legal name of the vehicle into which FM would subscribe. | Preserve jurisdictional or entity suffixes such as L.P., LP, SCSp, Cayman, parallel vehicle, feeder, or blocker designations. |
| `fm_investing_entity` | Required | Exact FM legal entity making the investment. | Primarily an FM-internal fact, not a GP-supplied fact. |
| `memo_as_of_date` | Required | Date of the investment recommendation memo. | Do not substitute the latest meeting date, source-document date, or generation date without confirmation. |

### Completion rule

The agent must not finalize the memo if `investment_opportunity`, `investment_vehicle_legal_name`, or `fm_investing_entity` remains unresolved or internally conflicting.

## 5. Onsite Meetings and Subsequent Due Diligence

### Section status

Required. Include all substantive interactions relevant to the opportunity through the memo as-of date.

### Internal record schema for each interaction

| Field | Requirement | Definition |
|---|---|---|
| `interaction_date` | Required | Exact date of meeting, call, webinar, or diligence interaction. |
| `interaction_title` | Recommended | Short label such as `Fund Launch Webinar`, `Portfolio Performance Review`, or `Co-Investment and Fund Discussion`. |
| `fm_attendees` | Required when identifiable | FM participants. Preserve full names and do not mix them with GP participants. |
| `gp_attendees` | Required when identifiable | GP participants or presenters. |
| `gp_attendee_roles` | Include when available | Role in parentheses, particularly for IR, fund leadership, investment professionals, or operating professionals. |
| `interaction_format` | Recommended | In person, onsite, virtual meeting, call, webinar, investor update, Q&A, or other format. |
| `interaction_purpose` | Required | What the parties met to discuss or what diligence objective the interaction served. |
| `key_topics` | Include when material | Strategy, fundraising, portfolio performance, market opportunity, team, process, terms, underperforming assets, co-investment, or other substantive topics. |
| `follow_up_or_dd_significance` | Conditional | Follow-up requested, material learned, unresolved question, or link to subsequent diligence. |

### Canonical sentence pattern

`On [Month D, YYYY], [FM attendee(s)] [met with / attended / joined] [GP attendee(s), including roles when known] [in person / virtually / in a webinar] to [purpose]. [Optional: Key diligence topics or follow-up significance.]`

Alternative compact line-item pattern:

`[Month D, YYYY] — [Interaction title]: [FM attendee(s)] [met with / attended] [GP attendee(s)] to [purpose and material topics].`

### Ordering and inclusion rules

- Sort interactions chronologically from earliest to latest.
- Use one record per substantive interaction.
- Consolidate duplicate records of the same event rather than listing the same meeting twice.
- Include relevant virtual sessions, calls, investor updates, webinars, and Q&A sessions despite the section title containing `Onsite`.
- Exclude purely administrative scheduling emails unless they contain substantive diligence information.
- Do not infer attendance from a distribution list or calendar invitation if actual attendance is unclear.
- Use roles only when supported by the reviewed materials.
- Keep descriptions concise: who, with whom, when, and for what purpose. Add outcomes only when documented and material.

## 6. Fund Terms Summary

### Section status and format

Required. Render as a two-column table: `Term` and `Summary`.

### Canonical term rows

The agent should search for and normalize the following rows in this order. Rows marked conditional should be included when applicable or when the approved FM template requires them.

| Canonical row | Status | Required content |
|---|---|---|
| Fund Name | Required | Full fund name, distinct from the FM subscription vehicle when different. |
| General Partner | Required | Exact legal GP entity. Do not substitute the investment manager unless they are the same legal entity. |
| Stage Focus | Required | Buyout, growth, venture, credit, secondaries, distressed, or other stage / transaction focus. Include control orientation if stated. |
| Geography Focus | Required | Primary and secondary geographies; note allocation limits when stated. |
| Target Fund Size (cap) | Required | Target size and hard cap, if both exist. Preserve currency. |
| Fund Currency | Conditional / recommended | Base currency and any investor currency election or share-class option. |
| Closing Dates (size) | Required | Initial, interim, and final close timing; include amounts or target percentages when available. |
| Base Management Fee | Required | Rate, calculation base, and applicable period. |
| Management Fee after Investment Period | Required | Rate, calculation base, step-down mechanics, and extension-period treatment. |
| Carried Interest | Required | Carry percentage and any tiering or special rate. |
| Hurdle Rate | Required | Preferred-return rate and compounding convention when specified. |
| Fee Breaks | Required | Early-close, re-up, commitment-size, strategic-LP, or other discounts. Write `Not specified in reviewed materials` rather than `None` unless absence is confirmed. |
| Investment Period | Required | Duration, start point, termination triggers, and extension rights when material. |
| Term (extensions) | Required | Base term, start point, number and duration of extensions, decision maker, and required consent. |
| Waterfall (Catch-up) | Required | European / whole-fund or deal-by-deal structure, catch-up percentage, and final LP/GP split. |
| Fee Offset | Required | Offset percentage, covered fee types, exclusions, and whether calculated on gross or net fees when available. |
| Additional Fees | Required | Organizational expense cap and material transaction, monitoring, broken-deal, adviser, or other charges. |
| Key Man | Required | Legal trigger, covered persons or required number, required time commitment, consequence, cure / replacement mechanism, and LP / LPAC approval thresholds when stated. |
| GP Commitment | Required | Percentage or amount; specify whether funded by the GP, team, affiliates, or fee waiver if stated. |
| Leverage | Required | Subscription line or fund-level borrowing limit, duration, purpose, and LPAC-consent threshold where relevant. |
| Recycling | Conditional / recommended | Maximum recycling amount or percentage, scope, and time limitations. |
| LP Co-Investment? | Required | Availability, allocation discretion, economics, and whether no-fee/no-carry treatment is stated or merely typical. |
| Hedging | Conditional / recommended | FX, equity, interest-rate, or portfolio-level hedging policy where relevant. |
| Reasonableness of Fees | Required analytical row | Concise LP-side assessment of whether material terms are in line with relevant market practice; identify specific above-market or below-market terms. |

### Optional sub-section: Management Fee Discounts

Include when the GP offers discounts whose economic effect is material to FM. Capture:

- Discount type.
- Basis-point or percentage reduction.
- Eligibility and deadline.
- Applicable fee base and period.
- Whether discounts stack.
- Estimated dollar benefit only when FM commitment amount and timing assumptions are confirmed.

### Term-specific validation rules

- Never report a fee rate without its calculation base and applicable period.
- Do not merge target fund size and hard cap.
- Do not simplify key-man language into a list of names if the trigger depends on a number of people, time-commitment standard, change of control, replacement mechanics, or investor approval.
- Keep `Key Man` legal terms distinct from the `Key Persons` biographical section.
- Preserve consent standards such as GP discretion, LPAC approval, majority in interest, supermajority, or advisory-committee approval.
- When draft and final documents conflict, flag the conflict before drafting a final table.
- `Reasonableness of Fees` is an FM assessment and should not be copied from GP marketing materials.

## 7. Investment Manager — Firm

### Section status

Required. Default length: two to four concise paragraphs, adjusted for the complexity and history of the GP.

### Internal information slots

1. `founding_and_history`
   - Founding year.
   - Relevant history and development of the organization.
2. `platform_scale`
   - Total AUM with as-of date.
   - Employees and investment professionals when material.
   - Offices and geographic footprint.
3. `business_platforms`
   - Relevant strategies such as private equity, credit, real estate, infrastructure, or other platforms.
   - Explain whether platforms operate independently or share committees and resources when material.
4. `leadership_and_ownership`
   - Founders, executive leadership, ownership structure, and significant governance arrangements.
5. `relevance_to_current_fund`
   - How the broader firm supports the specific strategy under review.
6. `material_history_or_evolution`
   - Major strategic shifts, reorganizations, performance-related changes, acquisitions, departures, or governance changes relevant to current underwriting.

### Boundary rules

- Firm describes the organization as a whole; Team describes the professionals responsible for the current fund.
- AUM, employee count, and office count must include an as-of date when available.
- Avoid unsupported promotional descriptions such as `leading`, `premier`, or `best-in-class`.
- Include other business platforms only to the extent that they affect resources, conflicts, governance, or the current fund.

## 8. Investment Manager — Team

### Section status

Required. The section should explain the collective team, not repeat all individual biographies.

### Internal information slots

| Slot | Expected content |
|---|---|
| `dedicated_team_size` | Number of professionals dedicated to the current strategy, with senior / mid-level / junior split where available. |
| `broader_resource_base` | Relevant regional, sector, operating, capital-markets, recruiting, legal, compliance, finance, or data resources available to the fund. |
| `senior_experience_and_tenure` | Average investing experience and tenure; label whether the metric applies to the whole team or only senior professionals. |
| `office_and_sector_coverage` | Location of the fund team and organization by geography or industry vertical. |
| `day_to_day_leadership` | Person or group overseeing daily investing and portfolio decisions. |
| `investment_committee` | Composition, voting or approval mechanics, permanent and rotating seats, and relevant oversight. |
| `decision_rights` | Which decisions are made by the fund team versus firm-level committees. |
| `team_continuity` | Promotions, departures, retirements, recruiting, succession, and retention issues when material. |
| `capacity_and_scalability` | Whether team size, senior coverage, and operating resources appear sufficient for target portfolio size and strategy complexity. |

### Optional leadership table

Use when the approved template or available data supports a concise overview of firm-level or fund-level leadership.

| Column | Definition |
|---|---|
| Name | Full current name. |
| Title | Current title. |
| Years at Firm | As-of-date tenure; do not confuse with total industry experience. |
| Background | Most relevant prior positions and investment experience. |
| Education | Degrees and institutions when material and verified. |

### Conditional sub-sections

- `Team Changes`: Include material departures, promotions, hires, retirements, succession, morale, incentive, or organizational changes.
- `Operations / Portfolio Enhancement Team`: Include team size, specialties, reporting line, timing of involvement, and relationship to deal teams.
- `Investment Committee`: Use a separate sub-section if committee composition and governance are sufficiently material or complex.

## 9. Key Persons

### Section status

Required. Include the people most material to the current strategy, fund leadership, investment decisions, sector coverage, portfolio oversight, and legal key-person analysis.

### Repeated person record

| Field | Requirement | Definition |
|---|---|---|
| `person_name` | Required | Full current name. |
| `current_title` | Required | Current title at the GP. |
| `fund_role` | Required | Role in the current fund, team, IC, sector, geography, or operating function. |
| `firm_join_year_or_tenure` | Include when available | Join year or tenure as of the memo date. |
| `total_relevant_experience` | Include when available | Years and type of relevant investment, operating, or industry experience. |
| `prior_employers_and_roles` | Recommended | Only the most relevant prior positions. |
| `relevant_investments_or_sectors` | Recommended | Selected deals, sectors, or geographies relevant to the current strategy. |
| `education` | Recommended | Verified degrees and institutions. |
| `office_location` | Conditional | Include when geography is relevant to coverage or decision making. |
| `key_person_clause_status` | Internal-only cross-check | Whether the person is named or relevant under the legal key-man provision. Do not automatically state this in the bio. |

### Canonical biography order

`[Name] is [current title] and [fund role]. [Join year / tenure and relevant experience.] [Relevant prior roles.] [Relevant investment, sector, or geographic experience.] [Education, if verified and useful.]`

### Selection rules

- Do not include every senior employee at the GP.
- Prioritize people who lead the fund, sit on the IC, control a material sector or geography, oversee value creation, or are named in key-person provisions.
- Do not copy an outdated website biography if a newer DDQ or organizational document indicates a changed title or departure.
- Keep biographies concise and comparable across people.

## 10. Strategy

### Section status

Required. This is a structured synthesis section, not a generic narrative.

### Required strategy components

1. **Portfolio construction**
   - Target number of platform investments.
   - Investment period and expected pace, if relevant.
   - Expected concentration and diversification.
2. **Transaction type and ownership**
   - Control, significant influence, minority, buyout, carve-out, take-private, distressed, or special-situation orientation.
3. **Target company size**
   - Enterprise value, revenue, EBITDA, equity check, or other stated size measures.
   - Preserve the specific metric and currency; do not convert EBITDA range into enterprise-value range.
4. **Geography**
   - Primary geographies and any secondary / opportunistic allocation.
   - Local-office or sourcing coverage relevant to execution.
5. **Sector focus**
   - Core sectors and subsectors.
   - Target allocation percentages or limits when stated.
6. **Target company archetype / investment criteria**
   - Examples: mission-critical products, recurring revenue, defensible market position, under-managed companies, complexity, strong cash flow, scalability, fragmented markets, management quality, or quantifiable risks.
7. **Sourcing and entry advantage**
   - Proprietary / semi-proprietary sourcing, local networks, carve-outs, family-owned businesses, complexity, sector expertise, or other claimed edge.
8. **Underwriting thesis**
   - Why the targeted companies are expected to generate returns.
   - Primary operational, strategic, growth, deleveraging, or multiple-related return drivers.
9. **Value-creation linkage**
   - High-level connection between strategy and the detailed Value Creation section.
10. **Co-investment and exposure management**
   - Expected use of LP co-investment for larger transactions or concentration management.
11. **Return objectives**
   - Gross or net IRR / MOIC targets, clearly labeled by investment level or fund level.
12. **Evidence and LP-side considerations**
   - Actual prior-fund behavior versus stated strategy.
   - Relevant execution risks, market risks, concentration risks, or dependence on operating capabilities.

### Recommended narrative sequence

1. One paragraph defining the strategy in plain terms.
2. One or more paragraphs or bullets covering sector, geography, target size, transaction type, and portfolio construction.
3. Target company characteristics and sourcing / entry rationale.
4. Return-generation and value-creation model.
5. Market opportunity and LP-side risks or execution considerations.

### Strategy validation rules

- Separate stated target allocation from actual historical allocation.
- Separate fund-level return targets from investment-level return targets.
- Treat GP market statistics and claimed entry advantages as GP assertions unless independently supported.
- Avoid duplicating the full Value Creation section; Strategy should explain what the fund buys and why, while Value Creation explains how the GP plans to improve investments.

## 11. Summary of Changes to Strategy

### Section status

Conditional. Include only when the current fund or current approach differs materially from predecessor funds or the GP's established historical approach.

### Inclusion triggers

- Addition, removal, or formal de-emphasis of a sector.
- Material change in target geography.
- Change in control / minority orientation.
- Material movement in company size, check size, or transaction complexity.
- Change in portfolio concentration, target number of investments, or co-investment usage.
- New underwriting screens or internal vetoes created in response to prior losses.
- Change in value-creation emphasis, leverage posture, or return objectives.

### Repeated change record

| Field | Definition |
|---|---|
| `change_title` | Short descriptive label, such as `Sector Discipline` or `Larger Target Company Size`. |
| `prior_approach` | What the prior fund or prior process did. |
| `current_approach` | What the current fund intends to do. |
| `reason_for_change` | Performance lesson, market development, team evolution, or explicit GP rationale. |
| `evidence_of_implementation` | Portfolio composition, policy, screening rule, examples, or other evidence that the change is actually in effect. |
| `lp_implication` | Expected benefit, new risk, execution dependency, or open diligence question. |

### Omission rule

If no material change is documented, omit the section entirely. Do not add an empty heading or manufacture a `no changes` narrative.

## 12. Value Creation

### Section status

Required. The section may appear as `Value-Add Capabilities` in source materials, but final output should use the approved FM heading.

### Required value-creation components

1. `operating_model`
   - Hands-on, board-led, adviser-led, functional-specialist, or deal-team-led model.
2. `resources`
   - Number and type of operating partners, retained advisers, sector experts, recruiters, technology specialists, capital-markets resources, and other relevant capabilities.
3. `timing_of_involvement`
   - Involvement during sourcing, diligence, underwriting, 100-day planning, ownership, and exit.
4. `repeatable_playbook`
   - Use only the levers supported for the current GP, such as:
     - Sales-force effectiveness.
     - Pricing and commercial excellence.
     - Cost optimization and operational excellence.
     - Technology / digital transformation.
     - FP&A and data analytics.
     - Recruiting and management upgrades.
     - Strategic repositioning.
     - Organic growth and new-market entry.
     - Add-on acquisitions and integration.
     - Procurement and working capital.
     - Capital structure and deleveraging.
5. `implementation_and_governance`
   - Who owns initiatives, how plans are approved, cadence of performance review, and escalation mechanisms.
6. `evidence_of_execution`
   - Prior portfolio-company examples, initiatives applied, add-on counts, revenue / EBITDA growth, margin improvement, or other dated metrics.
7. `attribution_and_limitations`
   - Organic versus inorganic contribution, GP claim versus verified result, unsuccessful cases, dependence on management, and execution risk.

### Recommended structure

- Introductory paragraph describing the model and resources.
- Bullets or short sub-sections for the main repeatable levers.
- One evidence paragraph or table summarizing prior-fund examples and dated results.
- One LP-side paragraph on repeatability, attribution, and execution risk.

### Validation rules

- Do not treat the existence of an operating team as proof of successful value creation.
- Do not present portfolio-company growth as fully attributable to GP initiatives without supporting evidence.
- Preserve the measurement date for all operating-performance statistics.
- Where possible, separate organic and acquisition-driven growth.

## 13. Investment Process and Decision Making

### Section status

Required when sufficient information is available. Because both sample memos discuss process and governance, the agent should actively search for this section rather than treat it as GP-specific background.

### Required process stages

1. `sourcing`
   - Networks, intermediaries, local offices, proprietary sourcing, sector teams, business-development resources.
2. `initial_screening`
   - Preliminary analysis, fit with strategy, initial IC or deal-approval gate.
3. `due_diligence`
   - Commercial, financial, operational, legal, management, market, downside, and external-adviser workstreams.
4. `value_creation_plan_development`
   - When operating resources become involved and how the business plan is developed.
5. `investment_committee_review`
   - Number of stages, committee composition, voting / consensus mechanics, permanent / rotating members, independent challenge, and chair authority.
6. `final_approval_and_signing`
   - Final decision point and required documentation.
7. `post_close_plan`
   - 100-day plan or equivalent, management alignment, and initial implementation.
8. `portfolio_monitoring`
   - Board oversight, review frequency, portfolio-review committees, exit / hold decisions, and escalation.

### Recommended narrative sequence

Describe the process chronologically from sourcing through ownership. Emphasize decision rights and control points rather than using generic phrases such as `rigorous due diligence` or `highly structured process` without supporting detail.

## 14. Summary of Process Changes

### Section status

Conditional. Include only when the GP has materially changed its sourcing, underwriting, investment-committee, governance, monitoring, or exit process.

### Inclusion triggers

- New or restructured IC.
- Addition of rotating members, independent reviewers, devil's-advocate review, or cross-sector challenge.
- New downside-case, recession-case, or independent assumption review.
- Changed approval stages or faster / more disciplined decision rules.
- New operating-partner involvement during diligence.
- New 100-day plan sign-off or portfolio-review cadence.
- Process change explicitly introduced in response to prior investment losses, delayed decisions, weak underwriting, or insufficient challenge.

### Repeated process-change record

| Field | Definition |
|---|---|
| `process_change_title` | Short label for the change. |
| `prior_process` | Former approach and identified weakness. |
| `current_process` | New control, governance mechanism, or workflow. |
| `reason_for_change` | Specific lesson, deficiency, or objective. |
| `example_or_evidence` | Deal example, policy, committee record, or observed use. |
| `lp_assessment` | Whether the change appears meaningful, consistently applied, and sufficient to address the prior issue. |

### Omission rule

Omit the section if changes are not documented or are merely cosmetic. A general description of the current process belongs in `Investment Process and Decision Making`, not here.

## 15. Required versus conditional section logic

| Section | Default status | If information is missing |
|---|---|---|
| Document Title | Required | Stop and request the opportunity name. |
| Core Investment Information | Required | Stop for unresolved legal vehicle or FM entity; flag other missing items. |
| Onsite Meetings and Subsequent Due Diligence | Required | State during evidence review that no qualifying interactions were located; obtain user confirmation before finalizing. |
| Fund Terms Summary | Required | Flag unresolved or draft terms; do not guess. |
| Firm | Required | Produce only from supported current facts; flag missing as-of dates. |
| Team | Required | Flag missing current org / roster information. |
| Key Persons | Required | Ask for confirmation of the relevant people if scope is unclear. |
| Strategy | Required | Flag missing ranges, allocations, or ownership model; do not infer from prior funds alone. |
| Summary of Changes to Strategy | Conditional | Omit if no material supported change. |
| Value Creation | Required | Flag if only generic marketing claims are available. |
| Investment Process and Decision Making | Required when sufficiently documented | If evidence is thin, identify the missing process stages before finalizing. |
| Summary of Process Changes | Conditional | Omit if no material supported change. |

## 16. Internal evidence object for the agent

Before drafting prose, the agent should create an internal evidence object for every field or material statement:

| Evidence field | Definition |
|---|---|
| `section` | Destination memo section. |
| `schema_field` | Canonical field or information slot. |
| `extracted_value` | Exact value or concise finding. |
| `source_document` | File name or source identifier. |
| `source_location` | Page, section, table, slide, meeting date, or other locator. |
| `source_date` | Date or version of the source. |
| `source_type` | Legal document, DDQ, PPM, presentation, meeting note, email, internal FM record, prior memo, or other. |
| `fact_type` | Documented fact, GP statement, FM observation, calculated value, or LP-side inference. |
| `confidence` | High, medium, or low based on directness and consistency of evidence. |
| `conflict_status` | None, unresolved, or resolved under an approved source-priority rule. |
| `notes` | Assumptions, missing context, required follow-up, or reason for omission. |

The clean memo may omit citations if required by the FM house format, but the evidence object should remain available for analyst review and memo audit.

## 17. Schema-level output controls

- Use English unless the user explicitly requests another language.
- Use professional institutional-investment prose.
- Preserve exact legal names, currencies, percentages, dates, and approval thresholds.
- Keep facts, GP claims, FM observations, and LP-side interpretations distinct.
- Avoid unsupported superlatives and generic marketing language.
- Do not silently reconcile conflicting values.
- Do not allow one missing field to cause the agent to fill it from another GP, prior fund, or historical example.
- Use a consistent as-of date throughout the memo.
- Ensure optional headings appear only when inclusion triggers are met.
- Run a final cross-section check for inconsistent names, dates, fund sizes, fee rates, strategy ranges, and team roles.

## 18. Relationship to the next control documents

This schema answers: **What sections and information slots must the memo contain?**

The next document, `Section-by-Section Drafting Rules`, should answer:

- Which source types the agent should search for each field.
- In what order sources should be trusted.
- How to reconcile conflicting dates, numbers, titles, and legal terms.
- How much compression or analytical interpretation is allowed in each section.
- How to distinguish GP assertions from FM conclusions.
- What the agent should do when evidence is missing.
- What section-specific validation test must pass before drafting.

The later `Source Hierarchy and Conflict Rules` should define authoritative-document priority, version handling, current-versus-historical scope, and the treatment of draft versus executed legal documents.
