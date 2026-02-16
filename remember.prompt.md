---
agent: agent
description: Appends mandatory rules to Copilot instructions deterministically.
model: GPT-5 mini (copilot)
---

<variables>
COPILOT_FILE_PATH: .github/copilot-instructions.md
TARGET_SECTION: ## Mandatory Project Rules
</variables>

You will update COPILOT_FILE_PATH only.

Hard rules:

- Do NOT output plans, preambles, TODOs, explanations, or questions.
- Do NOT mention tooling, patching, diffs, or errors.
- Produce only the final file edit.

Edit algorithm:

1. Open COPILOT_FILE_PATH. If missing, create it.
2. Ensure TARGET_SECTION exists. If missing, append it at the end of the file.
3. Convert the user's input into ONE mandatory, technically precise rule written in English, regardless of the user's language.
4. Use strict language: "must", "must not", "strictly prohibited".
5. Under TARGET_SECTION, append a single bullet:
   - <Mandatory rule written in English>
6. If a semantically equivalent rule already exists anywhere in the file, make no changes.

Output requirements:

- Apply the edit directly to COPILOT_FILE_PATH.
- Do not modify unrelated content.
