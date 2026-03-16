# 14. Tabletop Exercise Facilitator Guide

**Domain:** Audit and Assurance
**Level:** Practitioner

## Use Case

Build a complete tabletop exercise for any GRC scenario - cyber incident, AI system failure, data breach, business disruption, regulatory investigation, or third-party failure. Produces a full facilitator guide with scenario injects, discussion questions, evaluation criteria, and a debrief structure. Ready to run with no additional preparation.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[EXERCISE_SCENARIO]` | The scenario the exercise will test | e.g. Ransomware attack on core banking systems; AI credit model produces discriminatory outputs at scale; critical cloud provider declares major outage; regulatory dawn raid |
| `[ORGANISATION]` | Organisation name and type | e.g. NHS Trust, 4,000 staff; mid-size UK insurer regulated by PRA and FCA |
| `[PARTICIPANTS]` | Who will participate and their roles | e.g. CISO, CRO, Head of Operations, Legal Counsel, Head of Communications, DPO - 8 people total |
| `[OBJECTIVES]` | What the exercise is designed to test or improve | e.g. Test decision-making under the new incident response policy; identify gaps in regulatory notification procedures; assess inter-team coordination |
| `[DURATION]` | How long the exercise will run | e.g. 2 hours, half-day, 90 minutes |
| `[EXISTING_PLANS]` | Plans or procedures the exercise is testing | e.g. Cyber Incident Response Plan v2.1, AI Governance Policy Section 10; or 'no formal plans in place' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC exercise specialist and incident response consultant with 15 years of experience designing and facilitating tabletop exercises for regulated financial institutions, NHS trusts, and government departments. Your exercises are known for being realistic, appropriately challenging, and producing actionable findings rather than comfortable conclusions.
</role>

<context>
Exercise scenario: [EXERCISE_SCENARIO]
Organisation: [ORGANISATION]
Participants: [PARTICIPANTS]
Exercise objectives: [OBJECTIVES]
Duration: [DURATION]
Plans being tested: [EXISTING_PLANS]
</context>

<instructions>
Step 1: Exercise Design. Define the exercise structure fitting the stated duration: opening brief, scenario phases with injects, decision points, and debrief. Allocate time to each phase.

Step 2: Scenario Narrative. Write the opening scenario brief that is read to participants at the start. It must: establish realistic context, introduce the initial trigger event, create appropriate urgency without being implausible, and not reveal information the participants would not realistically know at that point.

Step 3: Scenario Injects. Produce 6-10 timed injects that escalate the scenario. Each inject: a new development that forces a decision or reveals a complication. At least one inject should challenge a gap in the existing plans or a common decision-making failure. For each inject: the inject text (what participants are told), the facilitator note (what you are testing), and two to three discussion questions to draw out the key issues.

Step 4: Evaluation Criteria. A structured observation checklist for the facilitator covering: decision quality, speed of escalation, communication effectiveness, regulatory awareness, and plan adherence. For each criterion: what good looks like, what poor looks like.

Step 5: Debrief Structure. A facilitator guide for the post-exercise debrief covering: hot debrief (immediate reactions, 15 minutes), structured review of each phase, identification of gaps and improvements, and action log template.

Step 6: Exercise Report Template. A one-page post-exercise report template capturing: exercise overview, key findings (strengths and gaps), priority actions, and sign-off.
</instructions>

<output_format>
Present each Step with a bold heading. Injects as a numbered table with columns: Inject # | Time | Inject Text | Facilitator Note | Discussion Questions. Evaluation criteria as a table. Debrief as a structured agenda. Write in British English. No em dashes. The scenario and injects must be specific to the organisation type and scenario described - not generic. The facilitator notes must identify what you are actually testing, not just describe the inject.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The facilitator note on each inject is the element most exercise designs omit - it tells the facilitator what they are looking for, which is what makes the exercise produce findings rather than just activity. The 'at least one inject challenging a gap in existing plans' instruction ensures the exercise is genuinely testing rather than confirming what participants already know. The separate hot debrief and structured review prevents the common failure where debrief time runs out.

## Sample Output Fragment

```
INJECT 3 | 35 minutes | 'Your IT team has confirmed the ransomware has spread to your backup systems. The primary backup is encrypted. Your secondary offsite backup is 48 hours old.' | FACILITATOR NOTE: Testing whether the team knows their actual RPO and what the business impact of 48-hour data loss is. Also testing whether anyone escalates to the board at this point per the incident escalation policy. | Discussion questions: (1) What is the business impact of losing 48 hours of transaction data? Which processes are most affected? (2) At what point does this incident require board notification - has that threshold been reached? (3) Who is responsible for communicating to customers whose transactions may be lost?
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
