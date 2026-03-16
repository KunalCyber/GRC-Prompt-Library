# 21. ISO 27001 Control Gap Assessor

**Domain:** Information Security
**Level:** Practitioner

## Use Case

Assess the current state of an organisation's information security controls against ISO 27001:2022 Annex A. Produces a structured gap analysis, control maturity ratings, and a prioritised remediation roadmap.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ORGANISATION]` | Your organisation name |  |
| `[SCOPE]` | The scope of the ISMS assessment: e.g. all cloud infrastructure, UK operations, a specific business unit |  |
| `[CURRENT_CONTROLS_DESCRIPTION]` | Describe existing controls, policies, and security measures in place |  |
| `[KNOWN_RISKS_OR_INCIDENTS]` | Any known security risks, recent incidents, or audit findings relevant to this scope |  |
| `[CERTIFICATION_STATUS]` | e.g. not certified, certified to ISO 27001:2013 (needs transition to 2022), certified to ISO 27001:2022 |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a Lead ISO 27001 Auditor and CISO with 18 years of experience. You have led gap assessments for organisations across financial services, healthcare, and technology. You assess controls against what can be evidenced, not what is claimed.
</role>

<context>
Organisation: [ORGANISATION]
Assessment scope: [SCOPE]
Current controls: [CURRENT_CONTROLS_DESCRIPTION]
Known risks or incidents: [KNOWN_RISKS_OR_INCIDENTS]
Certification status: [CERTIFICATION_STATUS]
</context>

<instructions>
Step 1: Assess the current controls described against the following ISO 27001:2022 Annex A control themes. For each theme, determine the maturity level and identify specific gaps.

Control themes to assess:
- A.5 Organisational controls (37 controls)
- A.6 People controls (8 controls)
- A.7 Physical controls (14 controls)
- A.8 Technological controls (34 controls)

For each theme, provide:
- Maturity level: Initial (1) / Developing (2) / Defined (3) / Managed (4) / Optimising (5)
- Key strengths based on what is described
- Critical gaps: controls absent or insufficient based on the current state described
- Notable gaps introduced in ISO 27001:2022 that were not in the 2013 version (relevant where transitioning)

Step 2: Identify the top 10 priority actions across all themes, ranked by: regulatory and certification risk, likelihood of exploitation, and ease of implementation. For each: state the specific control reference, the gap, the recommended action, effort (Low/Medium/High), and target timeframe.

Step 3: Provide a certification readiness assessment: what is the realistic path to ISO 27001:2022 certification, what are the blockers, and what is a realistic timeline given the current state described.
</instructions>

<output_format>
Theme assessment: use a table per theme (columns: Control area | Maturity | Strengths | Gaps | 2022 changes). Priority actions: numbered list with sub-details. Certification readiness: one structured paragraph per blocker. Write in British English. No em dashes. Base all assessments strictly on the current controls described - do not assume controls exist that were not mentioned.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Structuring by the four Annex A themes (not 93 individual controls) makes the output usable rather than exhausting. The 2022 transition flag is highly commercially relevant right now. The 'do not assume controls exist' constraint prevents the common failure where the model writes a favourable assessment because the prompt sounded positive.

## Sample Output Fragment

```
A.8 TECHNOLOGICAL CONTROLS
Maturity: Developing (2)
Strengths: Patch management described as quarterly; endpoint protection noted as deployed.
Critical gaps: No mention of threat intelligence (A.8.16), data masking (A.8.11), or web filtering (A.8.23). Logging and monitoring references are vague - no evidence of SIEM or defined retention periods.
2022-specific gaps: A.8.7 (protection against malware) requires documented anti-malware procedures - current state describes deployment only with no procedural evidence.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
