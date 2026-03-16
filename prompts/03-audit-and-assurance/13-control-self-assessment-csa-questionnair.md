# 13. Control Self-Assessment (CSA) Questionnaire

**Domain:** Audit and Assurance
**Level:** Essential

## Use Case

Draft a targeted questionnaire to send to a system owner, process owner, or team lead to confirm that a specific control is actually operating as designed. The practical tool that closes the gap between 'the control exists on paper' and 'the control is being performed.'

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CONTROL_OR_PROCESS]` | The control or process being self-assessed | e.g. Quarterly user access review for production systems, Monthly AI model performance monitoring, Supplier security due diligence process, Data subject access request handling |
| `[RESPONDENT_ROLE]` | Who will complete this questionnaire | e.g. System Administrator, Head of IT Operations, Data Protection Officer, Line manager, AI system owner |
| `[CONTROL_STANDARD]` | The standard or policy the control must satisfy | e.g. ISO 27001 A.5.18 (access rights), ISO 42001 A.9.4 (performance monitoring), GDPR Article 12 (SAR response timeframes), Internal IT policy Section 6 |
| `[ASSESSMENT_PERIOD]` | The period the questionnaire covers | e.g. Last quarter (1 July - 30 September 2025), Last 12 months, Current state as at today's date |
| `[EVIDENCE_REQUIRED]` | Whether the respondent should attach supporting evidence | e.g. Yes - attach the most recent access review report; Yes - attach a sample of 3 completed process records; No - written confirmation only |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior internal auditor and controls specialist. You write CSA questionnaires that surface genuine control failures, not just confirmation of what people think the auditor wants to hear. Your questions are specific, unambiguous, and written in the language of the person completing them - not in audit jargon.
</role>

<context>
Control or process: [CONTROL_OR_PROCESS]
Respondent role: [RESPONDENT_ROLE]
Control standard: [CONTROL_STANDARD]
Assessment period: [ASSESSMENT_PERIOD]
Evidence required: [EVIDENCE_REQUIRED]
</context>

<instructions>
Produce a complete CSA questionnaire.

Part A: Questionnaire Introduction (for the respondent)
Two to three sentences explaining: what they are being asked to do, why, how long it should take, and what happens with their responses. Tone: professional and non-threatening. Do not use audit language ('compliance', 'control effectiveness') in the introduction - use operational language ('confirming the process is working as expected').

Part B: The Questions
Produce 8-15 questions covering three categories:

Category 1 - Process Existence (3-4 questions): Confirm that the process is formally defined, understood, and owned.
Category 2 - Process Operation (4-6 questions): Confirm that the process was actually performed during the assessment period, at the required frequency, by the correct people, using the correct tools.
Category 3 - Process Effectiveness (2-4 questions): Confirm that exceptions were identified and addressed, that the process produced its intended output, and that the respondent is confident it is working correctly.

For every question:
- Write it in plain English appropriate to the respondent's role (not audit language)
- Use specific, closed questions where possible ('How many access reviews were completed in this period?' not 'Were access reviews completed?')
- Include a space for the respondent to provide evidence reference or free-text comment where the answer is not simply yes/no
- Flag questions that are highest-risk if answered negatively (these are the ones to follow up on)

Part C: Scoring and Escalation Guide (for the assessor)
A simple guide showing: which answers indicate a control is operating effectively, which indicate partial operation, and which should trigger an immediate follow-up or escalation.
</instructions>

<output_format>
Present each Part with a bold heading. Questions as a numbered form with response fields (Yes/No/Partial + Comment field). Mark highest-risk questions with [HIGH RISK] flag. Write in British English. No em dashes. Questions must be written for the stated respondent role - a System Administrator and a Head of Operations need different language for the same underlying control question.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The distinction between Process Existence, Process Operation, and Process Effectiveness questions is the difference between a CSA that confirms a control exists and one that confirms it works. Most CSAs only test existence. The 'closed questions where possible' instruction eliminates the 'yes we do that' responses that give false assurance. The HIGH RISK flag tells the assessor where to focus follow-up effort.

## Sample Output Fragment

```
Category 2: Process Operation

6. [HIGH RISK] How many user access reviews were completed for production systems during [ASSESSMENT_PERIOD]? Please state the number and the systems covered.
[ ] Response: ________________
[ ] Evidence attached: ________________

Note to assessor: Expected answer is one review per system per quarter. If the number is lower than expected, or if any production system was not reviewed, this requires immediate follow-up. A partial answer ('some were done') should be treated as a red flag.

7. When the last access review was completed, how many user accounts were identified as requiring action (removal, modification, or escalation for approval)?
[ ] Response: ________________
Note to assessor: A zero response is a red flag unless the system is very small - most access reviews identify at least some accounts requiring action. Zero may indicate the review was not performed rigorously.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
