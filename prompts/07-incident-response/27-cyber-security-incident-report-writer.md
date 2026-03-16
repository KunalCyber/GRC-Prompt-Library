# 27. Cyber Security Incident Report Writer

**Domain:** Incident Response
**Level:** Practitioner

## Use Case

Produce a complete, professional cyber security incident report from raw incident notes, timeline data, and technical findings. Suitable for board reporting, regulatory submission, insurance claims, and post-incident reviews. Covers what happened, root cause, impact, response actions, and lessons learned.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[INCIDENT_SUMMARY]` | Brief description of what happened | e.g. Ransomware deployed on 14 servers following successful phishing attack on 3 November; production systems offline for 18 hours |
| `[INCIDENT_TIMELINE]` | Chronological sequence of events | Paste your incident log, timeline notes, or bullet points - raw format is fine |
| `[IMPACT]` | What was affected and to what extent | e.g. 3,400 customer records potentially accessed; payment processing offline 18 hours; estimated recovery cost GBP 240k; no confirmed data exfiltration |
| `[RESPONSE_ACTIONS]` | What was done to respond and recover | e.g. Systems isolated within 2 hours; backup restoration completed 18 hours post-detection; threat actor persistence removed; all passwords reset |
| `[ORGANISATION_AND_AUDIENCE]` | Organisation name and who this report is for | e.g. Fintech Ltd - report for Audit Committee and ICO notification; or CISO report for board |
| `[REGULATORY_CONTEXT]` | Any regulatory notification obligations | e.g. GDPR Article 33 (ICO notification required within 72 hours); FCA operational incident reporting; or 'internal use only' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior cyber security incident manager and GRC specialist with 15 years of experience writing incident reports for regulated organisations, regulatory submissions, and board briefings. Your reports are known for being factual, well-structured, and forensically credible. You do not speculate beyond the evidence and you do not minimise findings to protect the organisation's reputation.
</role>

<context>
Incident summary: [INCIDENT_SUMMARY]
Timeline: [INCIDENT_TIMELINE]
Impact: [IMPACT]
Response actions taken: [RESPONSE_ACTIONS]
Organisation and audience: [ORGANISATION_AND_AUDIENCE]
Regulatory context: [REGULATORY_CONTEXT]
</context>

<instructions>
Step 1: Structure the timeline. Organise the raw timeline data into a clean chronological sequence. Identify: the initial compromise or trigger event, the detection point, the escalation point, and the recovery completion point. Calculate key time intervals: time to detect, time to escalate, time to contain, time to recover.

Step 2: Write the incident report covering these sections:

EXECUTIVE SUMMARY (max 200 words): What happened, when, the business impact, and the current status. Written for a board member or regulator. No technical jargon.

INCIDENT TIMELINE: Clean chronological table of events with columns: Date/Time | Event | Action Taken | By Whom (role).

TECHNICAL FINDINGS: What was compromised, how the attacker gained access, what they did once inside, what data or systems were affected. Based strictly on the information provided - flag where findings are preliminary or unconfirmed.

IMPACT ASSESSMENT: Quantified impact across: operational (systems and services affected, duration), data (records affected, sensitivity, confirmed or potential exfiltration), financial (direct costs, recovery costs, potential regulatory fines), reputational (customer notification required, media exposure).

RESPONSE ASSESSMENT: What went well, what could have been faster or more effective. Honest assessment against the incident response plan if one existed.

ROOT CAUSE ANALYSIS: The primary root cause and contributing factors. Use the Five Whys approach. Distinguish between the technical cause and the organisational cause.

LESSONS LEARNED AND CORRECTIVE ACTIONS: Numbered list of specific actions to prevent recurrence and improve response capability. Each action: owner (by role), target date, and success measure.

REGULATORY AND NOTIFICATION STATUS: Based on the regulatory context provided, state what notifications are required, to whom, by when, and what has been submitted.
</instructions>

<output_format>
Present each section with a bold heading. Timeline as a table. Impact assessment as a structured table by category. Lessons learned as a numbered list with owner and date columns. Write in British English. No em dashes. Where information is missing or preliminary, flag explicitly rather than omitting or speculating. The report must be factually accurate to the information provided - do not embellish or add details not in the source material.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The Five Whys root cause instruction is what separates a findings report from an incident report - regulators and insurers require causal analysis, not just event description. The 'flag preliminary findings' instruction prevents the report being used as definitive evidence before investigation is complete. The honest response assessment section is what most organisations omit and what audit committees most need to see.

## Sample Output Fragment

```
ROOT CAUSE ANALYSIS

Primary technical cause: A phishing email bypassed email filtering controls and was opened by a member of the finance team. The link led to credential harvesting, and the captured credentials had access to production file servers without MFA enforcement.

Five Whys:
1. Why did ransomware deploy? Attacker had valid credentials with sufficient system access.
2. Why did they have that access? Finance role had over-provisioned access rights not reviewed since 2021.
3. Why were access rights not reviewed? No periodic access review process was operating for this user group.
4. Why was MFA not enforced? MFA rollout excluded legacy systems; finance team used a legacy application.
5. Why was this gap not identified? Legacy system exclusions were not documented as accepted risks or flagged for remediation.

Organisational root cause: Absence of a periodic access review process and undocumented exceptions to the MFA policy.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
