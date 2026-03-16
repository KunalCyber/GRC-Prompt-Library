# 19. Human-in-the-Loop (HITL) Workflow Architect

**Domain:** AI Governance
**Level:** Practitioner

## Use Case

Design the workflow for how a human operator reviews, validates, and where necessary overrides an AI system decision. Directly implements ISO 42001 Annex A.9.2 (human oversight of AI systems) and EU AI Act Article 14. Produces a workflow specification ready for IT implementation and process documentation.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[AI_SYSTEM]` | The AI system requiring human oversight | e.g. Credit limit recommendation engine, AI-assisted claims triage, Automated HR screening tool, AI diagnostic support system |
| `[DECISION_TYPE]` | What decisions the AI system makes or influences | e.g. Recommends credit limit changes (financial impact up to GBP 10,000), classifies insurance claims by complexity and fraud risk, ranks job applicants for shortlisting |
| `[RISK_CLASSIFICATION]` | The risk level of this AI system | e.g. High-risk under EU AI Act Annex III, Limited risk, Internal use only / not customer-facing |
| `[HUMAN_OPERATORS]` | Who the human reviewers are | e.g. Credit underwriters (team of 12, 8-hour shifts), Claims handlers (distributed team, 24/7), HR business partners (8 people, office hours only) |
| `[VOLUME_AND_SLA]` | Processing volumes and time constraints | e.g. 400 AI recommendations per day, 2-hour SLA for customer notification; 150 claims per day, 24-hour triage SLA |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance specialist and business process designer with expertise in human-AI interaction, operational risk, and regulatory compliance. You have designed HITL workflows for regulated AI systems in financial services, healthcare, and insurance. Your workflows satisfy regulators, work in practice, and do not create bottlenecks that cause AI systems to be circumvented.
</role>

<context>
AI system: [AI_SYSTEM]
Decision type and financial/operational impact: [DECISION_TYPE]
Risk classification: [RISK_CLASSIFICATION]
Human operators: [HUMAN_OPERATORS]
Volume and SLA: [VOLUME_AND_SLA]
</context>

<instructions>
Design a complete Human-in-the-Loop oversight workflow.

Part A: Oversight Model Design
Determine and justify the appropriate oversight model:
- Human-in-the-loop: human reviews every AI output before action is taken
- Human-on-the-loop: AI acts, human monitors and can intervene
- Risk-tiered: low-risk outputs auto-approve, high-risk outputs require human review
Justify the recommended model based on the risk classification, volume, and SLA stated.

Part B: Review Triggers
Specify exactly which AI outputs require human review. For a risk-tiered model: what confidence thresholds, decision values, or output characteristics trigger review. Be specific - not 'high-risk outputs' but 'any recommendation affecting more than GBP X' or 'any output with confidence score below Y%'.

Part C: Review Interface Specification
What information must be presented to the human reviewer to enable an informed decision:
- AI output and confidence score
- Key factors that drove the AI recommendation (explainability requirement)
- Relevant context about the individual or case
- What the reviewer must decide (approve / modify / reject / escalate)
- Time available for the review (given the SLA)

Part D: Override Protocol
Exactly how a human reviewer overrides an AI decision:
- The action they take in the system
- What they must record (reason for override, alternative decision made)
- Who is notified of the override
- How overrides are aggregated and reviewed (this data feeds back to model improvement)

Part E: Audit Trail Requirements
What must be logged for every HITL interaction to satisfy regulatory requirements. Include: the AI output, the human decision, the time taken, the identity of the reviewer, and any override reason.

Part F: Escalation Path
What happens when the reviewer is uncertain. Who to escalate to, within what timeframe, and what information to pass.
</instructions>

<output_format>
Present each Part with a bold heading. Use a process flow description (numbered steps) for Part C and Part D. Use a table for Part E (columns: Data element | Source | Retention period | Access controls). Write in British English. No em dashes. The workflow must be operationally realistic given the volumes, SLA, and staffing described - not a theoretically ideal process that cannot be executed.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The override logging requirement in Part D is the element that most HITL designs omit - and it is the most valuable data in the system. Override patterns reveal where the AI model is systematically wrong and drive model improvement. Part F escalation path prevents the worst real-world outcome: reviewers rubber-stamping AI decisions when they are uncertain because there is no clear path to get help.

## Sample Output Fragment

```
Part B: Review Triggers (Risk-Tiered Model)

Auto-approve (no human review required):
- AI recommendation to maintain existing credit limit with confidence score above 85%
- Recommendation change of less than GBP 500 with confidence above 80%

Human review required (standard):
- Any recommendation to decrease a credit limit regardless of confidence score
- Any recommendation affecting customers flagged as financially vulnerable in the CRM
- Confidence score below 75% for any recommendation
- Any recommendation that would place a customer's total credit exposure above GBP 15,000

Senior reviewer required (escalated):
- Any recommendation where the model confidence score and the customer's recent payment history are in direct conflict
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
