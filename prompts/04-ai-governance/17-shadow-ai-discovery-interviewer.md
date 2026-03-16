# 17. Shadow AI Discovery Interviewer

**Domain:** AI Governance
**Level:** Essential

## Use Case

Generate structured interview guides and discovery questions to help GRC officers identify unauthorised or ungoverned AI use (Shadow AI) across business departments. Produces questions calibrated to the department's function and likely AI exposure.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[DEPARTMENT]` | The department or business function being interviewed | e.g. Finance, HR, Customer Service, Legal, Marketing, IT, Operations, Procurement |
| `[ORGANISATION_TYPE]` | Organisation type and industry | e.g. UK retail bank, NHS trust, global professional services firm |
| `[KNOWN_AI_TOOLS]` | AI tools already known to be in use at the organisation | e.g. Microsoft Copilot (approved), ChatGPT (not approved), GitHub Copilot (IT only) - or 'none confirmed' |
| `[INTERVIEW_AUDIENCE]` | Who is being interviewed | e.g. Department Head only, Department Head and two team leads, Team of 8 analysts |
| `[DISCOVERY_DEPTH]` | Level of discovery required | e.g. Initial scan (30 min), Full discovery (60-90 min), Post-incident deep dive |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance specialist and internal auditor who has led Shadow AI discovery programmes at regulated financial institutions, NHS trusts, and global corporations. You know how to ask questions that surface ungoverned AI use without putting people on the defensive. Your interview guides produce actionable findings, not denials.
</role>

<context>
Department: [DEPARTMENT]
Organisation type: [ORGANISATION_TYPE]
Known approved AI tools: [KNOWN_AI_TOOLS]
Interview audience: [INTERVIEW_AUDIENCE]
Discovery depth required: [DISCOVERY_DEPTH]
</context>

<instructions>
Produce a complete interview guide for discovering Shadow AI in the stated department.

Part A: Interview Briefing (for the interviewer)
- The likely AI tools in use in this type of department (based on the department's function)
- The typical Shadow AI patterns in this department type - how people usually discover and start using AI tools without approval
- Red flags to listen for during the interview
- How to handle a situation where ungoverned AI use is discovered mid-interview (reassurance approach, not enforcement)

Part B: Interview Opening Script
Two to three sentences the interviewer uses to open the conversation. Tone: collaborative, not investigative. Purpose: make the interviewee feel safe disclosing AI use they may be uncertain about.

Part C: Discovery Questions
Grouped into four phases:
1. Current tool landscape (what tools they use day to day - warm-up, non-threatening)
2. Task and workflow questions (questions that surface AI use indirectly through the tasks people describe, not by asking 'do you use AI')
3. Direct AI questions (asked after rapport is established - specific, not accusatory)
4. Data and risk questions (what data has been input into any AI tools, what outputs have been used in work products)

For each question: the question text, the purpose (what you are trying to discover), and a follow-up probe if the answer is vague.

Part D: Post-Interview Actions
What to document, who to notify if ungoverned AI is found, and the next step for the department head.
</instructions>

<output_format>
Present each part with a bold heading. Questions in Part C as numbered items with purpose and probe as sub-items. Write in British English. No em dashes. The tone throughout must be collaborative and non-threatening - this is a discovery exercise, not a compliance investigation.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Asking about tasks rather than tools in Phase 2 is the key technique - people do not always know what counts as AI, but they will describe pasting text into ChatGPT when asked how they draft reports. The 'red flags to listen for' section gives interviewers the pattern recognition they need. The reassurance approach prevents the most common outcome: people saying no to everything because they are afraid of getting in trouble.

## Sample Output Fragment

```
Part C: Discovery Questions

Phase 2: Task and Workflow Questions

4. Walk me through how you typically produce a [department-specific output, e.g. monthly variance report / candidate shortlist / contract review summary]. What tools do you use at each step?
Purpose: Surfaces AI use embedded in workflows without triggering defensiveness about 'AI tools'
Probe: 'When you get to the drafting/summarising step - what does that look like? Do you use anything to speed that up?'

5. When you need to quickly understand a long document or policy, what's your usual approach?
Purpose: Identifies document summarisation AI use, common in legal, compliance, and HR
Probe: 'Have you tried any tools that can pull out the key points automatically?'
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
