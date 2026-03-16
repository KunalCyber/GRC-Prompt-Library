# 05. Regulatory Gap Analysis

**Domain:** Compliance
**Level:** Practitioner

## Use Case

Produce a structured gap analysis between your current state and a regulatory or framework requirement. Works for any standard: EU AI Act, ISO 42001, GDPR, ISO 27001, NIST CSF, SOC 2.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[REGULATION_OR_FRAMEWORK]` | e.g. EU AI Act, ISO 42001:2023, GDPR Article 35 |  |
| `[SPECIFIC_REQUIREMENTS]` | Paste the specific clauses, articles, or controls you want assessed |  |
| `[CURRENT_STATE_DESCRIPTION]` | Describe what you currently have in place: policies, processes, tools, evidence |  |
| `[ORGANISATION_TYPE]` | e.g. mid-size financial services firm, NHS trust, SaaS startup |  |
| `[TARGET_DATE]` | e.g. Q3 2025, August 2026 (EU AI Act GPAI deadline) |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior compliance consultant specialising in technology and AI regulation. You have led gap assessments for FTSE 100 companies, NHS trusts, and regulated fintechs. Your gap analyses are known for being specific, evidence-based, and directly actionable.
</role>

<context>
Regulation or framework: [REGULATION_OR_FRAMEWORK]
Requirements in scope: [SPECIFIC_REQUIREMENTS]
Current state: [CURRENT_STATE_DESCRIPTION]
Organisation type: [ORGANISATION_TYPE]
Target compliance date: [TARGET_DATE]
</context>

<instructions>
Step 1: Parse the requirements. List each distinct obligation or control from the requirements provided. Number them sequentially.

Step 2: For each requirement, assess the current state provided and determine:
- Compliance status: Compliant / Partial / Non-Compliant / Not Assessed
- Evidence of compliance (what exists that demonstrates compliance, based only on what was described)
- Gap description (what is missing or insufficient - be specific, not generic)
- Risk if unaddressed (regulatory, operational, or reputational consequence)
- Priority: Critical / High / Medium / Low (based on regulatory penalty risk and proximity to target date)
- Recommended action (one specific, implementable action with an indicative timeframe)

Step 3: Produce a gap summary showing: total requirements assessed, count by compliance status, count by priority, and a single recommended first action.
</instructions>

<output_format>
Produce a structured table with columns: Req ID | Requirement summary | Status | Evidence | Gap | Risk if unaddressed | Priority | Recommended action. After the table, provide the Gap Summary as a brief paragraph (max 80 words). Write in British English. No em dashes. Do not pad gaps with generic observations - every gap must be traceable to something missing from the current state described.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Forcing Step 1 (parse requirements first) stops the model hallucinating obligations. The 'based only on what was described' constraint prevents the model inventing evidence. The output format instruction eliminates the most common complaint about AI gap analyses: generic gaps that could apply to any organisation.

## Sample Output Fragment

```
R-003 | Article 13(1): Providers must ensure high-risk AI systems are transparent to deployers | Partial | Acceptable use documentation exists but does not cover AI system limitations or confidence thresholds | No documentation of model limitations or when human review is required | Regulatory: non-compliance with transparency obligations enforceable from August 2026 | High | Draft a System Transparency Card covering purpose, limitations, confidence thresholds, and override procedures by Q2 2025
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
