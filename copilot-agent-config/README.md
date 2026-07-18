# Microsoft 365 Copilot Agent Configuration

This directory is the version-controlled source of truth for configuring and testing the FM investment memo agents.

## Current Agent

The current configuration is for the methodology-development agent:

`FM Memo Rules Builder`

Its job is to analyze approved historical memos together with their corresponding source packages and produce a validated section-by-section drafting rulebook. It is not the production memo-writing agent.

## Directory Structure

```text
copilot-agent-config/
├── README.md
└── rules-builder/
    ├── 01_FM_Memo_Rules_Builder_Instructions_v1.txt
    ├── 02_Knowledge_Source_Setup_Guide_v1.md
    ├── 03_FM_Memo_Rules_Builder_Test_Prompts_v1.txt
    └── 04_Tuning_and_Test_Log_Template.md
```

## How to Use This Package

1. Copy the complete contents of `01_FM_Memo_Rules_Builder_Instructions_v1.txt` into the Microsoft 365 Copilot Agent Builder **Instructions** field.
2. Follow `02_Knowledge_Source_Setup_Guide_v1.md` to add the two control documents and the historical calibration cases.
3. Run the prompts in `03_FM_Memo_Rules_Builder_Test_Prompts_v1.txt` in order. Do not send all prompts at once.
4. Record every test run and configuration change in `04_Tuning_and_Test_Log_Template.md`.
5. Commit changes before configuring the other computer so that the GitHub repository remains the source of truth.

## Versioning Convention

- Minor wording or retrieval changes: `v1.1`, `v1.2`
- Material workflow or section changes: `v2.0`
- Never overwrite an approved version without preserving its prior Git history.

## Future Production Agent

After the Rules Builder produces a human-approved drafting rulebook, create a separate production configuration directory:

```text
copilot-agent-config/production-memo-agent/
```

The production agent should use the approved Template Schema and validated Drafting Rules. It should not use the Rules Authoring Brief as its daily operating rulebook.
