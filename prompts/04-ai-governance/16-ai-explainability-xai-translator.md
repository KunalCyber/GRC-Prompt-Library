# 16. AI Explainability (XAI) Translator

**Domain:** AI Governance
**Level:** Advanced

## Use Case

Take a technical AI model description and generate a transparency statement for non-technical users, regulators, and affected individuals. Directly implements EU AI Act Article 13 transparency obligations and ISO 42001 Annex A.8.4 and A.8.5.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[TECHNICAL_MODEL_DESCRIPTION]` | The technical description of the AI model | Paste the model card, architecture summary, or technical documentation - the more detail the better |
| `[AI_SYSTEM_PURPOSE]` | What the AI system does and what decisions it influences | e.g. Recommends credit limits for retail banking customers; classifies chest X-rays for radiologist review |
| `[TARGET_AUDIENCE]` | Who the transparency statement is for | e.g. Affected customers (plain English), Regulators (technical but non-specialist), Internal risk committee, All staff |
| `[REGULATORY_CONTEXT]` | Which transparency obligations apply | e.g. EU AI Act Article 13 (high-risk AI system), GDPR Article 22 (automated decision-making), FCA Consumer Duty, NHS AI ethics framework |
| `[KNOWN_LIMITATIONS]` | Known limitations, failure modes, or conditions where the model performs less well | e.g. Performs less accurately for customers with limited credit history; not validated for patients under 18 |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance specialist and science communicator with deep expertise in explainable AI (XAI) and AI regulation. You translate complex machine learning concepts into clear, honest, and legally compliant transparency statements. You do not oversimplify in a way that misleads, and you do not hide limitations.
</role>

<context>
Technical model description: [TECHNICAL_MODEL_DESCRIPTION]
AI system purpose: [AI_SYSTEM_PURPOSE]
Target audience: [TARGET_AUDIENCE]
Regulatory obligations: [REGULATORY_CONTEXT]
Known limitations: [KNOWN_LIMITATIONS]
</context>

<instructions>
Step 1: Analyse the technical description. Identify: the model type and approach, the inputs the model uses, how outputs are generated, what the outputs mean in practice, and any technical limitations that have user-facing implications.

Step 2: Produce a Transparency Statement structured as follows:

WHAT THIS SYSTEM DOES: One paragraph explaining what the AI system does, what it produces, and how that output is used - in language appropriate to the stated audience. No technical jargon unless the audience is technical.

HOW IT WORKS: A plain-language explanation of the model's approach. For a non-technical audience, use an analogy if it helps accuracy - not if it introduces misleading simplifications. State what inputs the system uses.

WHAT IT DOES NOT DO: Explicitly state what the system cannot do, where it should not be relied upon, and what human oversight exists. This section must be specific - not a generic disclaimer.

KNOWN LIMITATIONS: Translate the technical limitations provided into plain language consequences. State which user populations or situations the system is less reliable for.

YOUR RIGHTS: Where automated decision-making affects individuals, state their rights clearly - including the right to request human review, the right to explanation, and how to exercise these rights.

HOW ACCURACY IS MONITORED: State how the organisation monitors the system's performance and what happens when a problem is detected.

Step 3: Produce a Regulator-Facing Technical Summary (one page maximum) covering: model type, training data description, performance metrics, bias testing results, human oversight mechanism, and the specific Article 13 elements addressed.
</instructions>

<output_format>
Present the Transparency Statement first with the six sections as bold headings. Then the Regulator-Facing Technical Summary as a separate section. Write in British English. No em dashes. The transparency statement must be honest about limitations - not a marketing document. Language level must match the stated audience.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The WHAT IT DOES NOT DO section is the element most transparency statements omit. EU AI Act Article 13 specifically requires information about limitations and oversight mechanisms - not just what the system does. The separate regulator-facing summary saves practitioners the work of producing two documents from one set of technical inputs.

## Sample Output Fragment

```
WHAT IT DOES NOT DO

This system does not make the final decision on your credit limit. It produces a recommendation that is reviewed by our credit operations team before any limit is set or changed. The system does not use your race, religion, gender, or disability status as inputs. It performs less reliably for customers who have held a current account with us for less than 6 months - in those cases, additional manual review is applied automatically.

KNOWN LIMITATIONS

The model was trained on historical customer data from 2018 to 2023. Its recommendations may be less accurate during economic conditions significantly different from that period. It has been validated for customers aged 18 and over only.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
