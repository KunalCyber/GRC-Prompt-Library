# 31. Universal Policy Maker

**Domain:** Policy Writing
**Level:** Practitioner

## Use Case

Generate a complete, production-ready policy document for any policy type - AUP, AI Policy, Change Management, Information Security, Data Protection, Third-Party Risk, Business Continuity, and more. Output is tailored to the organisation, aligned to the relevant frameworks, and ready for leadership review and approval.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[POLICY_TYPE]` | The exact name of the policy to draft | e.g. Acceptable Use Policy, AI Governance Policy, Change Management Policy, Data Retention Policy, Third-Party Risk Management Policy |
| `[ORGANISATION]` | Full organisation name and type | e.g. Lloyds Banking Group PLC - UK retail and commercial bank regulated by FCA and PRA |
| `[INDUSTRY_AND_SIZE]` | Industry sector, employee count, and key regulatory context | e.g. NHS Trust, 4,200 staff, regulated by CQC and ICO, subject to DSPT requirements |
| `[APPLICABLE_FRAMEWORKS]` | Standards, regulations, or frameworks this policy must align to | e.g. ISO 27001:2022, GDPR, EU AI Act, ISO 42001:2023, NIST CSF, FCA SYSC, internal risk framework |
| `[SCOPE_AND_EXCLUSIONS]` | What and who this policy covers, and what is explicitly excluded | e.g. Covers all staff, contractors, and third parties accessing organisation systems. Excludes legacy mainframe environment pending migration. |
| `[KEY_RISKS_TO_ADDRESS]` | The specific risks or obligations that triggered this policy | e.g. Recent AI deployment without governance controls; regulatory requirement under EU AI Act Article 4; internal audit finding F-2024-07 |
| `[TONE_AND_AUDIENCE]` | Who will read this policy and the tone required | e.g. All staff - plain English, accessible. Senior management - strategic and accountability-focused. Technical teams - precise and specific. |
| `[EXISTING_RELATED_POLICIES]` | Policies this document should cross-reference or not duplicate | e.g. Information Security Policy v3.2, Data Protection Policy v2.0, or 'none' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC policy specialist with 20 years of experience writing policies for regulated financial institutions, NHS trusts, global technology companies, and professional services firms. Your policies are used in regulatory submissions, certification audits, and board approvals. They are precise, enforceable, and written in language appropriate to their audience. You do not produce generic templates - every policy you write is specific to the organisation and its context.
</role>

<context>
Policy type: [POLICY_TYPE]
Organisation: [ORGANISATION]
Industry, size, and regulatory context: [INDUSTRY_AND_SIZE]
Applicable frameworks and regulations: [APPLICABLE_FRAMEWORKS]
Scope and exclusions: [SCOPE_AND_EXCLUSIONS]
Key risks or obligations this policy addresses: [KEY_RISKS_TO_ADDRESS]
Tone and primary audience: [TONE_AND_AUDIENCE]
Related policies to cross-reference: [EXISTING_RELATED_POLICIES]
</context>

<instructions>
Draft a complete, production-ready [POLICY_TYPE] for [ORGANISATION].

Step 1: Determine the correct section structure for this policy type. A Change Management Policy requires different sections than an Acceptable Use Policy. Use the standard section structure for the stated policy type. Do not use a generic one-size-fits-all structure.

Step 2: Write the document header block:
- Policy title
- Policy reference number: [TO BE ASSIGNED]
- Version: 1.0
- Status: DRAFT - FOR REVIEW
- Effective date: [TO BE CONFIRMED BY POLICY OWNER]
- Review date: [12 MONTHS FROM EFFECTIVE DATE]
- Policy owner: [ROLE TO BE ASSIGNED]
- Approved by: [APPROVER ROLE AND DATE - TO BE COMPLETED]
- Related policies: [list from context, or state 'none']

Step 3: Write each section in full. Apply these non-negotiable rules throughout:

RULE 1 - SPECIFICITY. Every obligation, control, and requirement must be specific to [ORGANISATION], its industry, its systems, and its regulatory context. No generic statements that could apply to any organisation. Reference the specific frameworks listed where obligations derive from them.

RULE 2 - ENFORCEABILITY. Every obligation must be testable and evidentiable. Replace vague obligations ('take appropriate measures', 'use reasonable care') with specific ones ('submit a request via the IT service desk before accessing any system not listed in the approved software register'). If a legal minimum requires vague language, state it, then add a specific operational interpretation immediately below.

RULE 3 - COMPLETENESS. The policy must cover the full scope stated. Do not omit sections because they are complex.

RULE 4 - TONE. Match the tone to the stated audience. If audience is all staff, use plain English with defined terms. If audience is technical, use precise technical language. If audience is senior management, use strategic framing. Do not mix registers within a section.

RULE 5 - FORMAT. Use numbered sections and sub-sections (e.g. 4.1, 4.2). Use full sentences in policy language - no bullet lists in the policy body. Tables are permitted for roles and responsibilities matrices, control summaries, and classification schemes.

Step 4: Write a Roles and Responsibilities section as a table with columns: Role | Responsibilities under this policy.

Step 5: Write a Compliance and Consequences section stating: how compliance will be monitored, the frequency of review, and the consequences of non-compliance (reference the disciplinary policy or equivalent without stating specific sanctions unless required by regulation).

Step 6: Write a Definitions section covering all defined terms used in the policy body. Definitions must match the applicable frameworks where terms are defined by regulation (e.g. use EU AI Act Article 3 definitions for AI-related terms, GDPR Article 4 definitions for personal data terms).
</instructions>

<output_format>
Present the complete policy document in order: document header block, then numbered sections in the correct order for this policy type, ending with the Definitions section. Write in British English. No em dashes. No bullet lists in the policy body. The Roles and Responsibilities section must be a table. All defined terms used in the policy body must appear in the Definitions section. The policy must read as a finished document - not a template with placeholder guidance notes.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Step 1 forces the model to determine the correct structure for the specific policy type before writing - an Information Security Policy and a Change Management Policy have fundamentally different section requirements. The five non-negotiable rules eliminate the four most common policy failures: generic content, unenforceable obligations, incomplete scope, and tone mismatch. The specificity rule with the prohibition on generic statements is the single instruction that most improves output quality.

## Sample Output Fragment

```
CHANGE MANAGEMENT POLICY

Policy reference: [TO BE ASSIGNED] | Version: 1.0 | Status: DRAFT
Effective date: [TO BE CONFIRMED] | Review date: [12 months from effective date]
Policy owner: Chief Information Officer | Approved by: [TO BE COMPLETED]

1. PURPOSE

1.1 This policy establishes the requirements for managing changes to [ORGANISATION]'s IT systems, applications, infrastructure, and operational processes in a controlled and auditable manner. It applies to all changes - standard, normal, and emergency - affecting systems within the scope defined in Section 3.

1.2 This policy is issued in response to [KEY_RISKS_TO_ADDRESS] and is aligned to [APPLICABLE_FRAMEWORKS]...
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
