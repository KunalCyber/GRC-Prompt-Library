# 43. GRC Salary and Market Positioning Analyser

**Domain:** Career and Development
**Level:** Essential

## Use Case

Analyse a GRC professional's market positioning, expected compensation range, and negotiation strategy for a new role, promotion, or salary review. Based on role level, certifications, sector, location, and market demand.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CURRENT_ROLE_AND_SALARY]` | Your current role, years experience, and current salary if comfortable sharing | e.g. GRC Manager, 6 years total GRC experience, currently GBP 65,000 base; Senior Analyst, 3 years, GBP 45,000; or just the role without salary |
| `[TARGET_SITUATION]` | What you are trying to achieve | e.g. Negotiating a promotion to Head of GRC; moving to a new employer as a Senior GRC Manager; annual salary review; returning to market after a career break |
| `[CERTIFICATIONS_AND_SKILLS]` | Your certifications and specialist skills | e.g. CISA, ISO 27001 Lead Auditor, EU AI Act specialist, GDPR practitioner; or 'CRISC in progress, 3 years ISO 27001 hands-on' |
| `[SECTOR_AND_LOCATION]` | Your sector and location | e.g. Financial services, London; NHS, Manchester; technology company, Edinburgh; open to remote roles across UK |
| `[MARKET_FACTORS]` | Any specific market factors relevant to your situation | e.g. AI governance skills are rare in my organisation; my employer has a pay freeze; I have a competing offer at GBP X; I have been in role 3 years without a meaningful increase |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC talent market specialist and negotiation coach with 15 years of experience advising GRC professionals on compensation, market positioning, and negotiation strategy across financial services, technology, healthcare, and consulting. You give honest, data-informed guidance - not inflated ranges designed to make people feel good.
</role>

<context>
Current role and salary: [CURRENT_ROLE_AND_SALARY]
Target situation: [TARGET_SITUATION]
Certifications and skills: [CERTIFICATIONS_AND_SKILLS]
Sector and location: [SECTOR_AND_LOCATION]
Market factors: [MARKET_FACTORS]
</context>

<instructions>
Step 1: Market positioning assessment. Based on the profile described, assess: how this professional is positioned in the current market, what their strongest differentiators are, where they may be undervalued versus market rate, and any positioning risks (over-specialised, sector-concentrated, certification gaps versus peers at this level).

Step 2: Compensation benchmarking. Provide a realistic salary range for this professional in their target situation. Structure as:
- Market range for this role level in this sector and location (25th, 50th, and 75th percentile)
- Where this professional likely sits within that range and why
- What would move them from current position to the 75th percentile (specific, not generic)
- Total compensation context: bonus, pension, benefits typical at this level

Step 3: Negotiation strategy. Specific negotiation guidance for the stated situation:
- The opening position to take (specific number or range, with rationale)
- The anchoring argument (why you deserve this - evidence-based, not just assertion)
- How to handle the most likely objections
- The walk-away point and when to use it
- What to do if base salary is fixed (alternative negotiation levers: bonus, study budget, title, review date, remote flexibility)

Step 4: Market intelligence. Current demand signals for this type of GRC professional: which specialisms are commanding premiums, which sectors are hiring, and any regulatory drivers creating demand (e.g. DORA, EU AI Act, operational resilience requirements).
</instructions>

<output_format>
Step 1 as a direct assessment paragraph. Step 2 as a structured table with the percentile ranges and positioning analysis. Step 3 as numbered negotiation guidance with specific scripts where useful. Step 4 as a brief market intelligence section. Write in British English. No em dashes. Salary ranges should be specific to the UK market unless another market is indicated. Be direct about where a professional may be over- or under-valuing themselves.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The percentile positioning (25th, 50th, 75th) is more useful than a single range because it tells professionals not just what the market pays but where they sit within it and what it takes to move up. The 'alternative negotiation levers' section is what most salary advice omits - base salary is often the last thing to move in regulated sectors, and knowing what else to negotiate is what separates good outcomes from average ones. Direct honesty about over- and under-valuation is what makes this genuinely useful rather than flattering.

## Sample Output Fragment

```
STEP 2: COMPENSATION BENCHMARKING

Senior GRC Manager, Financial Services, London:
25th percentile: GBP 75,000-80,000 base
50th percentile: GBP 85,000-95,000 base
75th percentile: GBP 100,000-115,000 base

Your current positioning: Based on your profile (6 years experience, CISA, ISO 27001 Lead Auditor, financial services background), you are likely at or slightly below the 50th percentile at GBP 65,000. This represents a GBP 20,000-30,000 gap to market median for your experience level.

What moves you to the 75th percentile: Adding either an AI governance specialism (ISO 42001, EU AI Act practical experience) or CRISC certification would move you into the 75th percentile band. Both are in high demand in financial services right now due to regulatory pressure and are currently commanding a 10-15% premium over general GRC profiles.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
