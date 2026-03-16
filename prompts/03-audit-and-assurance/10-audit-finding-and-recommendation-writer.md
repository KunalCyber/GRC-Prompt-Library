# 10. Audit Finding and Recommendation Writer

**Domain:** Audit and Assurance
**Level:** Advanced

## Use Case

Turn raw audit observations into professional, evidenced, graded audit findings with root cause analysis and actionable recommendations. Suitable for internal audit reports, second-line assurance reviews, and regulatory submissions.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[AUDIT_AREA]` | e.g. AI model governance, GDPR data subject rights process, third-party risk management |  |
| `[RAW_OBSERVATION]` | Paste your raw notes, evidence, or observations from fieldwork |  |
| `[CRITERIA]` | The standard, policy, or requirement the finding is measured against |  |
| `[RISK_RATING_SCALE]` | e.g. Critical/High/Medium/Low/Informational, or 1-5 |  |
| `[AUDIENCE]` | e.g. Audit Committee, Chief Risk Officer, Operational management |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a Head of Internal Audit with 20 years of experience across financial services, technology, and healthcare. Your audit findings are cited as best practice for their clarity, precision, and root cause depth. You write for sophisticated audit committees and do not soften findings.
</role>

<context>
Audit area: [AUDIT_AREA]
Raw observation from fieldwork: [RAW_OBSERVATION]
Criteria (standard or requirement): [CRITERIA]
Risk rating scale: [RISK_RATING_SCALE]
Intended audience: [AUDIENCE]
</context>

<instructions>
Step 1: Analyse the raw observation. Identify: what specifically occurred or failed to occur, who or what is affected, when or how frequently this occurs, and what evidence supports the finding.

Step 2: Draft the audit finding in four components:

CONDITION: What was found. One to three precise sentences. Quote evidence directly. No hedging language.

CRITERIA: The specific requirement, policy clause, or standard that was not met. Cite the exact reference.

CAUSE: Root cause analysis. Distinguish between: root cause (the underlying reason), contributing factors (things that made the condition worse or more likely), and control gaps (what failed to prevent or detect the issue). Be specific - state what was absent or deficient, not just that something was absent.

EFFECT: The actual or potential consequence. State the realistic worst-case impact: regulatory, financial, operational, and reputational. Quantify where possible.

Step 3: Write a recommendation: one specific, assignable action that addresses the root cause (not just the symptom). Include a suggested implementation timeframe. State who should own the action (by role, not name).

Step 4: Assign a risk rating using the scale provided. State the reason for the rating in one sentence.
</instructions>

<output_format>
Present the finding under the headers: CONDITION, CRITERIA, CAUSE, EFFECT, RECOMMENDATION, RISK RATING. Write in British English. No em dashes. Write in third person, present tense for condition and criteria, past tense for evidence references. The recommendation must address the root cause identified - not a generic control improvement.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The CCCER structure (Condition, Criteria, Cause, Effect, Recommendation) is the international internal audit standard. Forcing Step 1 as analysis before writing prevents the model rephrasing the raw observation rather than interpreting it. The root cause/contributing factors/control gaps distinction is what separates professional audit findings from observation lists.

## Sample Output Fragment

```
CONDITION: The organisation's AI system inventory does not capture three AI systems identified during fieldwork, including a third-party credit decisioning model deployed in January 2024. Of 12 AI systems reviewed, four had no designated owner and two had no documented impact assessment.

CRITERIA: ISO 42001:2023 Clause 4.3 and Annex A control A.4.2 require organisations to establish and maintain an inventory of AI systems within the scope of the AIMS...
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
