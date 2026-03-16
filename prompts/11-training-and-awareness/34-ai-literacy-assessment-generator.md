# 34. AI Literacy Assessment Generator

**Domain:** Training and Awareness
**Level:** Essential

## Use Case

Create role-appropriate quizzes, self-assessments, and evaluation rubrics to measure AI literacy across the workforce. Directly supports EU AI Act Article 4 (AI literacy obligation) and ISO 42001 Annex A.4.3. Produces assessments calibrated to the role's actual AI exposure.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[TARGET_ROLE]` | The role or audience being assessed | e.g. All staff, Data scientists and ML engineers, Customer service agents using AI tools, Senior management and board, HR team using AI screening tools |
| `[ASSESSMENT_FORMAT]` | The format required | e.g. 10-question multiple choice quiz, Self-assessment checklist (yes/no), Written scenario-based evaluation, Manager observation rubric |
| `[AI_TOOLS_IN_USE]` | The AI tools this role actually uses or will use | e.g. Microsoft Copilot for document drafting, AI-powered CRM recommendations, ChatGPT for research, custom credit model outputs |
| `[LITERACY_LEVEL_TARGET]` | The minimum literacy level being assessed for | e.g. Basic awareness (can identify AI outputs and know when to flag concerns), Operational (can use AI tools correctly and identify errors), Advanced (can evaluate AI system risks and design controls) |
| `[REGULATORY_CONTEXT]` | Regulatory or policy requirements this assessment supports | e.g. EU AI Act Article 4 literacy obligation, ISO 42001 A.4.3, internal AI policy Section 9, FCA Consumer Duty |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior learning and development specialist and AI governance expert. You design assessments that measure real capability, not just recall. Your assessments are used to satisfy regulatory literacy requirements and to identify genuine skill gaps that training programmes then address.
</role>

<context>
Target role: [TARGET_ROLE]
Assessment format: [ASSESSMENT_FORMAT]
AI tools in use: [AI_TOOLS_IN_USE]
Literacy level target: [LITERACY_LEVEL_TARGET]
Regulatory context: [REGULATORY_CONTEXT]
</context>

<instructions>
Produce a complete AI literacy assessment for the stated role and format.

Part A: Assessment Design Notes
- What the assessment is designed to measure (linked to the regulatory requirement)
- How the results should be interpreted and used
- Pass threshold recommendation and rationale

Part B: The Assessment
Produce the full assessment in the stated format. Apply these design principles:
1. Questions must test application of knowledge, not just recall. 'Which of these is an example of AI bias?' tests application. 'What is AI bias?' tests recall. Prefer the former.
2. Wrong answers must be plausible. An obviously wrong answer teaches nothing.
3. Scenario-based questions must use realistic situations specific to the stated role and tools.
4. At least 30% of questions should address what to do when something goes wrong (escalation, flagging errors, override procedures) - not just what AI is.
5. Include at least one question specifically about the individual's rights and responsibilities under the applicable regulatory framework.

Part C: Answer Key and Rationale
For every question, provide the correct answer and a one-sentence explanation of why it is correct - for use by assessors or for learner feedback.

Part D: Assessment Record Template
A simple record template capturing: employee name, role, date, score, pass/fail, assessor, and next review date. For regulatory compliance evidence purposes.
</instructions>

<output_format>
Present each Part with a bold heading. For multiple choice questions, use A/B/C/D options. Write in British English. No em dashes. Questions must reflect the actual AI tools and context described - not generic AI awareness questions.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The 30% rule on escalation and error-flagging questions is the design principle that makes this assessment compliance-useful rather than just awareness-checking. EU AI Act Article 4 requires that staff can 'critically assess' AI outputs - testing recall of definitions does not satisfy that. The answer key with rationale makes the assessment self-improving: learners who get questions wrong understand why.

## Sample Output Fragment

```
Question 4 (Scenario-based - Application)
You are reviewing a customer complaint and the AI-assisted CRM has flagged it as 'low priority' with a confidence score of 67%. The customer is describing what sounds like a potential fraud situation. What is the correct action?
A) Accept the AI classification and route it to the standard low-priority queue
B) Override the AI classification, escalate to the fraud team, and log that you overrode the system and why
C) Wait to see if the AI reclassifies it when more information is added
D) Refer to your manager before taking any action

Correct answer: B
Rationale: A 67% confidence score indicates meaningful uncertainty. Human oversight must be applied when AI outputs conflict with direct evidence of risk. Logging the override is required for audit purposes under [REGULATORY_CONTEXT].
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
