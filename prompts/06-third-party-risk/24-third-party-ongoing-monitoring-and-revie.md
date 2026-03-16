# 24. Third-Party Ongoing Monitoring and Review

**Domain:** Third-Party Risk
**Level:** Practitioner

## Use Case

Conduct a structured periodic review of an existing supplier or third-party relationship. Covers performance against contractual obligations, risk profile changes, compliance status, and whether the relationship continues to meet the organisation's risk appetite. The operational third-party risk work that happens after onboarding - quarterly reviews, triggered reassessments, and annual due diligence renewals.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[SUPPLIER_NAME]` | Name of the supplier being reviewed | e.g. AWS, Salesforce, a specialist AI model provider, a managed security services provider |
| `[SERVICES_PROVIDED]` | What the supplier provides and what data or systems they access | e.g. Cloud hosting for core banking platform; processes customer PII; classified as critical supplier |
| `[REVIEW_TYPE]` | Type of review being conducted | e.g. Quarterly performance review, Annual due diligence renewal, Triggered review following an incident, Pre-contract renewal assessment |
| `[LAST_REVIEW_FINDINGS]` | What the last review found and what actions were agreed | e.g. Two medium risks identified: SLA breach in Q2, subprocessor not notified within required timeframe. Both marked as remediated. Or 'first review - no prior findings' |
| `[CHANGES_SINCE_LAST_REVIEW]` | Anything that has changed since the last review | e.g. Supplier acquired by a US company, supplier experienced a security incident affecting other clients, new AI features added to the platform, your organisation's data volumes with this supplier doubled |
| `[RISK_APPETITE]` | Your organisation's risk appetite for this supplier relationship | e.g. Critical supplier - zero tolerance for unresolved high risks; Standard supplier - high risks must be mitigated within 90 days; low criticality - medium risks acceptable |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior third-party risk manager with 15 years of experience managing supplier relationships for regulated financial institutions, NHS trusts, and global technology companies. You conduct reviews that identify genuine risk changes - not checkbox exercises. You know what questions reveal real problems and what answers should trigger escalation.
</role>

<context>
Supplier: [SUPPLIER_NAME]
Services and data access: [SERVICES_PROVIDED]
Review type: [REVIEW_TYPE]
Last review findings and agreed actions: [LAST_REVIEW_FINDINGS]
Changes since last review: [CHANGES_SINCE_LAST_REVIEW]
Risk appetite for this relationship: [RISK_APPETITE]
</context>

<instructions>
Produce a structured third-party review covering all of the following.

Part A: Change Impact Assessment
Assess each change described since the last review. For each change, determine:
- Whether the change materially affects the risk profile of this relationship
- Whether the change triggers a contractual notification obligation (yours to the supplier or theirs to you)
- Whether the change requires a formal risk reassessment or can be noted as a monitoring item
- The specific action required (if any) and urgency

Part B: Prior Findings Verification
For each finding from the last review marked as remediated, specify:
- What evidence should be requested to confirm the remediation is genuine (not just reported)
- What a paper remediation looks like versus a real one (the failure mode to watch for)
- Whether the remediation addresses the root cause or only the symptom

Part C: Periodic Review Questions
Produce a structured set of review questions to put to the supplier covering:
1. Security and resilience posture - any changes to certifications, audits, incidents, or key controls
2. Regulatory and compliance status - any regulatory actions, investigations, or material compliance changes
3. Sub-processor and fourth-party changes - any changes to the supplier's own supply chain that affect the services
4. AI-specific questions (if applicable) - any changes to AI features, models, or automated decision-making in the services
5. Key person and organisational changes - leadership changes, acquisitions, restructuring that could affect service delivery

For each question: the question text, the purpose, and what a concerning answer looks like.

Part D: Risk Rating Update
Based on everything above, produce an updated risk rating for this relationship:
- Current risk rating: Critical / High / Medium / Low
- Direction of travel: Increasing / Stable / Decreasing
- Rationale (one paragraph)
- Whether the relationship continues to sit within the stated risk appetite

Part E: Actions and Escalations
- Actions to be completed before next review (specific, owned, time-bound)
- Any items requiring escalation to senior management or board
- Whether a formal risk reassessment is triggered
- Recommended next review date and type
</instructions>

<output_format>
Present each Part with a bold heading. Use a table for Part A (columns: Change | Risk impact | Contractual trigger | Action required | Urgency). Use numbered questions for Part C. Write in British English. No em dashes. The review must be proportionate to the supplier's criticality - a critical supplier review should be more rigorous than a standard one given the same information.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The 'paper remediation versus real remediation' guidance in Part B is the element that most periodic reviews miss. Suppliers report findings as closed; reviewers accept the report without checking. The change impact assessment before the standard questions ensures the review is risk-driven, not just a routine repetition of last time. The fourth-party question in Part C is the one that catches the supply chain risks that only appear when a supplier's own suppliers change.

## Sample Output Fragment

```
Part B: Prior Findings Verification

Finding: Subprocessor not notified within required contractual timeframe (marked remediated)

Evidence to request: Updated subprocessor notification procedure with version date after the finding; evidence of at least one subsequent subprocessor notification that followed the new procedure (e.g. an email or system record showing notification was sent within the required timeframe).

Paper remediation failure mode: Supplier submits an updated policy document. This confirms the policy was changed - not that the process is now operating correctly. A genuine remediation shows the new process being executed, not just defined.

Root cause check: The original finding was a process failure (notification not sent in time). A policy update addresses the documentation. Ask specifically: what changed in the operational process that ensures the notification happens automatically or is assigned to a named role with a deadline?
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
