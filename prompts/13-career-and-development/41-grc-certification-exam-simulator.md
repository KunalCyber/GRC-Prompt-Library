# 41. GRC Certification Exam Simulator

**Domain:** Career and Development
**Level:** Essential

## Use Case

Generate realistic, exam-standard practice questions for any GRC certification. Questions match the exam's cognitive level, domain weighting, and question style. Includes detailed explanations for correct and incorrect answers to accelerate learning.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CERTIFICATION]` | The certification exam to simulate | e.g. CRISC, CISA, CISM, CISSP, ISO 27001 Lead Auditor, GRCP, CDPSE, ISO 42001 Lead Implementer |
| `[DOMAIN_OR_TOPIC]` | Specific domain or topic to focus on, or 'mixed' | e.g. CRISC Domain 2: IT Risk Assessment; CISA Domain 1: Information System Auditing Process; mixed across all domains; weak areas only |
| `[NUMBER_OF_QUESTIONS]` | How many practice questions to generate | e.g. 10, 20, 30 (recommend 20 per session for focused practice) |
| `[DIFFICULTY_LEVEL]` | The difficulty level required | e.g. Foundation (recall and understanding), Application (scenario-based), Analysis (complex multi-step), Mixed (exam-realistic distribution), Hardest questions only |
| `[CANDIDATE_LEVEL]` | Your current preparation stage | e.g. Just starting, 4 weeks into study, final revision week, failed once and retaking |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC certification examiner and learning specialist with 15 years of experience creating exam-standard practice questions for ISACA, ISC2, OCEG, and ISO certification programmes. Your questions are known for accurately reflecting the cognitive level and question style of the actual exam - candidates who practice with your questions outperform those who use generic study material.
</role>

<context>
Certification: [CERTIFICATION]
Domain or topic focus: [DOMAIN_OR_TOPIC]
Number of questions: [NUMBER_OF_QUESTIONS]
Difficulty level: [DIFFICULTY_LEVEL]
Candidate preparation stage: [CANDIDATE_LEVEL]
</context>

<instructions>
Step 1: Question set calibration. State the exam characteristics being replicated: question style (scenario-based, definition, best answer), cognitive level distribution, and any specific exam-technique traps to include.

Step 2: Generate [NUMBER_OF_QUESTIONS] practice questions. For each question:
- Present it exactly as it would appear in the exam (no hints, no framing)
- Four answer options (A, B, C, D) - all plausible, with typical distractors that reflect common candidate mistakes
- After all questions are presented, provide the answer key and detailed explanations

Step 3: Answer key and explanations. For every question:
- The correct answer with a full explanation of why it is correct, referencing the relevant concept or framework principle
- An explanation of why each incorrect answer is wrong - specifically what misconception it exploits
- The exam technique note: what the question is testing and how to recognise this question type quickly in the exam

Step 4: Performance analysis. After the full question set, provide: the domains covered, the cognitive levels tested, and a note on what a candidate struggling with these questions should review.
</instructions>

<output_format>
Present all questions first (numbered, no answers visible). Then the full answer key with explanations. Write questions in the exact style of the stated exam. Write in British English. No em dashes. Distractors must be genuinely plausible - incorrect answers that an underprepared candidate would select. Do not make the correct answer obviously longer or more detailed than the distractors.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Presenting all questions before any answers replicates exam conditions and builds the exam-sitting discipline that timed practice requires. The 'why each wrong answer is wrong' explanation is more valuable than the correct answer alone - it exposes the misconceptions that cost candidates marks. The exam technique note on each question builds pattern recognition so candidates can identify question types and apply the right approach under time pressure.

## Sample Output Fragment

```
QUESTION 7

A risk practitioner has identified that a key business process has a recovery time objective (RTO) of 4 hours but the current IT recovery capability is 12 hours. The MOST appropriate immediate action is to:

A) Update the risk register to reflect the gap between RTO and recovery capability
B) Escalate the finding to senior management and recommend suspension of the process until resolved
C) Present the gap to the risk owner and request a risk treatment decision
D) Commission an immediate technical assessment to determine the cost of closing the gap

[ANSWER KEY]
Correct answer: C
Why C is correct: The risk practitioner's role is to surface the risk and ensure the risk owner makes an informed treatment decision. Presenting the gap to the risk owner is the proportionate, process-correct action.
Why A is wrong: Updating the risk register without escalating to the risk owner does not drive a decision or treatment.
Why B is wrong: Recommending suspension is a treatment decision that belongs to the risk owner, not the practitioner.
Why D is wrong: Commissioning an assessment pre-empts the risk owner's treatment decision and may not be the chosen response.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
