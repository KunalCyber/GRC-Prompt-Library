# 26. AI Incident Response Playbook

**Domain:** Incident Response
**Level:** Advanced

## Use Case

Draft a structured AI incident response playbook for a specific AI system or class of AI risk. Covers detection, assessment, escalation, containment, notification, and post-incident review.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ORGANISATION]` | Your organisation name |  |
| `[AI_SYSTEM]` | The AI system or class of AI incident this playbook covers |  |
| `[REGULATORY_CONTEXT]` | e.g. EU AI Act Article 73 (serious incident reporting), FCA rules, GDPR Article 33 |  |
| `[ESCALATION_STRUCTURE]` | Key roles: who is the AI system owner, who is the CISO/CRO, who is the DPO, who is legal counsel |  |
| `[SEVERITY_SCALE]` | e.g. P1/P2/P3, Critical/High/Medium/Low, or describe your existing severity framework |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior incident response specialist and AI governance expert. You have written incident response playbooks for regulated AI systems in financial services and healthcare. Your playbooks are operable under pressure: clear, decision-tree structured, and unambiguous.
</role>

<context>
Organisation: [ORGANISATION]
AI system in scope: [AI_SYSTEM]
Regulatory notification obligations: [REGULATORY_CONTEXT]
Escalation roles: [ESCALATION_STRUCTURE]
Severity classification scale: [SEVERITY_SCALE]
</context>

<instructions>
Draft a complete AI incident response playbook with the following phases:

PHASE 1 - DETECTION AND LOGGING: Define what constitutes an AI incident for this system (be specific: model performance degradation, biased outputs, data breach via AI, system unavailability, adversarial attack, regulatory notification trigger). Define how incidents are reported and logged.

PHASE 2 - INITIAL ASSESSMENT (within 1 hour): Severity classification criteria using the stated scale. Decision tree: what questions must be answered to classify severity. Who is notified at each severity level.

PHASE 3 - ESCALATION AND RESPONSE TEAM ACTIVATION: Who is activated at each severity level, what their specific responsibilities are, and the communication channel to use.

PHASE 4 - CONTAINMENT: Specific containment actions for this AI system - when to suspend the system, when to revert to a prior model version, when to switch to a manual fallback process.

PHASE 5 - REGULATORY AND EXTERNAL NOTIFICATION: Using the regulatory context provided, specify: what threshold triggers a notification obligation, to whom, within what timeframe, and what information must be included.

PHASE 6 - RESOLUTION AND RECOVERY: Criteria for declaring the incident resolved. Steps required before the AI system is returned to production.

PHASE 7 - POST-INCIDENT REVIEW: Required review activities, timeline, outputs (root cause report, control improvements, lessons learned).
</instructions>

<output_format>
Present each phase with a bold heading. Use numbered steps within each phase. For decision points, use IF/THEN format (e.g. IF severity is Critical THEN activate [role] within 30 minutes). Include a one-page Summary Response Card at the end showing: incident types, severity criteria, notification timeframes, and key contacts (by role). Write in British English. No em dashes. All timeframes must be specific - do not use 'as soon as possible' or 'promptly'.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The seven-phase structure matches ISO 22301 and NIST SP 800-61 incident response frameworks that regulators expect to see. The IF/THEN format for decision points eliminates ambiguity under pressure. The Summary Response Card instruction forces the model to produce the one-page reference that response teams actually use during an incident.

## Sample Output Fragment

```
PHASE 2 - INITIAL ASSESSMENT (complete within 60 minutes of detection)

2.1 Answer the following questions to classify severity:

IF the incident involves outputs that may have directly harmed an individual (financial loss, physical harm, discrimination) THEN classify as [P1/Critical] immediately without further assessment.

IF the incident involves a potential personal data breach affecting 100+ individuals THEN classify as [P1/Critical] and notify the Data Protection Officer within 30 minutes.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
