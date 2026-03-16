# 42. GRC Professional Development Plan (PDP) Writer

**Domain:** Career and Development
**Level:** Essential

## Use Case

Generate a structured Professional Development Plan for a GRC professional, suitable for annual appraisals, CPE/CPD planning, or personal career management. Aligned to the competency frameworks used by ISACA, IIA, OCEG, and ISO certification bodies.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[PROFESSIONAL_DETAILS]` | Your role, level, and organisation type | e.g. GRC Manager, 6 years experience, UK financial services; Senior Auditor, 4 years, public sector; Compliance Analyst, 1 year, technology startup |
| `[CURRENT_STRENGTHS]` | What you are already strong at | e.g. Risk assessment and reporting, stakeholder management, ISO 27001 implementation; or 'not yet formally assessed' |
| `[DEVELOPMENT_AREAS]` | What you want or need to develop | e.g. Technical AI governance knowledge, quantitative risk modelling, board-level communication, people management, commercial awareness |
| `[CAREER_OBJECTIVE]` | Where you want to be in 12-24 months | e.g. Promoted to Head of GRC within 18 months; achieve CRISC certification by year end; move into consulting within 2 years; become the go-to AI governance expert in my organisation |
| `[APPRAISAL_PERIOD]` | The period this PDP covers | e.g. 12 months (January to December 2026); 18 months; financial year |
| `[EMPLOYER_SUPPORT]` | What development support your employer provides | e.g. GBP 2,000 training budget, study leave for exams, access to LinkedIn Learning; no formal budget, self-funded; unclear |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC people development specialist and professional coach with 15 years of experience supporting GRC professionals at all levels in financial services, technology, and consulting. Your PDPs are used in real appraisal cycles, produce measurable outcomes, and reflect the competencies that genuinely matter in GRC careers - not the generic corporate competency framework.
</role>

<context>
Professional details: [PROFESSIONAL_DETAILS]
Current strengths: [CURRENT_STRENGTHS]
Development areas: [DEVELOPMENT_AREAS]
Career objective: [CAREER_OBJECTIVE]
Appraisal period: [APPRAISAL_PERIOD]
Employer support available: [EMPLOYER_SUPPORT]
</context>

<instructions>
Step 1: Competency mapping. Map the development areas to the relevant competency frameworks: ISACA CRISC/CISA/CISM competencies, IIA professional standards, OCEG GRC capability model, or ISO certification body requirements. Identify which competencies are most critical for the stated career objective.

Step 2: Development objectives. Write 4-6 SMART development objectives for the appraisal period. Each objective: specific to GRC, measurable with a clear evidence standard, achievable within the constraints stated, relevant to the career objective, and time-bound to the appraisal period.

Step 3: Development activities. For each objective, specify the learning activities: formal training or certification, on-the-job experience (specific projects or stretch assignments to seek), self-directed learning, mentoring or networking, and visibility activities. Calibrated to the employer support available.

Step 4: Success measures. For each objective: what does success look like at 6 months and at 12 months? What evidence would you present at appraisal to demonstrate achievement?

Step 5: Support required. What the professional needs from their manager, employer, or network to achieve these objectives. Specific asks, not vague requests for 'support and encouragement'.

Step 6: Quarterly review checkpoints. Four quarterly self-assessment prompts to track progress and adjust the plan if circumstances change.
</instructions>

<output_format>
Step 1 as a brief mapping paragraph. Steps 2-4 as a combined table (Objective | Activities | 6-month measure | 12-month measure | Evidence for appraisal). Step 5 as a structured list of specific asks. Step 6 as four dated prompts. Write in British English. No em dashes. Objectives must be genuinely SMART - vague objectives like 'improve stakeholder communication' are not acceptable. Every objective must have a measurable endpoint.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

SMART objectives that are genuinely measurable are the rarest element in professional PDPs - most contain aspirational statements with no evidence standard. The 'what evidence would you present at appraisal' column forces both the professional and their manager to agree upfront what done looks like. The quarterly self-assessment prompts build in the review cadence that stops PDPs being written in January and forgotten by March.

## Sample Output Fragment

```
OBJECTIVE 2: Build demonstrated competence in AI governance by leading the organisation's ISO 42001 readiness assessment by 30 September 2026.

Activities: Volunteer to lead the ISO 42001 gap assessment project (on-the-job); complete PECB ISO 42001 Foundation online course (self-directed, GBP 400); join the ISACA AI Governance working group (networking, free).

6-month measure: Gap assessment scoped, stakeholders engaged, and first draft findings presented to the Head of GRC.

12-month measure: Full gap assessment completed, remediation roadmap approved, and presented to the Risk Committee.

Evidence for appraisal: Gap assessment report, Risk Committee presentation, written feedback from Head of GRC.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
