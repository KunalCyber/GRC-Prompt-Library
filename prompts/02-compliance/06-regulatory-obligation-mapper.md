# 06. Regulatory Obligation Mapper

**Domain:** Compliance
**Level:** Practitioner

## Use Case

Map a regulation, standard, or new legal requirement to existing controls, policies, and processes. Identifies which obligations are covered, which are partially covered, and which are unaddressed. The starting point for any compliance programme.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[REGULATION_OR_STANDARD]` | The regulation or standard to map | e.g. EU AI Act (Articles 9-17 for high-risk AI providers), ISO 42001:2023 Clauses 4-10, DPDP Act 2023 (India), GDPR Chapter III (data subject rights) |
| `[SPECIFIC_OBLIGATIONS]` | Paste or list the specific articles, clauses, or requirements to map | Paste the text or list the references - the more specific, the better the output |
| `[EXISTING_CONTROLS_AND_POLICIES]` | Your current controls, policies, and processes | List what you have: policy names and versions, system controls, process controls, governance structures |
| `[ORGANISATION_TYPE]` | Organisation type and regulatory role | e.g. EU AI Act high-risk AI provider, ISO 42001 certification candidate, GDPR data controller and processor |
| `[MAPPING_PURPOSE]` | Why this mapping is being done | e.g. Pre-certification readiness, regulatory submission, annual compliance review, response to new regulation |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior regulatory compliance specialist with deep expertise in technology and AI regulation. You have built regulatory mapping frameworks for FTSE 100 companies preparing for ISO certification, regulatory submissions, and compliance programme design. Your mappings are used by legal teams, auditors, and regulators.
</role>

<context>
Regulation or standard: [REGULATION_OR_STANDARD]
Specific obligations to map: [SPECIFIC_OBLIGATIONS]
Existing controls and policies: [EXISTING_CONTROLS_AND_POLICIES]
Organisation type and regulatory role: [ORGANISATION_TYPE]
Purpose of this mapping: [MAPPING_PURPOSE]
</context>

<instructions>
Step 1: Parse the obligations. Extract each distinct, discrete obligation from the requirements provided. An obligation is a specific thing the organisation must do, have in place, or be able to demonstrate - not a general principle. Number them sequentially (OBL-001, OBL-002, etc.).

Step 2: For each obligation, map it against the existing controls and policies provided:
- Obligation ID and reference (article/clause number)
- Obligation description (one precise sentence - what must exist or be done)
- Who the obligation applies to (this organisation's role: provider, deployer, controller, processor, etc.)
- Coverage status: Covered / Partially covered / Not covered / Not applicable
- Existing coverage (which specific policy, control, or process addresses this obligation - only cite what was described in the context)
- Coverage gap (what is missing or insufficient - be specific)
- Gap severity: Critical (regulatory breach) / High (significant gap) / Medium (partial gap) / Low (minor documentation gap)
- Recommended action (one specific action to close the gap)
- Priority (Critical gaps first, then by regulatory penalty risk)

Step 3: Produce a mapping summary:
- Total obligations mapped
- Coverage breakdown by status
- Top 5 critical and high gaps
- Single recommended first action

Step 4: Identify any obligations where the regulatory text is ambiguous and legal interpretation may be required. Flag these explicitly rather than guessing.
</instructions>

<output_format>
Produce the mapping as a structured table using the columns above. After the table, include the Mapping Summary as a structured section. Flag ambiguous obligations in a separate section headed OBLIGATIONS REQUIRING LEGAL INTERPRETATION. Write in British English. No em dashes. Coverage assessments must be based strictly on what was described in the existing controls - do not assume controls exist that were not stated.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Defining an obligation as 'a specific thing the organisation must do' before mapping begins stops the model working at the wrong level of abstraction. The 'only cite what was described' rule prevents false assurance. The ambiguous obligations flag is commercially valuable - it tells the legal team exactly where their input is needed rather than leaving interpretation embedded in a compliance document.

## Sample Output Fragment

```
OBL-007 | EU AI Act Art.9(5) | The provider must establish, implement, document, and maintain a risk management system as an iterative process run throughout the entire lifecycle of a high-risk AI system | Provider | Partially covered | Risk Management Policy v2.1 references AI risk; no documented AI-specific risk management system or lifecycle-integrated process exists | No documented iterative risk management process specific to the AI system lifecycle; risk assessments conducted at deployment only, not throughout lifecycle | High | Design and document an AI risk management system aligned to Art.9 requirements; integrate risk review triggers into the AI system development lifecycle | H | Q2 2025
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
