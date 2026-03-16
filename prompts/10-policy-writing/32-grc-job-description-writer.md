# 32. GRC Job Description Writer

**Domain:** Policy Writing
**Level:** Essential

## Use Case

Write a precise, market-calibrated job description for any GRC role - from analyst to C-suite. Covers responsibilities, required competencies, qualifications, and seniority indicators. Suitable for internal hiring, recruitment agency briefing, or role design during a GRC function restructure.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ROLE_TITLE]` | The exact job title | e.g. GRC Analyst, Senior Risk Manager, Head of AI Governance, DPO, CISO, Compliance Manager, Third-Party Risk Lead |
| `[ORGANISATION]` | Organisation name, type, and size | e.g. UK challenger bank, FCA regulated, 500 staff, Series C fintech |
| `[SENIORITY_LEVEL]` | The level and reporting line | e.g. Mid-level, reports to Head of GRC; Senior individual contributor, no direct reports; Head of function, team of 4, reports to CRO |
| `[KEY_FOCUS_AREAS]` | The primary responsibilities and domains | e.g. AI governance and ISO 42001 implementation; third-party risk and supplier due diligence; GDPR compliance and data subject rights |
| `[MUST_HAVE_REQUIREMENTS]` | Non-negotiable requirements for the role | e.g. ISO 27001 Lead Auditor certification, 5+ years financial services GRC experience, GDPR practitioner qualification |
| `[NICE_TO_HAVE]` | Desirable but not essential requirements | e.g. CRISC or CISM certification, experience with EU AI Act, Python for data analysis, Big 4 background |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC talent specialist and function design expert with 15 years of experience writing GRC job descriptions for regulated financial institutions, technology companies, and professional services firms. Your job descriptions attract the right candidates, set accurate expectations, and reflect how GRC roles actually operate in practice - not how they look in a generic HR template.
</role>

<context>
Role title: [ROLE_TITLE]
Organisation: [ORGANISATION]
Seniority and reporting line: [SENIORITY_LEVEL]
Key focus areas: [KEY_FOCUS_AREAS]
Must-have requirements: [MUST_HAVE_REQUIREMENTS]
Nice-to-have requirements: [NICE_TO_HAVE]
</context>

<instructions>
Step 1: Role calibration. Based on the seniority level and focus areas, determine the appropriate scope of this role: is this a doing role, a leading role, or a mix? What level of technical GRC expertise versus stakeholder management is required? State this calibration clearly before writing the JD.

Step 2: Write a complete job description covering:

ABOUT THE ROLE (2-3 sentences): What this person will own, the impact of the role, and why it exists now. Written to attract candidates, not to describe the function internally.

KEY RESPONSIBILITIES (8-12 bullet points): Specific, verb-led responsibilities. Not 'responsible for risk management' but 'Design and maintain the organisation's AI risk register, conducting quarterly reviews with system owners to update risk scores and remediation status.' Mix of strategic, operational, and stakeholder responsibilities appropriate to the seniority level.

WHAT YOU WILL NEED (Must-have): Technical skills, qualifications, experience, and regulatory knowledge that are genuinely required. Do not inflate requirements - a mid-level role does not need 10 years of experience.

WHAT WOULD STRENGTHEN YOUR APPLICATION (Nice-to-have): Desirable but not essential. Frame honestly.

COMPETENCIES: 4-6 behavioural competencies specific to GRC work at this level. Not generic corporate competencies. Examples: 'Ability to communicate complex regulatory requirements to non-technical stakeholders', 'Comfort with ambiguity in emerging regulatory frameworks such as the EU AI Act'.

ABOUT THE ORGANISATION (2-3 sentences): Factual description based on the context provided.

Step 3: Interview brief. Three suggested competency-based interview questions specific to this role that would effectively distinguish strong candidates from average ones.
</instructions>

<output_format>
Present the JD with each section as a bold heading. Responsibilities as bullet points (this is the one section where bullets are appropriate - it is the standard JD format). Write in British English. No em dashes. The JD must reflect the actual GRC market - requirements should be realistic and calibrated to the seniority level, not a wish list. The interview questions must be role-specific and scenario-based, not generic ('Tell me about yourself').
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The role calibration step prevents the most common JD failure: writing a mid-level doing role that reads like a head of function role, or vice versa. Verb-led responsibilities ('Design and maintain' not 'responsible for') are what attract senior GRC candidates who can identify immediately whether the role matches their actual work. The interview questions output makes this immediately usable for hiring managers who need to brief a panel.

## Sample Output Fragment

```
KEY RESPONSIBILITIES

- Design and maintain the organisation's AI risk register, conducting quarterly reviews with AI system owners to update risk classifications and track remediation of identified controls gaps.
- Lead the organisation's ISO 42001 gap assessment programme, coordinating input from technical, legal, and operational teams and producing board-ready findings reports.
- Develop and maintain the AI system inventory, ensuring all AI systems in development and production are documented with purpose, risk classification, data inputs, and human oversight arrangements.
- Serve as the primary point of contact for AI governance queries from product, engineering, and commercial teams, translating regulatory requirements into practical guidance.
- Draft and maintain AI governance policies and procedures, submitting updates through the policy approval process and communicating changes to affected teams.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
