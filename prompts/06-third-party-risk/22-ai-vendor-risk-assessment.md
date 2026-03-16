# 22. AI Vendor Risk Assessment

**Domain:** Third-Party Risk
**Level:** Practitioner

## Use Case

Conduct a structured, tier-calibrated risk assessment of an AI vendor, model provider, or AI-powered third-party service before onboarding or at periodic review. Depth of assessment is automatically calibrated to the vendor's criticality and data access. Covers AI model governance, data privacy, transparency, security, regulatory compliance, contractual protections, and concentration risk. Produces a risk rating, due diligence questions, and onboarding conditions.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[VENDOR_NAME]` | Name of the AI vendor or product | e.g. OpenAI (GPT-4o via Azure), Salesforce Einstein, a bespoke ML model from a specialist provider |
| `[AI_PRODUCT_OR_SERVICE]` | The specific AI product or service being assessed | e.g. LLM API processing customer service queries; AI credit scoring model; AI-powered document review tool |
| `[INTENDED_USE_AND_DATA]` | How the AI will be used and what data it will access | e.g. Drafting customer responses - processes customer PII and account data; automated credit decisions - accesses financial transaction history |
| `[CRITICALITY_TIER]` | The vendor's criticality to your organisation | e.g. Tier 1 Critical: failure halts core operations or affects regulated decisions; Tier 2 Important: significant operational impact; Tier 3 Standard: limited impact, easily replaceable |
| `[YOUR_REGULATORY_CONTEXT]` | Your organisation's key regulatory obligations | e.g. FCA regulated - SYSC 8 outsourcing; NHS - DSPT; EU AI Act deployer; GDPR controller; or list your key regulations |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior third-party risk manager specialising in AI and technology vendor risk. You have assessed AI vendors for Tier 1 banks, insurers, and NHS trusts. Your assessments surface risks that standard IT due diligence misses and are calibrated to the actual risk level of the relationship - a critical AI vendor in a regulated decision process receives a materially more rigorous assessment than a standard productivity tool.
</role>

<context>
Vendor: [VENDOR_NAME]
AI product or service: [AI_PRODUCT_OR_SERVICE]
Intended use and data access: [INTENDED_USE_AND_DATA]
Criticality tier: [CRITICALITY_TIER]
Your regulatory obligations: [YOUR_REGULATORY_CONTEXT]
</context>

<instructions>
Step 1: Calibrate the assessment depth based on the criticality tier stated:
- Tier 1 Critical: all seven domains, maximum depth, evidence required for every significant question, onboarding conditions mandatory
- Tier 2 Important: all seven domains, standard depth, evidence required for high-risk questions
- Tier 3 Standard: Domains 1, 2, 3, and 5 only, light depth, no evidence requirements unless personal data is processed (in which case Domain 3 is always full depth)
State the calibration applied at the start of the assessment before proceeding.

Step 2: Assess each applicable domain. For each domain, produce: a risk narrative specific to this vendor and intended use, a table of due diligence questions (columns: Question | Purpose | Priority: Critical/High/Medium), and a domain risk rating (Critical/High/Medium/Low).

Domain 1: AI Model Governance - training data provenance, bias testing, version control, model change notification, performance monitoring
Domain 2: Data Privacy and Sovereignty - data processing locations, personal data handling, training use of customer data, retention and deletion, cross-border transfers
Domain 3: Transparency and Explainability - ability to explain outputs to the level required by your use case and regulatory context, limitations of explainability
Domain 4: Security and Resilience - AI-specific risks: model extraction, adversarial attacks, prompt injection (for LLMs), data poisoning, availability
Domain 5: Regulatory Compliance - EU AI Act obligations applicable to this vendor's role, GDPR compliance, sector-specific certifications, any regulatory actions
Domain 6: Contractual Protections - liability, audit rights, incident notification timeframes, sub-processor controls, model change notice periods, exit provisions
Domain 7: Concentration and Dependency Risk - single points of failure, market concentration, what happens if this vendor exits the market or is acquired

Step 3: Overall vendor risk rating. State: Critical/High/Medium/Low with a one-paragraph justification referencing the highest-scoring domains.

Step 4: Onboarding conditions. List the specific conditions that must be met before onboarding proceeds. For Tier 1 and Tier 2: these are mandatory. For Tier 3: list as recommended. Each condition must be specific and verifiable - not 'ensure security controls are adequate.'
</instructions>

<output_format>
State the calibration tier at the top before any domain assessment. For each domain: sub-heading, risk narrative paragraph, due diligence questions table. After all domains: overall rating paragraph, then onboarding conditions as a numbered list. Write in British English. No em dashes. All risks must be specific to the vendor type, intended use, and data described - not generic IT vendor risks. A Tier 1 assessment should be materially more detailed than a Tier 3 assessment.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The calibration step before any domain assessment is the fix the original prompt lacked. A Tier 3 standard SaaS tool and a Tier 1 critical AI model in a regulated decision process require fundamentally different assessment depth - the original prompt treated them identically. Domain 3 (data privacy) triggering full depth regardless of tier is the correct rule: personal data processing always requires full scrutiny. The specific onboarding conditions requirement (verifiable, not vague) is what turns a risk assessment into a governance gate.

## Sample Output Fragment

```
CALIBRATION: Tier 1 Critical - all seven domains, maximum depth, evidence required, onboarding conditions mandatory.

Domain 1: AI Model Governance

Risk narrative: [VENDOR_NAME] provides a foundation model via API. The primary model governance risk is that model updates - including changes to safety filters, output behaviour, or underlying weights - are deployed without advance notice, potentially invalidating your EU AI Act technical documentation and your internal risk assessment. Secondary risk: training data provenance is not publicly documented in sufficient detail to confirm the model was not trained on your customers' data submitted via the API.

| Question | Purpose | Priority |
| What is your advance notice period for material model updates, and how is 'material' defined in your terms? | Establishes whether the organisation can maintain current technical documentation as required by EU AI Act Article 11 | Critical |
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
