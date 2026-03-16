# 30. Risk and Compliance Committee Report

**Domain:** Board Reporting
**Level:** Advanced

## Use Case

Produce a structured risk and compliance management report for Risk Committees, ExCo, Operating Committees, or Audit Committees. Covers the reporting period's key developments, risk position, compliance status, incidents, and actions required.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[REPORT_TYPE]` | The committee or audience this report is for | e.g. Risk Committee, Audit Committee, ExCo, Operating Committee, Compliance Committee |
| `[ORGANISATION]` | Organisation name | e.g. Nationwide Building Society |
| `[REPORTING_PERIOD]` | The period this report covers | e.g. Q3 2025 (1 July to 30 September 2025) |
| `[KEY_DEVELOPMENTS]` | Significant events, changes, or issues during the period | e.g. Two P2 incidents, one regulatory request for information from FCA, DORA programme milestone achieved, new AI system deployed |
| `[RISK_AND_COMPLIANCE_METRICS]` | Current metrics and status figures | e.g. Open risks: 14 (3 Red, 6 Amber, 5 Green); Overdue actions: 7; Policy exceptions: 2; Incidents this period: 4 |
| `[ACTIONS_AND_DECISIONS_REQUIRED]` | What the committee needs to approve, note, or decide | e.g. Approve revised risk appetite statement, note the FCA response timeline, escalate overdue remediation to ExCo |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a Chief Risk Officer and Head of Compliance with 20 years of experience writing committee reports for regulated financial institutions, healthcare organisations, and global corporations. Your reports are known for being crisp, decision-focused, and free of padding. You give committees what they need to discharge their oversight obligations - not what they want to hear.
</role>

<context>
Report type: [REPORT_TYPE]
Organisation: [ORGANISATION]
Reporting period: [REPORTING_PERIOD]
Key developments during the period: [KEY_DEVELOPMENTS]
Risk and compliance metrics: [RISK_AND_COMPLIANCE_METRICS]
Actions and decisions required: [ACTIONS_AND_DECISIONS_REQUIRED]
</context>

<instructions>
Step 1: DIAGNOSTIC. Before drafting, assess the information provided:
- What is the overall risk direction of travel? (improving / stable / deteriorating - based on metrics and developments provided)
- Which single development from the period is most significant and why?
- Are there any overdue actions or unresolved issues that require escalation in this report?
- Is any section of this report likely to be incomplete because insufficient information was provided? If so, flag it explicitly rather than inventing data.
State this assessment in 3-4 sentences before proceeding.

Step 2: Write a complete [REPORT_TYPE] report for [REPORTING_PERIOD] covering the following sections:

1. EXECUTIVE SUMMARY (max 150 words): The three most significant developments of the period, the overall risk and compliance position, and the specific actions required from this committee. Written for a board member reading this in 2 minutes.

2. RISK POSITION: Current risk profile based on the metrics provided. Present as a structured summary: overall position, movement since last period (improving / stable / deteriorating), top risks by residual score, and any risks approaching or breaching tolerance.

3. COMPLIANCE STATUS: Regulatory and policy compliance position. Cover: active regulatory matters, policy compliance, known breaches or near-misses, upcoming regulatory deadlines, and any areas where the organisation's position is uncertain.

4. INCIDENTS AND EVENTS: Summary of incidents and significant events during the period. For each: description, severity, current status, and impact on risk position.

5. ACTIONS AND REMEDIATION: Status of open actions from prior periods. Flag overdue actions with escalation recommendation. New actions arising from this period.

6. FORWARD LOOK: Key risks and compliance obligations coming in the next quarter. Regulatory deadlines, planned activities with risk implications, and any emerging risks on the horizon.

7. DECISIONS AND APPROVALS REQUIRED: A numbered list of the specific decisions or approvals this committee is asked to make. One per line. Specific and actionable.
</instructions>

<output_format>
Use bold section headings. Use RAG status indicators (Red / Amber / Green) for risk and compliance status. Use tables for the risk position summary and actions tracker. Write in British English. No em dashes. Active voice throughout. Every statement must be traceable to the information provided - no invented metrics or events. If the information provided is insufficient to complete a section, state what additional information is needed rather than inventing it.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The 150-word limit on the executive summary enforces the discipline that committees require but drafters resist. 'Do not state what they want to hear' prevents the common failure of sanitising bad news before it reaches a committee. The 'state what information is needed rather than inventing it' instruction prevents hallucinated metrics - the most dangerous failure mode in a committee report.

## Sample Output Fragment

```
1. EXECUTIVE SUMMARY

The overall risk position for [REPORTING_PERIOD] is AMBER, stable compared to the prior period. Three developments require committee attention: (1) two P2 incidents during the period, both now resolved, with root cause analyses pending review; (2) receipt of an FCA request for information on AI governance practices, response due 14 November 2025; and (3) seven actions from prior periods are now overdue, of which three have been outstanding for more than 90 days and are recommended for escalation to ExCo.

The committee is asked to: approve the revised risk appetite statement (item 7.1); note the FCA response timeline and confirm the designated lead; and direct management on the escalation of overdue actions.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
