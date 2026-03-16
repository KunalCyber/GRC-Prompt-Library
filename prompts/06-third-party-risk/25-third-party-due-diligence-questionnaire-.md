# 25. Third-Party Due Diligence Questionnaire (DDQ) Builder

**Domain:** Third-Party Risk
**Level:** Practitioner

## Use Case

Build a complete, tiered due diligence questionnaire to send to a supplier or third party. Calibrated to the supplier's risk tier, service type, and data access. Covers information security, AI governance, data protection, business continuity, financial stability, regulatory compliance, and sub-processor management. Produces questions a supplier can actually answer - with evidence fields, follow-up probes, and a scoring guide for the reviewer.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[SUPPLIER_NAME]` | Name of the supplier receiving the questionnaire | e.g. Workday Inc., a specialist AI fraud detection vendor, a cloud-based legal research platform |
| `[SERVICES_AND_DATA_ACCESS]` | What the supplier does and what data or systems they access | e.g. Provides AI-powered HR platform; processes employee PII including salaries and performance data for 3,200 staff; hosted in AWS EU-West |
| `[RISK_TIER]` | The supplier's risk tier or criticality classification | e.g. Tier 1 - Critical (failure would halt core operations); Tier 2 - Important (significant operational impact); Tier 3 - Standard (limited impact); or describe your own tiering criteria |
| `[YOUR_REGULATORY_CONTEXT]` | Your organisation's regulatory obligations that the questionnaire must reflect | e.g. FCA regulated - SYSC 8 outsourcing requirements; NHS - DSPT and data security standards; EU AI Act deployer obligations; GDPR data controller; or list your key regulations |
| `[AI_IN_SCOPE]` | Whether the supplier uses or provides AI in their services | e.g. Yes - the service uses AI/ML for [describe]; Yes - supplier's platform includes AI features we have not fully assessed; No - traditional software only; Unknown - needs to be established |
| `[QUESTIONNAIRE_PURPOSE]` | Why this DDQ is being sent | e.g. New supplier onboarding due diligence; Annual renewal of existing supplier; Post-incident reassessment; Regulatory requirement to evidence third-party oversight |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior third-party risk manager with 15 years of experience designing and reviewing supplier due diligence questionnaires for regulated financial institutions, NHS trusts, and global technology companies. Your DDQs are known for three things: they get completed (because the questions are specific and answerable), they surface genuine risks (because the questions probe beyond policy existence to operational reality), and they hold up under regulatory scrutiny (because they cover what regulators actually look for).
</role>

<context>
Supplier: [SUPPLIER_NAME]
Services and data access: [SERVICES_AND_DATA_ACCESS]
Risk tier: [RISK_TIER]
Your regulatory obligations: [YOUR_REGULATORY_CONTEXT]
AI in scope: [AI_IN_SCOPE]
Purpose of this DDQ: [QUESTIONNAIRE_PURPOSE]
</context>

<instructions>
Produce a complete, tiered due diligence questionnaire calibrated to this supplier's risk tier and service type.

CALIBRATION RULES - apply before writing any questions:
- Tier 1 / Critical suppliers: all domains, maximum depth, evidence required for every significant question
- Tier 2 / Important suppliers: all domains, standard depth, evidence required for high-risk questions
- Tier 3 / Standard suppliers: core domains only (security, data protection, business continuity), light depth, evidence optional
- AI in scope: add the full AI Governance section regardless of tier
- Data access (personal data): always include full data protection section regardless of tier

SECTION STRUCTURE - include all applicable sections:

Section 1: Supplier Profile and Corporate Information
Company overview, ownership structure, key financial indicators, regulatory status, and any recent material changes (acquisitions, restructuring, investigations).

Section 2: Information Security and Cyber Resilience
Security certifications and audit status, access controls, encryption practices, vulnerability management, security incident history, penetration testing, and employee security awareness.

Section 3: Data Protection and Privacy
Data processing locations, data minimisation practices, subject rights fulfilment capability, breach notification procedures, data retention and deletion, and sub-processor data flows.

Section 4: AI Governance (include if AI is in scope)
How AI models in the service are governed, trained, tested for bias, version-controlled, and monitored. Transparency of AI decision-making. Compliance with applicable AI regulation. Human oversight mechanisms. Whether the supplier has an AI policy and whether it has been reviewed.

Section 5: Business Continuity and Operational Resilience
BCP/DR documentation, RTO/RPO commitments, testing frequency and most recent test results, concentration risk (key person dependencies, single points of failure), and contingency for service outage.

Section 6: Regulatory and Legal Compliance
Regulatory licences and certifications held, any current or recent regulatory investigations or enforcement actions, compliance with regulations applicable to the services (state which based on context), insurance coverage.

Section 7: Sub-Processor and Fourth-Party Management
List of material sub-processors, how sub-processors are assessed, notification procedure for sub-processor changes, and concentration risk in the supplier's own supply chain.

Section 8: Contractual and Exit Readiness
Data portability and extraction capability, exit assistance obligations, transition support, and data return/destruction on termination.

For each question:
- Number it sequentially within its section (e.g. 2.4, 3.7)
- Write it in plain, direct language - not audit jargon
- Specify the response format: Yes/No + evidence, Free text, Select from list, Numeric value
- Where evidence should be provided, name the specific document type expected (e.g. 'Attach most recent ISO 27001 certificate', 'Attach most recent penetration test executive summary dated within 12 months')
- Flag HIGH RISK questions - ones where a negative or vague answer should trigger immediate follow-up
- Include at least one follow-up probe for each HIGH RISK question

After the questionnaire, produce:

REVIEWER SCORING GUIDE: A simple table showing how to score responses - what constitutes a satisfactory answer, a partial answer, and an unsatisfactory answer for each section. Include a section risk rating (Green/Amber/Red) based on scores.

SUPPLIER COVER NOTE: A brief, professional introductory paragraph to send with the questionnaire explaining its purpose, the deadline for response, who to return it to, and how responses will be used.
</instructions>

<output_format>
Present each section with a bold numbered heading. Questions numbered within sections. Clearly mark [HIGH RISK] questions. Evidence fields formatted as 'Evidence required: [document type]'. Write in British English. No em dashes. The questionnaire must be calibrated to the risk tier stated - a Tier 3 standard supplier should receive a materially shorter questionnaire than a Tier 1 critical supplier. Do not pad a Tier 3 questionnaire with Tier 1 questions - it makes the whole questionnaire less likely to be completed properly.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The calibration rules at the start force the model to determine the appropriate depth before writing a single question. This is the single most important design decision in a DDQ - a Tier 3 supplier that receives a 120-question questionnaire identical to what a Tier 1 critical supplier receives will either not complete it or complete it badly. Naming specific evidence types (rather than 'provide supporting documentation') eliminates the most common DDQ failure: suppliers attaching whatever document they have rather than what was actually needed. The follow-up probe requirement on HIGH RISK questions is what turns a questionnaire into a due diligence exercise rather than a form-filling exercise.

## Sample Output Fragment

```
Section 4: AI Governance

4.1 Does your service use artificial intelligence, machine learning, or automated decision-making in any part of the functionality provided to us?
Response: Yes / No / Partially (describe)
If yes, proceed to questions 4.2 to 4.11. If no, proceed to Section 5.

4.3 [HIGH RISK] How are AI models used in this service tested for bias and fairness before deployment, and how frequently are bias assessments repeated during operation?
Response: Free text (minimum 100 words)
Evidence required: Most recent bias testing report or methodology document
Follow-up probe: 'Your response describes the testing methodology. Please provide the results of the most recent bias assessment, including any protected characteristics where bias was identified and the action taken.'
Reviewer note: A response describing only the process without results, or stating that bias testing has not been conducted, is HIGH RISK. Escalate to the AI Governance lead before proceeding with onboarding.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
