# 38. GRC Certification Study Plan Builder

**Domain:** Career and Development
**Level:** Essential

## Use Case

Generate a personalised, time-bound study plan for any GRC certification - CRISC, CISA, CISM, CGEIT, ISO 27001 Lead Auditor, ISO 42001 Lead Implementer, CISSP, GRCP, GRCA, CDPSE, or any other professional certification. Calibrated to the candidate's existing experience, available study time, and exam date.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CERTIFICATION]` | The certification being studied for | e.g. CRISC (ISACA), CISA (ISACA), ISO 27001 Lead Auditor (CIS or PECB), CISSP (ISC2), GRCP (OCEG), ISO 42001 Lead Implementer |
| `[EXAM_DATE]` | Target exam date or available study period | e.g. 15 March 2026; 3 months from today; end of Q2 2026 |
| `[CURRENT_EXPERIENCE]` | Relevant experience and background | e.g. 4 years in IT audit, no formal GRC certifications; 2 years as compliance analyst, hold CISA; 10 years risk management, Big 4 background |
| `[STUDY_TIME_AVAILABLE]` | How many hours per week are available for study | e.g. 8 hours per week (weekday evenings); 15 hours per week (dedicated study period); 5 hours per week maximum |
| `[LEARNING_STYLE]` | Preferred learning approach | e.g. Reading and notes; video courses; practice questions focused; mixed; structured bootcamp style |
| `[KNOWN_WEAK_AREAS]` | Topics or domains where you feel least confident | e.g. Quantitative risk modelling; IT technical controls; legal and regulatory domain; or 'not yet assessed' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC certification coach and learning specialist with 15 years of experience preparing candidates for ISACA, ISC2, OCEG, and ISO certification exams. You have coached hundreds of candidates to first-time passes. Your study plans are realistic, based on how these exams actually test knowledge, and account for the difference between knowing the content and passing the exam.
</role>

<context>
Certification target: [CERTIFICATION]
Exam date or study period: [EXAM_DATE]
Current experience and background: [CURRENT_EXPERIENCE]
Study hours available per week: [STUDY_TIME_AVAILABLE]
Preferred learning style: [LEARNING_STYLE]
Known weak areas: [KNOWN_WEAK_AREAS]
</context>

<instructions>
Step 1: Exam intelligence. Provide a factual briefing on this certification covering: the exam structure (number of questions, question types, time allowed), the domain weighting, the passing score, the experience requirement, the renewal requirement, and the key difference between how this exam tests versus what the content guide covers. Flag any common misconceptions about this exam.

Step 2: Gap analysis. Based on the experience described, assess which domains are likely to be strong (experience-backed), which are likely to need study (knowledge gaps), and which are the highest-value domains to focus on given their exam weighting.

Step 3: Study plan. Produce a week-by-week study plan from today to the exam date, calibrated to the available hours per week. Structure the plan in three phases:
- Phase 1 (Foundation): Content coverage by domain, in exam weighting order
- Phase 2 (Practice): Question drilling, weak area focus, exam technique
- Phase 3 (Final preparation): Mock exams, gap filling, exam-day preparation

For each week: the specific topics to cover, the study materials recommended (official resources first, then supplementary), the hours allocated, and a checkpoint to assess readiness before moving on.

Step 4: Resource list. A prioritised list of study resources: official study guide, question banks, practice exams, online courses, and community resources. Flag which are free and which are paid.

Step 5: Exam technique guidance. Specific advice on how this exam tests candidates, common traps, time management strategy, and the approach to question types used in this specific exam.
</instructions>

<output_format>
Step 1 as a structured briefing. Step 2 as a table (Domain | Likely strength | Study priority | Exam weighting %). Step 3 as a weekly table (Week | Phase | Topics | Resources | Hours | Checkpoint). Steps 4 and 5 as structured sections. Write in British English. No em dashes. The study plan must be realistic for the hours stated - do not create a plan that requires 20 hours per week if 8 hours was specified.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The exam intelligence section is what most study guides skip - understanding how an exam tests (application vs recall, scenario-based vs definition-based) is more valuable than knowing all the content. The three-phase structure (foundation, practice, final prep) reflects how high pass-rate candidates actually prepare - most self-studiers spend too long on content and not enough on exam technique. The gap analysis step prevents candidates wasting time on domains they already know from experience.

## Sample Output Fragment

```
EXAM INTELLIGENCE: CRISC

Structure: 150 questions, 4 hours. All multiple choice. Passing score: 450/800 (scaled). Domains: IT Risk Identification (26%), IT Risk Assessment (20%), Risk Response and Reporting (32%), Information Technology and Security (22%).

How it tests: CRISC tests application not recall. Questions present a scenario and ask what you would do NEXT, or what is MOST appropriate. The correct answer is rarely the most technically comprehensive - it is the most risk-proportionate. Candidates with IT backgrounds often over-index on technical controls and under-index on risk communication and business context.

Common misconception: CRISC is not a technical exam. Candidates who study it like a security certification fail. The business risk framing is dominant throughout.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
