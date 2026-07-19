# Knowledge Source Setup Guide — FM Memo Rules Builder

## 1. Agent Builder Fields

Use the following values:

- **Name:** `FM Memo Rules Builder`
- **Description:** `Builds and validates LP-side investment memo drafting rules using approved historical FM memos and their corresponding source packages.`
- **Default response mode/model:** Select `Think deeper` if available.
- **Only use specified sources:** Turn on if available.
- **Search all websites:** Turn off.
- **Reference people in organization:** Turn off unless a specific test requires it.
- **Create documents, charts, and code:** Optional; turn on only if approved and useful for exporting the rulebook.

Copy the complete contents of `01_FM_Memo_Rules_Builder_Instructions_v1.txt` into the Instructions field.

## 2. Always-Required Control Files

Upload these two files as Knowledge:

1. `LP_Investment_Memo_Template_Schema_v1.txt`
2. `Section_by_Section_Drafting_Rules_Authoring_Brief_v1.txt`

For the current Bain Capital Insurance Fund II and Bessemer Century Fund III calibration cases, also upload:

3. `05_Calibration_Case_Notes_v1.txt`

The Case Notes describe the current folder boundaries and package-specific triage guidance. They do not replace the SharePoint folder connections and are not an authoritative source for fund facts.

Wait until neither file displays `Preparing` before testing.

## 3. Initial Calibration Cases

Start with two approved historical cases. Each case must include both sides of the pair:

```text
Calibration/
├── Case_01_Firm_Fund/
│   ├── Final_Memo/
│   │   └── Approved_Final_Memo.docx
│   └── Source_Package/
│       └── [the exact materials used for that memo]
└── Case_02_Firm_Fund/
    ├── Final_Memo/
    │   └── Approved_Final_Memo.docx
    └── Source_Package/
        └── [the exact materials used for that memo]
```

Add each case by browsing to its specific SharePoint or OneDrive folder, or by entering the exact folder URL. Keep each case boundary explicit.

Do not connect the entire private-equity archive at this stage.

## 4. Held-Out Validation Case

Prepare a third complete historical case, but do not add it during rule development:

```text
Validation/
└── Case_03_Firm_Fund/
    ├── Final_Memo/
    │   └── Approved_Final_Memo.docx
    └── Source_Package/
        └── [the exact materials used for that memo]
```

Add the held-out case only immediately before running the held-out validation prompt. This prevents the Agent from using the answer case while developing the rules.

## 5. What Not to Add Initially

Do not add:

- Public websites.
- The full SharePoint investment archive.
- Outlook email or Teams chats.
- Unapproved memo drafts.
- Duplicate or superseded versions.
- Source packages whose relationship to a final memo is unclear.
- Materials for unrelated funds in the same calibration folder.
- The held-out validation case before validation.
- Redline, blackline, or comparison copies when a clean/current/final version of the same document is available, unless change analysis is required.

Websites can be considered later for narrow verification use, but they should not be part of initial rule calibration because they weaken source control and reproducibility.

## 6. Recommended File Manifest

For each case, maintain a simple manifest with:

| Field | Description |
|---|---|
| Case ID | Unique case name |
| Firm | GP/firm name |
| Fund | Investment opportunity |
| Final memo filename | Approved output |
| Memo approval status | Approved/final only |
| Memo date | As-of date |
| Source folder URL | Exact source package |
| Files expected | High-level inventory |
| Files missing | Known gaps |
| Validation role | Calibration or held-out |

## 7. Starter Prompts

Configure these optional starter prompts:

1. **Confirm Control Documents** — `Explain the distinct role of each uploaded control document and the document you are expected to produce.`
2. **Inventory Calibration Materials** — `Inventory and pair the connected historical final memos and source packages. Do not draft rules yet.`
3. **Build Evidence Map** — `Map recurring memo sections and fields to their supporting source types and locators.`
4. **Validate Drafting Rules** — `Test the draft rules against the designated held-out historical case and report every discrepancy.`

## 8. Readiness Checklist

Do not begin rule drafting until all are true:

- The two control files are ready and accessible.
- At least two approved historical memos are available.
- Each historical memo has an exact source-package pairing.
- Draft and final versions are distinguishable.
- The Agent correctly explains the role of the Schema versus the Authoring Brief.
- The held-out case remains excluded from the development set.
- Public web search and unrelated sources are not being used.

## 9. Security and Sharing

Keep the Agent set to `Only you` during calibration. Do not share it broadly until file permissions, sensitivity labels, output behavior, and held-out validation have been reviewed. The Agent must never be treated as an autonomous investment decision-maker.
