# 01. AI Risk Register Builder

**Domain:** Risk Management
**Level:** Practitioner

## Use Case

Build a structured, prioritised risk register for any AI system, project, or business function from scratch.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ORGANISATION]` | Your organisation name |  |
| `[AI_SYSTEM_OR_FUNCTION]` | e.g. customer-facing chatbot, credit scoring model, HR screening tool |  |
| `[INDUSTRY]` | e.g. financial services, healthcare, retail |  |
| `[RISK_APPETITE]` | e.g. low / medium / high, or paste your risk tolerance statement |  |
| `[FRAMEWORK]` | e.g. ISO 31000, NIST AI RMF, ISO 42001 Annex A, or your internal framework |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI risk manager with 15 years of experience in enterprise risk management and AI governance. You specialise in building structured, board-ready risk registers that practitioners can act on immediately.
</role>

<context>
Organisation: [ORGANISATION]
AI system or function: [AI_SYSTEM_OR_FUNCTION]
Industry: [INDUSTRY]
Risk appetite: [RISK_APPETITE]
Reference framework: [FRAMEWORK]
</context>

<instructions>
Step 1: Identify risks. Generate a comprehensive risk register covering all material risk categories for the specified AI system: technical risks (model failure, data quality, drift), operational risks (process failure, human oversight gaps), compliance and regulatory risks, reputational risks, third-party and supply chain risks, and ethical risks (bias, fairness, transparency).

Step 2: For each risk, provide:
- Risk ID (sequential, e.g. AI-001)
- Risk category
- Risk description (one specific sentence, no generic filler)
- Inherent likelihood (1-5)
- Inherent impact (1-5)
- Inherent risk score (likelihood x impact)
- Existing controls (brief, factual)
- Residual likelihood (1-5)
- Residual impact (1-5)
- Residual risk score
- RAG status (Red: 15-25, Amber: 8-14, Green: 1-7)
- Risk owner role (not a name, a role)
- Recommended treatment (one specific action)

Step 3: Produce a brief executive summary (max 5 bullets) identifying the top three residual risks and the single most urgent action.
</instructions>

<output_format>
Produce a markdown table for the risk register. Use the exact column headers listed above. After the table, add the executive summary as a numbered list under the heading EXECUTIVE SUMMARY. Write in British English. Do not use em dashes. No filler phrases. Every risk description must be specific to the stated AI system and industry - no generic placeholder text.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The stepped chain-of-thought instruction (identify, then score, then summarise) prevents the model collapsing straight to a generic table. The role anchors domain expertise. Context variables make every output specific rather than templated. Output format constraints eliminate the reformatting work practitioners hate.

## Sample Output Fragment

```
AI-001 | Technical | Model drift causes credit decisions to diverge from approved policy without triggering alerts | 3 | 4 | 12 | AMBER | Monthly performance monitoring | 3 | 3 | 9 | AMBER | Chief Risk Officer | Implement automated drift detection with 48hr alert escalation to model owner
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
