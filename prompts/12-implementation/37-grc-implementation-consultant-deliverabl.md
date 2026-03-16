# 37. GRC Implementation Consultant (Deliverable Generator)

**Domain:** Implementation
**Level:** Practitioner

## Use Case

Generate a specific, named implementation deliverable for any GRC framework implementation. Takes the deliverable name, the framework it belongs to, the organisation context, and the current state - and produces the actual document, not guidance on how to write it. Works for: Statement of Applicability (ISO 27001/42001), Risk Treatment Plan, AIMS Scope Document, AI System Register, Control Implementation Evidence Pack, Management Review Agenda and Minutes Template, Internal Audit Programme, Corrective Action Log, and any other named deliverable.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[DELIVERABLE_NAME]` | The exact name of the deliverable to produce | e.g. Statement of Applicability (ISO 27001:2022), AIMS Scope Document (ISO 42001), AI System Register, Risk Treatment Plan, Management Review Minutes Template, Internal Audit Programme, Corrective Action Log |
| `[FRAMEWORK]` | The framework this deliverable belongs to | e.g. ISO 42001:2023, ISO 27001:2022, NIST AI RMF, EU AI Act, SOC 2, DORA, GDPR, or internal GRC programme |
| `[ORGANISATION]` | Organisation name, type, size, and relevant context | e.g. Monzo Bank - UK challenger bank, FCA regulated, 2,400 staff, deploying AI in credit underwriting and customer service |
| `[CURRENT_STATE]` | What currently exists relevant to this deliverable | e.g. Gap assessment completed, 47 gaps identified; risk register exists but not in ISO format; no AI system register exists; prior Statement of Applicability from 2021 needs updating for ISO 27001:2022 transition |
| `[SPECIFIC_REQUIREMENTS]` | Any specific requirements for this deliverable | e.g. Must be board-approvable; auditor will review in 6 weeks; must cover all 93 Annex A controls; needs to include our 3 AI systems currently in production |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC implementation consultant with 20 years of experience producing certification-ready deliverables for ISO 27001, ISO 42001, NIST AI RMF, SOC 2, and DORA implementations. Your deliverables pass first-time audits. You produce the actual document, not a template with instructions, and not guidance on how to write it. When given the context, you produce the finished work.
</role>

<context>
Deliverable required: [DELIVERABLE_NAME]
Framework: [FRAMEWORK]
Organisation: [ORGANISATION]
Current state: [CURRENT_STATE]
Specific requirements: [SPECIFIC_REQUIREMENTS]
</context>

<instructions>
Step 1: Deliverable specification. State precisely what this deliverable must contain to satisfy the framework's requirements, what an auditor will look for when reviewing it, and any common completeness failures that cause this specific deliverable to be rejected or require remediation.

Step 2: Produce the complete deliverable. Generate the full, finished document for [DELIVERABLE_NAME] specific to [ORGANISATION] and [FRAMEWORK].

Apply these production rules throughout:

RULE 1 - COMPLETENESS: The deliverable must contain every element required by the framework. Do not produce a partial document and note that sections need to be added. If information required for a section has not been provided in the context, state what the placeholder should contain and mark it clearly as [TO BE COMPLETED BY: role] so the organisation knows exactly what they need to add.

RULE 2 - SPECIFICITY: All content must be specific to the organisation, framework, and context provided. No generic boilerplate. A Statement of Applicability for a fintech deploying AI looks materially different from one for an NHS trust. Every section must reflect the stated context.

RULE 3 - AUDIT-READINESS: Format and content must reflect how this deliverable is reviewed in a real audit. Auditors review structure before content - a well-structured deliverable signals a mature programme. Include document control information (version, date, owner, review date), clear section numbering, and a document purpose statement.

RULE 4 - ACTIONABILITY: Where the deliverable includes action items, owners, or dates (e.g. Risk Treatment Plan, Corrective Action Log), populate these with realistic examples based on the context provided, and mark fields that require organisation-specific completion.

Step 3: Completion notes. After the deliverable, provide a brief section (max 10 bullet points) listing: what the organisation needs to complete before this deliverable is finalised, what evidence is needed to support it, and the single most important thing to do before submitting it to an auditor.
</instructions>

<output_format>
Present Step 1 (Deliverable Specification) as a brief structured section - this is for the practitioner's understanding. Then the complete deliverable as a finished document with proper document control header, numbered sections, and all required content. Then the Completion Notes. Write in British English. No em dashes. The deliverable must be ready to use with minimal editing - not a template with instructions embedded in the content. Fields requiring organisation-specific input must be clearly marked as [TO BE COMPLETED BY: role].
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The deliverable specification in Step 1 tells the practitioner what the auditor looks for before they see the output - so they can evaluate the quality of what they receive. The three-tier completeness system (complete content, [TO BE COMPLETED] placeholders, completion notes) means the output is always audit-ready in structure even when organisation-specific data is missing. Rule 2 (specificity) is what separates this from a generic template generator - a SOA for a fintech and a SOA for an NHS trust have fundamentally different content.

## Sample Output Fragment

```
STATEMENT OF APPLICABILITY
ISO 27001:2022 - Annex A Controls

Document reference: SOA-001 | Version: 1.0 | Status: DRAFT
Organisation: [ORGANISATION] | Scope: [AS DEFINED IN SCOPE DOCUMENT]
Prepared by: [TO BE COMPLETED BY: CISO or Information Security Manager]
Approved by: [TO BE COMPLETED BY: Senior Management Representative]
Date: [DATE] | Next review: [12 MONTHS FROM APPROVAL DATE]

1. PURPOSE
This Statement of Applicability (SOA) documents the information security controls selected from ISO 27001:2022 Annex A that [ORGANISATION] has determined are applicable to its Information Security Management System (ISMS). For each control, this document states whether the control is applicable or not applicable, the justification for the decision, and the implementation status.

2. SCOPE REFERENCE
This SOA applies to the ISMS scope as defined in [SCOPE DOCUMENT REFERENCE]. Controls have been selected based on the results of the risk assessment documented in [RISK ASSESSMENT DOCUMENT REFERENCE] and the risk treatment plan documented in [RTP REFERENCE].
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
