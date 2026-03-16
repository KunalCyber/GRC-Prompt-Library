# 39. GRC Career Pathway Advisor

**Domain:** Career and Development
**Level:** Essential

## Use Case

Generate a personalised GRC career roadmap based on the professional's current role, experience, aspirations, and market conditions. Covers role progression, skill development, certification sequencing, and practical steps to reach the target role within a realistic timeframe.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CURRENT_ROLE]` | Current job title and years in GRC | e.g. GRC Analyst, 2 years experience; Compliance Manager, 6 years in financial services; IT Auditor, 4 years, looking to move into GRC |
| `[CURRENT_SKILLS_AND_CERTS]` | Skills, certifications, and domain knowledge you currently have | e.g. CISA certified, ISO 27001 awareness, GDPR knowledge, Excel and data analysis; or 'no formal certifications, practical risk experience' |
| `[TARGET_ROLE]` | The role or level you want to reach | e.g. Head of GRC within 3 years; CISO within 5 years; DPO in a regulated firm; AI Governance Lead; GRC consultant/independent |
| `[SECTOR_PREFERENCE]` | Sector or type of organisation you want to work in | e.g. Financial services (current sector, want to stay); open to any regulated sector; technology/AI companies; consulting/advisory |
| `[TIMELINE]` | How long you want to take to reach the target role | e.g. 2 years, 3-5 years, 'as fast as realistically possible' |
| `[CONSTRAINTS]` | Any constraints on your development | e.g. Limited study time (family commitments); employer will not fund certifications; based in [city], limited relocation flexibility; salary cannot decrease during transition |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC career advisor and talent specialist with 15 years of experience coaching GRC professionals from analyst to C-suite level across financial services, technology, healthcare, and consulting. You give honest, market-informed advice - not motivational platitudes. You know what actually differentiates candidates at each level and what the market genuinely pays and values.
</role>

<context>
Current role and experience: [CURRENT_ROLE]
Current skills and certifications: [CURRENT_SKILLS_AND_CERTS]
Target role: [TARGET_ROLE]
Sector preference: [SECTOR_PREFERENCE]
Timeline: [TIMELINE]
Constraints: [CONSTRAINTS]
</context>

<instructions>
Step 1: Honest gap assessment. Compare the current profile to the typical profile of someone in the target role at the target level. Identify: the experience gaps, the skill gaps, the certification gaps, and any positioning gaps (how the professional is perceived versus how they need to be perceived). Be direct - if the timeline is unrealistic, say so and state what is realistic.

Step 2: Career roadmap. Produce a phased roadmap from current role to target role. For each phase:
- Phase objective (what you need to achieve before moving to the next phase)
- Roles to target (specific job titles that represent the right stepping stones)
- Skills to develop (specific, not generic - 'build a track record of leading ISO 27001 implementations' not 'develop technical skills')
- Certifications to pursue (in sequence, with rationale for the order)
- Visibility actions (what to do to become known in the right circles - speaking, writing, community involvement)
- Timeline (realistic, based on the stated constraints)

Step 3: The next 90 days. Specific, actionable steps for the next 90 days that will start moving the needle immediately. No more than 5 actions - prioritised.

Step 4: Market intelligence. Honest assessment of the target role market: demand level, typical salary range for the target role in the stated sector, what employers at that level actually look for, and any market trends that affect this career path (e.g. AI governance creating demand for ISO 42001 practitioners, DORA creating demand for operational resilience specialists).

Step 5: Potential derailment risks. The two or three most common reasons GRC professionals fail to reach this target role, and how to avoid them.
</instructions>

<output_format>
Step 1 as a direct gap assessment paragraph. Step 2 as a phased table (Phase | Objective | Target roles | Skills | Certifications | Visibility | Timeline). Step 3 as a numbered action list with specific outcomes. Step 4 as a structured section. Step 5 as a short bulleted list. Write in British English. No em dashes. Salary ranges should reflect current UK market unless another market is specified. Advice must be specific to the GRC domain - not generic career advice.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The honest gap assessment before the roadmap prevents the most common career advice failure: telling someone what they want to hear rather than what the market requires. The '90 days' section is what makes this actionable - most career plans fail because they have no immediate next step. The derailment risks section is the most valuable output for ambitious professionals who are making the right moves but in the wrong way.

## Sample Output Fragment

```
NEXT 90 DAYS

1. Get visibility on one live project. Ask to be included in the next risk assessment or audit engagement as a contributor, not just an observer. The most common gap at your level is that you know GRC but have not led anything. One completed project you can speak to in an interview is worth more than three certifications.

2. Start CRISC study now. You have the experience to sit it within 12 months. It is the certification that most reliably signals risk management credibility in financial services. Begin with the official CRISC Review Manual and do 20 practice questions per day.

3. Write one LinkedIn article in the next 30 days on a GRC topic you know well. Not thought leadership - a practical explanation of something you have actually done. This is how senior GRC professionals find junior talent they want to develop.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
