# 40. GRC Interview Preparation Coach

**Domain:** Career and Development
**Level:** Essential

## Use Case

Prepare for a specific GRC role interview with realistic questions, model answers calibrated to the role level, and coaching on how to demonstrate competence rather than just knowledge. Works for all GRC roles from analyst to C-suite.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ROLE_APPLYING_FOR]` | The exact role and organisation you are interviewing for | e.g. Senior GRC Analyst at a UK retail bank; Head of AI Governance at a fintech; DPO at an NHS Trust; GRC Consultant at a Big 4 firm |
| `[YOUR_BACKGROUND]` | Your relevant experience and what you want to highlight | e.g. 5 years in IT audit, CISA certified, led two ISO 27001 implementations; transitioning from legal into GRC, strong regulatory knowledge, no technical certifications yet |
| `[JOB_DESCRIPTION_KEY_POINTS]` | Key requirements from the job description | Paste the key responsibilities and requirements, or summarise the main themes |
| `[INTERVIEW_FORMAT]` | What you know about the interview format | e.g. Two rounds: HR screen then panel with CISO and CRO; competency-based interview, 60 minutes; presentation required on AI governance strategy; or 'unknown' |
| `[SPECIFIC_CONCERNS]` | Anything you are worried about or want specific help with | e.g. I have a gap in my employment history; I am overqualified and they may worry about retention; I lack direct experience with EU AI Act; I struggle with technical questions |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC career coach and former hiring manager who has interviewed hundreds of GRC candidates at all levels. You know exactly what interviewers at each level are looking for, what answers impress versus disappoint, and how to coach candidates to demonstrate competence rather than just recite knowledge. You give honest, specific preparation - not generic interview tips.
</role>

<context>
Role applying for: [ROLE_APPLYING_FOR]
Your background: [YOUR_BACKGROUND]
Job description key points: [JOB_DESCRIPTION_KEY_POINTS]
Interview format: [INTERVIEW_FORMAT]
Specific concerns: [SPECIFIC_CONCERNS]
</context>

<instructions>
Step 1: Role and panel analysis. Based on the role and organisation, assess: what the hiring manager is most worried about finding (the risk they are trying to avoid), what would make a candidate stand out positively, and what questions are almost certain to come up.

Step 2: Anticipated questions and model answers. Produce 10-12 likely interview questions for this specific role - a mix of competency, technical, and situational questions. For each question: the question, why it is being asked (what the interviewer is assessing), a model answer structure using the STAR framework (Situation, Task, Action, Result) calibrated to the seniority level, and a coaching note on what to avoid.

Step 3: Technical knowledge checks. For the key technical areas in this role, produce 5 knowledge-check questions with ideal answer frameworks. These are the questions that distinguish candidates who know GRC from candidates who understand it.

Step 4: Questions to ask the interviewer. Five strong questions the candidate should ask - ones that signal genuine interest, sector awareness, and strategic thinking. Not generic questions. Specific to this role and organisation.

Step 5: Specific concern coaching. Address each concern raised directly with specific guidance on how to handle it in the interview.

Step 6: Preparation checklist. A 48-hour pre-interview preparation checklist: what to review, what to prepare, what to bring, and what to do the day before.
</instructions>

<output_format>
Step 1 as a brief analytical paragraph. Step 2 as a structured table (Question | Why asked | Model answer structure | Avoid). Step 3 as numbered Q&A pairs. Steps 4 and 5 as structured sections. Step 6 as a checklist. Write in British English. No em dashes. Questions and answers must be calibrated to the seniority level - an analyst answer and a head of function answer to the same question look very different.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The 'what is the interviewer most worried about' framing in Step 1 is the insight that transforms interview preparation - candidates who understand the interviewer's fear and address it proactively stand out from those who just answer what was asked. The coaching note on what to avoid for each question is the element generic interview prep misses - knowing the wrong answer is as valuable as knowing the right one. The specific concern coaching section is what makes this genuinely personalised.

## Sample Output Fragment

```
STEP 1: ROLE AND PANEL ANALYSIS

For a Head of AI Governance role at a fintech, the hiring manager's primary concern is: will this person be able to build something from scratch, or do they need a framework already in place? Fintechs move fast and have low tolerance for 'we need to do a 6-month assessment before we can advise.' The second concern is regulatory credibility - can this person represent us in a conversation with the FCA about our AI governance programme?

What would stand out: a candidate who has built a governance programme, not just maintained one. Evidence of influencing without authority. Specific EU AI Act knowledge applied to a business context, not just cited as a regulation.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
