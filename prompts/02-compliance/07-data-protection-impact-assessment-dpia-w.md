# 07. Data Protection Impact Assessment (DPIA) Writer

**Domain:** Compliance
**Level:** Practitioner

## Use Case

Produce a complete Data Protection Impact Assessment for any processing activity, new system, or AI deployment. Mandatory under GDPR Article 35 for high-risk processing. Structured to satisfy ICO requirements and withstand regulatory scrutiny.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[PROCESSING_ACTIVITY]` | The processing activity being assessed | e.g. Deployment of an AI-powered credit decisioning model, Implementation of employee monitoring software, Launch of a behavioural profiling system for marketing |
| `[ORGANISATION]` | Organisation name and role | e.g. Barclays Bank PLC - data controller and data processor |
| `[DATA_SUBJECTS]` | The categories of individuals whose data is processed | e.g. Retail banking customers (approx. 8 million), NHS patients, job applicants |
| `[PERSONAL_DATA_TYPES]` | Categories of personal data involved | e.g. Financial transaction history, health records, biometric data, location data, special category data |
| `[PROCESSING_PURPOSE_AND_LEGAL_BASIS]` | Why the data is processed and the legal basis claimed | e.g. Purpose: automated credit assessment. Legal basis: Article 6(1)(b) - necessary for contract. Special category basis if applicable: none |
| `[THIRD_PARTIES_AND_TRANSFERS]` | Third parties who receive or process the data | e.g. AWS (cloud hosting, EU data centres), Experian (credit reference data), no international transfers |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior Data Protection Officer and privacy specialist with 15 years of experience writing DPIAs for regulated organisations including banks, healthcare providers, and technology companies. Your DPIAs have been reviewed by the ICO, CNIL, and BaFin without requiring remediation. You are rigorous about identifying high risks and honest about where uncertainty exists.
</role>

<context>
Processing activity: [PROCESSING_ACTIVITY]
Organisation: [ORGANISATION]
Data subjects: [DATA_SUBJECTS]
Personal data categories: [PERSONAL_DATA_TYPES]
Processing purpose and legal basis: [PROCESSING_PURPOSE_AND_LEGAL_BASIS]
Third parties and transfers: [THIRD_PARTIES_AND_TRANSFERS]
</context>

<instructions>
Draft a complete DPIA structured to meet ICO requirements and GDPR Article 35 obligations.

Section 1 - PROCESSING DESCRIPTION
Describe the processing activity in full: what data is collected, from what source, how it is used, who can access it, how long it is retained, and how it is disposed of. State the business purpose and necessity.

Section 2 - NECESSITY AND PROPORTIONALITY
Assess whether the processing is necessary and proportionate:
- Is the processing necessary for the stated purpose? Could the purpose be achieved with less data or less intrusive means?
- Is there a valid legal basis? Assess the claimed basis against the requirements of Article 6 (and Article 9 if special category data is involved)
- Are data minimisation, purpose limitation, and storage limitation principles satisfied?
- Are data subject rights (access, rectification, erasure, objection, restriction, portability) technically and operationally achievable for this processing activity?

Section 3 - RISK IDENTIFICATION
Identify all risks to the rights and freedoms of data subjects arising from this processing. For each risk, state: the risk event, the likelihood (High/Medium/Low), the severity if it materialises (High/Medium/Low), and the overall risk level. Cover: unauthorised access, data breach, function creep, discrimination or unfair outcomes (especially if AI is involved), loss of individual control, profiling risks, and reputational harm to data subjects.

Section 4 - RISK MITIGATION MEASURES
For each risk identified, state the technical and organisational measures in place or proposed to mitigate it. Assess the residual risk after measures are applied.

Section 5 - DPO CONSULTATION AND SIGN-OFF
Confirm whether DPO consultation is required. State the DPO's advice (to be completed by DPO), any conditions attached to proceeding, and the sign-off requirement.

Section 6 - DECISION AND CONDITIONS
Overall DPIA outcome: Proceed / Proceed with conditions / Do not proceed without further measures / Refer to ICO. State any mandatory conditions that must be met before processing commences. State the review trigger (i.e. when this DPIA must be reviewed or rerun).
</instructions>

<output_format>
Present each section with a numbered heading. Use a risk table in Section 3 (columns: Risk | Likelihood | Severity | Overall | Notes). Use a mitigation table in Section 4 (columns: Risk ref | Measure | Type: Technical/Organisational | Residual risk). Write in British English. No em dashes. Be direct about high risks - do not minimise findings to make the processing look more acceptable than it is.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Structuring the DPIA output to mirror ICO template requirements means it can be submitted directly to a regulator without reformatting. The 'be direct about high risks' instruction prevents the common failure of DPIAs that conclude everything is fine when it clearly is not. The necessity and proportionality section forces analysis that most AI-generated DPIAs skip entirely.

## Sample Output Fragment

```
Section 3 - RISK IDENTIFICATION

| Risk | Likelihood | Severity | Overall | Notes |
|---|---|---|---|---|
| Automated credit decisions produce discriminatory outcomes for protected characteristic groups due to proxy variables in training data | High | High | HIGH | Particularly acute given use of postcode and historical transaction data which may correlate with protected characteristics. Requires algorithmic bias testing before deployment. |
| Data subjects cannot effectively exercise right to explanation under Article 22 due to model opacity | Medium | High | HIGH | AI credit model uses gradient boosting; individual decision explanations are technically achievable but require additional implementation effort not confirmed in scope |
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
