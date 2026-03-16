# Contributing to the Ultimate GRC Prompt Library

Thank you for considering a contribution. This library exists because GRC practitioners share what works.

---

## What Makes a Good Contribution

**A new prompt is worth adding if:**
- It addresses a GRC task that practitioners perform regularly
- It does not duplicate an existing prompt
- The output would be difficult to produce without AI assistance, or significantly faster with it
- It follows the prompt structure below

**An improvement to an existing prompt is worth submitting if:**
- You used the prompt in real work and found a specific failure mode
- The fix makes the output more reliable or more specific
- You have tested the improvement and can show a before/after

---

## Prompt Structure

Every prompt must follow this format:

```
<role>
[Specific senior expert role with domain and experience credentials]
</role>

<context>
[VARIABLE_ONE] - What this variable represents
[VARIABLE_TWO] - What this variable represents
</context>

<instructions>
Step 1: [First action - always a diagnostic or analysis step before producing content]
Step 2: [Main production step]
Step 3: [Output refinement or summary]
</instructions>

<output_format>
[Specific format instructions]
Write in British English. No em dashes.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

**Non-negotiable rules for all prompts:**
- British English throughout
- No em dashes in the prompt text (except the one in the CRITICAL OUTPUT RULE showing the character to avoid)
- Step 1 must be a diagnostic or calibration step, not immediate production
- All variables in `[SQUARE_BRACKETS]` with a description
- `<output_format>` must include the CRITICAL OUTPUT RULE verbatim

---

## How to Submit

1. Fork the repository
2. Create a branch: `git checkout -b add-prompt-NAME` or `git checkout -b fix-prompt-NUMBER`
3. Add or edit the prompt file in the appropriate domain folder
4. Update the prompt index in `README.md` if adding a new prompt
5. Open a pull request with:
   - What the prompt does
   - Which GRC domain it belongs to
   - The complexity level (Essential / Practitioner / Advanced) and why
   - If an improvement: what failure mode you found and how the fix addresses it

---

## What Not to Submit

- Generic prompts that could apply to any profession (not GRC-specific)
- Prompts that duplicate existing functionality without meaningful improvement
- Prompts without proper `<role>`, `<context>`, `<instructions>`, `<output_format>` structure
- Prompts that produce outputs you have not tested
- Anything with em dashes in the prompt text

---

## Reporting Issues

Open an issue if:
- A prompt produces unreliable or incorrect outputs for a specific use case
- A prompt is missing a constraint that would make it safer or more accurate
- A GRC use case is not covered and you want to discuss it before building

---

## Code of Conduct

Be direct. Be specific. Be useful. GRC practitioners are busy people. Contributions that waste their time are not welcome. Contributions that save their time always are.
