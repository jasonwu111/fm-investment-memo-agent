# FM Investment Memo Agent

This repository contains the control documents and Microsoft 365 Copilot handoff package for building an LP-side investment memo drafting agent.

## Recommended Microsoft 365 Copilot uploads

Upload the two `.txt` files individually to Microsoft 365 Copilot Agent Builder:

1. `LP_Investment_Memo_Template_Schema_v1.txt`
2. `Section_by_Section_Drafting_Rules_Authoring_Brief_v1.txt`

The ZIP file is provided for transfer only. Unzip it before uploading because Agent Builder does not use ZIP archives as knowledge sources.

## Files

- `LP_Investment_Memo_Template_Schema_v1.md` — Human-readable Markdown source defining required memo structure, fields, and conditional-section logic.
- `LP_Investment_Memo_Template_Schema_v1.txt` — Agent Builder-compatible version.
- `Section_by_Section_Drafting_Rules_Authoring_Brief_v1.md` — Human-readable research and handoff brief for deriving validated drafting rules from historical memos and source packages.
- `Section_by_Section_Drafting_Rules_Authoring_Brief_v1.txt` — Agent Builder-compatible version.
- `Microsoft_365_Copilot_Upload_Package_v1.zip` — Transfer archive containing the two TXT files.

## Data boundary

Historical memos are examples of structure, tone, selection, and analytical depth only. Facts for a new investment opportunity must come from the user-identified current fund or deal folder and approved FM internal records.

This repository contains methodology documents only. It should not contain confidential GP source packages, meeting notes, legal documents, personal data, or live investment materials unless FM has expressly approved their storage in the selected private repository.
