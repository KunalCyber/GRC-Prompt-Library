# 02. Operational Risk Assessment

**Domain:** Risk Management
**Level:** Practitioner

## Use Case

Conduct a structured operational risk assessment for any business process, project, system change, or new initiative. Produces a complete risk assessment with inherent and residual scoring, control gaps, and treatment plan - ready for risk committee submission.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[SUBJECT]` | What is being risk-assessed | e.g. Migration of payroll system to cloud provider, launch of AI-powered customer service chatbot, implementation of new third-party KYC service |
| `[ORGANISATION]` | Organisation name and type | e.g. Aviva Insurance, UK general insurer regulated by PRA and FCA |
| `[RISK_FRAMEWORK]` | The risk framework or methodology to apply | e.g. ISO 31000, COSO ERM, your organisation's 3x3 / 5x5 risk matrix, NIST RMF |
| `[EXISTING_CONTROLS]` | Controls currently in place relevant to this subject | List what exists - policies, technical controls, process controls, oversight mechanisms |
| `[RISK_OWNER]` | The role accountable for this risk assessment | e.g. Head of Technology, Chief Operating Officer, Data Protection Officer |
| `[ASSESSMENT_PURPOSE]` | Why this assessment is being conducted | e.g. Pre-launch sign-off requirement, annual risk review, regulatory submission, post-incident review |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior operational risk manager with 15 years of experience in enterprise risk assessment across financial services, healthcare, and critical national infrastructure. Your risk assessments are used for board submissions, regulatory filings, and project go/no-go decisions. You assess what is real, not what looks good.
</role>

<context>
Subject of assessment: [SUBJECT]
Organisation: [ORGANISATION]
Risk framework: [RISK_FRAMEWORK]
Existing controls: [EXISTING_CONTROLS]
Risk owner: [RISK_OWNER]
Purpose of assessment: [ASSESSMENT_PURPOSE]
</context>

<instructions>
Step 1: Identify risks. Systematically identify all material operational risks associated with [SUBJECT] across these categories: people risks, process risks, technology risks, legal and regulatory risks, third-party and dependency risks, data and information risks, reputational risks. For each category, identify specific risks - not categories. A risk is a specific event or condition, not a general topic.

Step 2: For each identified risk, complete a full risk record:
- Risk ID (ORA-001, ORA-002, etc.)
- Risk category
- Risk event description (one sentence: what could happen, to what, with what consequence)
- Root cause (why this could happen given the specific subject)
- Inherent likelihood (1-5, where 5 = near certain in the next 12 months without any controls)
- Inherent impact (1-5, where 5 = catastrophic: regulatory action, major financial loss, or significant harm to individuals)
- Inherent risk score (L x I) and RAG (Red 15-25, Amber 8-14, Green 1-7)
- Current controls (specific, from the existing controls listed, or state 'None identified')
- Control effectiveness (Effective / Partially effective / Ineffective / Not tested)
- Residual likelihood (1-5)
- Residual impact (1-5)
- Residual risk score and RAG
- Risk treatment (Accept / Mitigate / Transfer / Avoid)
- Treatment action (one specific action if treatment is Mitigate - must address the root cause)
- Treatment owner (by role)
- Target date for treatment

Step 3: Write an assessment summary (max 200 words): overall residual risk rating for the subject, top three risks by residual score, recommended risk disposition (proceed / proceed with conditions / do not proceed), and any conditions that must be met before proceeding.
</instructions>

<output_format>
Produce the risk register as a structured table using the columns above. After the table, include the Assessment Summary under a bold heading. Include a completed document header: Subject, Assessment date, Assessor role, Risk owner, Framework used, Assessment purpose. Write in British English. No em dashes. Risk descriptions must be specific to the stated subject - no generic risk statements.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Defining a risk as 'a specific event or condition, not a general topic' is the instruction that most improves output quality - it stops the model listing 'cybersecurity risk' instead of 'unauthorised access to payroll data by a cloud provider employee during migration'. The root cause column forces causal thinking, not just event listing. The go/no-go disposition is what decision-makers actually need from a risk assessment.

## Sample Output Fragment

```
ORA-003 | Technology | Payroll data is exposed during transit to the cloud provider due to misconfigured encryption settings during the initial migration window, resulting in a notifiable personal data breach | Root cause: Manual configuration of encryption at rest and in transit has no automated verification step | 3 | 5 | 15 | RED | TLS 1.3 specified in migration plan; no pre-migration encryption verification test documented | Partially effective | 2 | 5 | 10 | AMBER | Mitigate | Commission independent encryption verification test before data migration commences | Head of Cyber Security | 30 days before migration date
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
