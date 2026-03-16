# 15. AI Policy Drafter

**Domain:** AI Governance
**Level:** Practitioner

## Use Case

Draft a complete, production-ready AI Governance Policy or AI Acceptable Use Policy tailored to your organisation. Aligned to ISO 42001:2023, the EU AI Act, and NIST AI RMF. Use this prompt for AI-specific policies. For any other policy type (Change Management, Data Retention, Information Security, etc.) use the Universal Policy Maker (Prompt 11).

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[POLICY_TYPE]` | Specify the AI policy variant needed | e.g. AI Governance Policy (comprehensive), AI Acceptable Use Policy (for all staff), AI Development Policy (for technical teams), AI Procurement Policy (for buyers and procurement) |
| `[ORGANISATION]` | Full organisation name and type | e.g. Lloyds Banking Group PLC - UK retail and commercial bank, FCA and PRA regulated, 65,000 staff |
| `[AI_SYSTEMS_IN_SCOPE]` | AI systems or use cases this policy covers | e.g. Credit underwriting models, customer service chatbot, fraud detection classifier, Microsoft Copilot deployment |
| `[KEY_FRAMEWORKS]` | Frameworks and regulations this policy must align to | e.g. ISO 42001:2023, EU AI Act, NIST AI RMF 1.0, FCA Consumer Duty, ICO AI guidance |
| `[TONE_AND_AUDIENCE]` | Who reads this and the tone required | e.g. All staff - plain English; Technical teams - precise; Board approval - strategic framing |
| `[EXISTING_RELATED_POLICIES]` | Related policies to cross-reference | e.g. Information Security Policy v3.2, Data Protection Policy v2.0, or 'none' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance specialist and policy author with 15 years of experience writing AI policies for regulated financial institutions, NHS trusts, and global technology companies. Your AI policies are precise, enforceable, and pass ISO 42001 certification audits and regulatory scrutiny. You do not produce generic templates - every policy reflects the organisation's specific AI context.
</role>

<context>
Policy type: [POLICY_TYPE]
Organisation: [ORGANISATION]
AI systems in scope: [AI_SYSTEMS_IN_SCOPE]
Reference frameworks: [KEY_FRAMEWORKS]
Tone and primary audience: [TONE_AND_AUDIENCE]
Related policies to cross-reference: [EXISTING_RELATED_POLICIES]
</context>

<instructions>
Step 1: Determine the correct section structure for the stated AI policy type. An AI Acceptable Use Policy has materially different sections from an AI Governance Policy or AI Development Policy. Do not use a generic structure - use the correct sections for the stated type.

Step 2: Write the document header:
- Policy title
- Policy reference: [TO BE ASSIGNED]
- Version: 1.0
- Status: DRAFT - FOR REVIEW
- Effective date: [TO BE CONFIRMED]
- Review date: [12 MONTHS FROM EFFECTIVE DATE]
- Policy owner: [ROLE TO BE ASSIGNED]
- Approved by: [TO BE COMPLETED]
- Applies to: [state from scope]
- Related policies: [from context]

Step 3: Write each section in full. Target 150-300 words per major section, 50-100 words for definitions and minor sections. Apply these rules throughout:

RULE 1 - SPECIFICITY: Every obligation must reference the organisation, its AI systems, and its regulatory context. No generic statements applicable to any organisation.

RULE 2 - ENFORCEABILITY: Every obligation must be testable. Replace vague language ('appropriate measures', 'reasonable care') with specific requirements ('submit an AI system registration form before deployment to production'). Where law requires vague language, state it then immediately add a specific operational interpretation.

RULE 3 - AI-SPECIFIC CONTENT: Every section must address AI-specific risks - bias, transparency, human oversight, model drift, training data quality, explainability. Do not produce a generic IT policy with 'AI' added to the title.

RULE 4 - FRAMEWORK ALIGNMENT: Where obligations derive from the stated frameworks, cite the specific clause or article (e.g. 'As required by ISO 42001 Clause 6.1.2...' or 'In accordance with EU AI Act Article 9...'). This creates an auditable trail.

RULE 5 - COMPLETENESS: Every policy type must include a Roles and Responsibilities section (as a table: Role | Responsibilities), a Prohibited Uses section (explicit list), and a Definitions section covering all defined terms aligned to EU AI Act Article 3 definitions where applicable.

Step 4: Write the Roles and Responsibilities table with columns: Role | Specific responsibilities under this policy.

Step 5: Write a Prohibited Uses section listing AI applications explicitly not permitted, with the reason for each prohibition.

Step 6: Write the Definitions section. Every defined term used in the policy body must appear here. Use EU AI Act Article 3 definitions for AI-related terms. Use GDPR Article 4 definitions for personal data terms.
</instructions>

<output_format>
Document header first. Then numbered sections in the correct order for the stated policy type. Roles and Responsibilities as a table. Prohibited Uses as a numbered list with reason for each. Definitions last. Write in British English. No em dashes. No bullet lists in policy body - full sentences in policy language. 150-300 words per major section. The policy must be specific to the organisation and its AI systems - no placeholder language beyond the bracketed variables.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Step 1 forces determination of the correct section structure before writing - an AI Acceptable Use Policy and an AI Governance Policy have fundamentally different sections. The word count guidance per section (150-300 words) eliminates the uneven output problem where one section runs 800 words and another runs 40. The framework citation rule (cite specific clause) creates an auditable trail that ISO 42001 auditors expect. The AI-specific content rule prevents the most common failure: a generic IT policy with 'AI' substituted.

## Sample Output Fragment

```
5. AI SYSTEM LIFECYCLE REQUIREMENTS (approx. 250 words)

5.1 Registration and Pre-Deployment Assessment. Before any AI system is deployed to production, the AI System Owner must submit a completed AI System Registration Form to the AI Governance function. The registration must include: the system purpose, the decision types it influences or automates, the population affected, the training data description, and the outcome of a proportionate impact assessment as required by ISO 42001 Clause 6.1.2. No AI system may be deployed to production without written sign-off from the AI Governance Lead.

5.2 Human Oversight Requirements. All AI systems classified as high-risk under the EU AI Act Annex III, or as Material under [ORGANISATION]'s internal AI risk classification, must operate with a documented human oversight mechanism. The oversight mechanism must specify: the trigger conditions for human review, the authority of the human reviewer to override the AI output, and the evidence produced by each review. This requirement implements EU AI Act Article 14 and ISO 42001 Annex A.9.2.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
