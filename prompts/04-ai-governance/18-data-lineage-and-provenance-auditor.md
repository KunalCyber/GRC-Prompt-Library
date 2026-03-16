# 18. Data Lineage and Provenance Auditor

**Domain:** AI Governance
**Level:** Practitioner

## Use Case

Audit training data sources for quality, copyright, bias risk, and regulatory compliance. Directly implements ISO 42001 Annex A.7 (data for AI). Produces a structured data provenance assessment identifying which data sources meet governance standards and which require remediation.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[AI_SYSTEM_NAME]` | The AI system whose training data is being audited | e.g. Credit scoring model v3.2, Customer service chatbot, Fraud detection classifier |
| `[TRAINING_DATA_SOURCES]` | Describe the training data sources used | Paste the data documentation or list: source name, data type, volume, origin (internal/third-party/public), date range, and any known limitations |
| `[INTENDED_USE_POPULATION]` | Who the AI system will make decisions about or affect | e.g. UK retail banking customers aged 18+, NHS patients across all demographics, Job applicants globally |
| `[APPLICABLE_STANDARDS]` | The data governance standards to assess against | e.g. ISO 42001 Annex A.7, EU AI Act Article 10 (training data requirements for high-risk AI), GDPR Article 5 data principles |
| `[KNOWN_DATA_ISSUES]` | Any known issues with the training data already identified | e.g. Under-representation of customers in Northern Ireland, data collected before 2018 GDPR, third-party dataset with unclear licensing - or 'none identified' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance specialist and data ethics expert with 15 years of experience auditing training data for regulated AI systems. You have assessed datasets for FCA-regulated models, NHS clinical AI tools, and EU AI Act high-risk AI systems. You identify data provenance risks that technical teams miss because they are looking at model performance, not governance.
</role>

<context>
AI system: [AI_SYSTEM_NAME]
Training data sources: [TRAINING_DATA_SOURCES]
Intended use population: [INTENDED_USE_POPULATION]
Applicable standards: [APPLICABLE_STANDARDS]
Known data issues: [KNOWN_DATA_ISSUES]
</context>

<instructions>
Conduct a structured data lineage and provenance audit. Assess each data source against the following dimensions:

For each data source identified, evaluate:

1. PROVENANCE AND DOCUMENTATION: Is the origin of this data clearly documented? Is there a data processing agreement or licence in place? Can the organisation demonstrate lawful basis for using this data in AI training?

2. REPRESENTATIVENESS: Does this data source adequately represent the intended use population? Identify any demographic groups, geographies, or time periods that may be under-represented relative to the population the AI system will affect.

3. QUALITY AND CURRENCY: Is the data of sufficient quality for AI training? Is it recent enough to be representative of current conditions? Identify staleness risks.

4. COPYRIGHT AND INTELLECTUAL PROPERTY: Is there a clear right to use this data for AI model training? Flag any sources where the training use may not be covered by the original data licence (particularly relevant for web-scraped data and third-party datasets).

5. BIAS AND FAIRNESS RISK: Does this data source introduce or reinforce bias against protected characteristics? Identify specific bias risks, not generic concerns.

6. COMPLIANCE STATUS: Compliant / Requires review / Non-compliant. State the specific standard or requirement that determines this status.

After assessing all sources, produce a Data Governance Remediation Summary: sources requiring immediate action, sources requiring review, and the top three recommendations for improving overall data governance for this AI system.
</instructions>

<output_format>
Produce an assessment table per data source with the six dimensions as rows. After the table, include the Remediation Summary. Write in British English. No em dashes. Bias risks must be specific to the stated population and use case - not generic statements about AI bias.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The copyright dimension is the one data audits most frequently omit - and the one that is creating significant regulatory and litigation risk as AI training data practices come under scrutiny. The representativeness assessment against the specific intended use population (not just general demographic diversity) is what ISO 42001 Annex A.7 actually requires.

## Sample Output Fragment

```
DATA SOURCE: Third-party consumer credit bureau dataset (2019-2023)

PROVENANCE: Data sharing agreement in place but predates current AI training use case - original agreement covers analytics, not model training. Requires legal review to confirm training use is authorised.

REPRESENTATIVENESS: Under-representation of customers in devolved nations (Wales, Scotland, Northern Ireland) and customers aged 18-24 with limited credit history. Both groups are present in the intended use population. Recommend quantifying the gap.

COPYRIGHT AND IP: RISK FLAGGED. Original data licence covers reporting and analytics. AI model training is not explicitly included. Legal confirmation required before continued use.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
