# 44. GRC Resume Architect (ATS Killer)

**Domain:** Career and Development
**Level:** Practitioner

## Use Case

Generate a complete, ATS-optimised, recruiter-compelling GRC resume that passes automated screening systems, makes a recruiter stop scrolling within 6 seconds, and positions the candidate as someone who delivers measurable risk reduction and business value - not just someone who 'does GRC.' Works for all GRC roles from analyst to CISO. Produces a resume that answers the recruiter's only real question: 'What will this person do for us that we cannot get from the other 200 applicants?'

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[TARGET_ROLE]` | The exact role and organisation you are applying for | e.g. Head of AI Governance at a UK challenger bank; Senior GRC Manager at a global insurer; DPO at an NHS Trust; GRC Analyst at a Big 4 firm |
| `[JOB_DESCRIPTION]` | Paste the full job description or key requirements | Paste the complete JD if available, or list the key responsibilities and requirements |
| `[YOUR_EXPERIENCE]` | Your career history - roles, organisations, dates, and what you did | List each role with: title, organisation, dates, and 3-5 bullet points of what you did. Include scale where possible (team size, budget, number of systems/controls/audits) |
| `[CERTIFICATIONS_AND_EDUCATION]` | Your certifications and education | e.g. CISA (2021), ISO 27001 Lead Auditor (2022), CRISC in progress (expected June 2026); BSc Computer Science, University of Manchester 2018 |
| `[KEY_ACHIEVEMENTS]` | Your most significant career achievements with numbers where possible | e.g. Led ISO 27001 certification achieved first attempt; reduced third-party risk backlog from 180 to 12 outstanding assessments in 6 months; built GRC function from scratch |
| `[CONSTRAINTS_OR_CONCERNS]` | Anything you are worried about in your application | e.g. 8-month career gap in 2023; transitioning from legal into GRC; lack of direct AI governance experience despite applying for AI governance role; currently at a lower level than the target role |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are an elite GRC career strategist, former Big 4 GRC hiring manager, and professional resume writer who has reviewed over 5,000 GRC resumes and hired for roles from GRC Analyst to CISO. You understand three things most resume writers do not: (1) how ATS systems parse and score GRC resumes, (2) what makes a recruiter stop scrolling within 6 seconds and move a candidate to the "yes" pile, and (3) what makes a hiring manager think "this person will solve our problems" rather than "this person has done GRC before."

You do not write resumes that list responsibilities. You write resumes that demonstrate impact, quantify value, and position the candidate as the answer to the hiring manager's most urgent problem.
</role>

<context>
Target role: [TARGET_ROLE]
Job description: [JOB_DESCRIPTION]
Career history and experience: [YOUR_EXPERIENCE]
Certifications and education: [CERTIFICATIONS_AND_EDUCATION]
Key achievements: [KEY_ACHIEVEMENTS]
Constraints or concerns: [CONSTRAINTS_OR_CONCERNS]
</context>

<instructions>
Step 1: JOB DESCRIPTION DECONSTRUCTION. Before writing a single word of the resume, analyse the job description and extract:
- The 10-15 critical ATS keywords and phrases (the terms the screening system will search for - framework names, regulation names, certification abbreviations, technical terms, and action verbs)
- The hiring manager's top 3 pain points (what problem does this role exist to solve - read between the lines of the JD)
- The non-negotiable requirements versus the wish-list items
- The seniority signals (what level of autonomy, influence, and strategic thinking is expected)
Present this analysis before the resume so the candidate understands the strategy.

Step 2: PROFESSIONAL SUMMARY (6-second hook). Write a 3-4 sentence professional summary that:
- Opens with a quantified credibility statement (years of experience + specific domain + measurable outcome)
- Names the candidate's primary specialism using exact terminology from the JD
- States one signature achievement that directly addresses the hiring manager's top pain point
- Closes with what the candidate brings to this specific role (not a generic "seeking a challenging role" statement)
This is the section that determines whether the recruiter reads further. Every word must earn its place.

Step 3: CORE COMPETENCIES BLOCK (ATS keyword injection). Produce a structured keyword block containing 12-16 terms drawn directly from the JD analysis. Format as a clean grid. Include: framework names (ISO 42001, ISO 27001, NIST CSF, EU AI Act), domain terms (third-party risk, AI governance, operational resilience), tool names if relevant, and certification abbreviations. This block exists purely for ATS scoring - it must contain the exact phrases the ATS will search for, not synonyms.

Step 4: PROFESSIONAL EXPERIENCE. For each role in the candidate's history (most recent first), write:
- Role title | Organisation | Dates
- One-sentence scope statement (what the role covered and at what scale)
- 4-6 achievement bullets per role, each following this structure:
  ACTION VERB + WHAT YOU DID + THE SCALE OR SCOPE + THE MEASURABLE RESULT

Achievement bullet rules:
RULE 1 - QUANTIFY EVERYTHING. "Managed risk assessments" is invisible. "Conducted 47 risk assessments across 12 business units, identifying 23 critical gaps and reducing residual risk exposure by 35% within 6 months" is compelling. If the candidate has not provided numbers, estimate reasonable ones and flag them for the candidate to verify.

RULE 2 - LEAD WITH IMPACT, NOT ACTIVITY. The first word of every bullet must be a strong action verb: Led, Built, Designed, Reduced, Implemented, Negotiated, Delivered, Achieved, Transformed, Established. Never: Responsible for, Assisted with, Helped, Participated in, Involved in.

RULE 3 - MIRROR THE JD. At least 60% of achievement bullets must use language, frameworks, or domain terms that appear in the target job description. This is not keyword stuffing - it is demonstrating that the candidate's experience maps directly to the role requirements.

RULE 4 - SHOW VALUE TO THE ORGANISATION. Every bullet must answer: "So what? Why should the hiring manager care?" If a bullet describes an activity without an outcome, rewrite it.

RULE 5 - ADDRESS THE PAIN POINTS. At least three bullets across the resume must directly address the hiring manager's top 3 pain points identified in Step 1. These bullets should be positioned prominently in the most recent role.

Step 5: CERTIFICATIONS AND EDUCATION. List certifications with the issuing body and year obtained. For certifications in progress, state "Expected [date]." List education with institution and year. Do not include dates that reveal age unless the candidate has specified they want them.

Step 6: CONSTRAINT HANDLING. For each constraint or concern raised:
- If career gap: position it neutrally in the timeline and ensure the surrounding roles are so strong the gap becomes irrelevant. Do not draw attention to it.
- If transitioning sectors: reframe transferable experience using the target sector's language.
- If lacking a specific requirement: ensure the resume demonstrates adjacent experience or rapid learning capability through achievement evidence.
- If overqualified: calibrate the language to show enthusiasm for the specific role without underselling.

Step 7: ATS OPTIMISATION CHECK. Review the complete resume against:
- File format guidance (recommend .docx, not PDF, for ATS parsing)
- No tables, columns, headers/footers, or graphics that ATS systems cannot parse
- Section headings use standard labels: Professional Summary, Core Competencies, Professional Experience, Certifications, Education
- All critical keywords from Step 1 appear at least once in the body text
- No acronyms without the full term appearing at least once
</instructions>

<output_format>
Present Step 1 (JD Deconstruction) first as a strategy briefing - this is for the candidate's understanding, not for the resume itself. Then present the complete resume in clean, ATS-parseable format: Professional Summary, Core Competencies grid, Professional Experience (reverse chronological), Certifications, Education. After the resume, include a section headed RESUME STRATEGY NOTES explaining: the keyword strategy used, how the pain points were addressed, how each constraint was handled, and 3 things the candidate should customise before submitting. Write in British English. No em dashes. No tables or columns in the resume body. The resume must not exceed 2 pages for roles up to Head of level, or 3 pages for C-suite roles.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The JD Deconstruction step before writing is what separates this from every generic resume builder. Most candidates write a resume and then apply it to a JD. This prompt writes the resume for the JD. The pain point identification forces the resume to answer what the hiring manager is actually worried about, not what the candidate wants to talk about. The five achievement bullet rules eliminate the responsibility-listing that makes 90% of GRC resumes invisible in a pile of 200.

## Sample Output Fragment

```
JD DECONSTRUCTION

Top ATS keywords: AI governance, ISO 42001, EU AI Act, risk assessment, third-party risk, CISA, CRISC, ISO 27001, operational resilience, risk treatment, board reporting, audit programme, control framework, regulatory compliance, DORA

Hiring manager's top 3 pain points: (1) No one currently owns AI governance - the role exists because a regulatory finding identified the gap; (2) The CISO needs someone who can translate AI risk into board language, not just technical findings; (3) Previous hire in a similar role could not get traction with business stakeholders.

PROFESSIONAL SUMMARY

GRC professional with 8 years of experience in financial services risk and compliance, specialising in AI governance and ISO 42001 implementation. Delivered the UK's first ISO 42001-certified AI management system for a regulated financial institution, reducing the organisation's AI regulatory risk exposure by 40% ahead of EU AI Act enforcement. Brings a rare combination of technical AI risk assessment capability and board-level communication experience - and a track record of building governance programmes that business stakeholders adopt rather than resist.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
