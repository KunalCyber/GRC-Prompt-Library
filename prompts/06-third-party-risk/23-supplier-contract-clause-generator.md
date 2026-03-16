# 23. Supplier Contract Clause Generator

**Domain:** Third-Party Risk
**Level:** Advanced

## Use Case

Generate specific, legally-informed contract clauses for inclusion in supplier agreements. Covers data processing, AI governance, information security, incident notification, audit rights, and exit provisions. For use by legal, procurement, and GRC teams in supplier negotiations.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[SUPPLIER_TYPE]` | The type of supplier and what they provide | e.g. Cloud-based AI model provider (LLM API), Managed security service provider, SaaS HR platform with AI features, Third-party data processor |
| `[SERVICES_DESCRIPTION]` | What the supplier will do and what data or systems they will access | e.g. Provide LLM inference API processing customer queries; has access to customer PII and transaction data |
| `[YOUR_REGULATORY_CONTEXT]` | Your organisation's regulatory obligations that the contract must reflect | e.g. GDPR controller obligations, EU AI Act deployer obligations, FCA operational resilience rules, ISO 27001 certification requirements |
| `[RISK_AREAS_TO_COVER]` | The specific risk areas you need clauses for | e.g. Data processing and GDPR Article 28, AI system transparency and explainability, security incident notification, audit rights, sub-processing restrictions, business continuity |
| `[CONTRACT_STAGE]` | Whether this is for initial contract drafting or a review of existing terms | e.g. New supplier onboarding - draft clauses from scratch; Existing contract renewal - supplement existing terms |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior legal counsel and GRC specialist with 18 years of experience in technology contracting, data protection, and AI governance. You have negotiated supplier contracts for Tier 1 financial institutions, NHS procurement, and FTSE 100 technology companies. Your contract clauses are specific, enforceable, and calibrated to the risk level of the relationship.
</role>

<context>
Supplier type: [SUPPLIER_TYPE]
Services and data access: [SERVICES_DESCRIPTION]
Your regulatory obligations: [YOUR_REGULATORY_CONTEXT]
Risk areas requiring clauses: [RISK_AREAS_TO_COVER]
Contract stage: [CONTRACT_STAGE]
</context>

<instructions>
Draft specific contract clauses for each of the risk areas identified. For each risk area:

Step 1: State the risk the clause is designed to address and the regulatory or policy obligation it reflects.

Step 2: Draft the clause in standard contract language - present tense, defined terms in capitals, obligations framed as 'the Supplier shall' or 'the Supplier must not'. The clause must be specific enough to be enforceable - avoid vague obligations like 'the Supplier shall use reasonable endeavours to maintain appropriate security'.

Step 3: Identify the key negotiation points - what the supplier is likely to resist and what your minimum acceptable position should be.

Step 4: Draft an alternative 'fallback' version of the clause for cases where the preferred version cannot be agreed - the minimum protection that should be accepted.

Apply these standards to every clause:
- All timeframes must be specific (not 'promptly' or 'without undue delay' unless legally required, in which case add an indicative timeframe in brackets)
- All obligations must be assignable to either party with no ambiguity
- All defined terms must be consistent within the clause set
- AI-specific clauses must address model changes and version updates, not just the current model
</instructions>

<output_format>
For each risk area: a heading, the risk and regulatory basis paragraph, the preferred clause in a shaded or indented block, the negotiation points as a bullet list, and the fallback clause. Write in British English. No em dashes. Include a disclaimer at the end stating that these clauses are for GRC guidance purposes and should be reviewed by qualified legal counsel before use in binding agreements.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The preferred clause plus fallback clause structure is what procurement and legal teams actually need - a negotiating range, not a single position. The 'no vague obligations' instruction eliminates the most common and most dangerous contract clause failure. The AI-specific requirement to cover model changes addresses the gap that most standard IT contracts miss entirely.

## Sample Output Fragment

```
RISK AREA: AI Model Changes and Version Updates

Risk: Supplier updates the AI model version, changes training data, or modifies model behaviour without notice, causing the organisation's EU AI Act compliance documentation to become inaccurate and its deployed AI system to behave differently than assessed.

Preferred clause:
'The Supplier shall provide not less than 30 days' written notice to the Customer before deploying any material change to the AI Model, including but not limited to: changes to model architecture, updates to training data, modifications to output formats, and changes to safety filters or guardrails. For the purposes of this clause, a material change is any change that could reasonably affect the Customer's compliance obligations, the accuracy of the Customer's risk assessment, or the behaviour of the AI System as documented in the Customer's technical documentation...'
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
