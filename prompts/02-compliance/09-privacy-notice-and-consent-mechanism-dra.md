# 09. Privacy Notice and Consent Mechanism Drafter

**Domain:** Compliance
**Level:** Practitioner

## Use Case

Draft a complete, GDPR-compliant privacy notice or consent mechanism for any processing activity, product, or service. Covers all mandatory Article 13 and 14 content, plain English accessibility requirements, and layered notice structure. Suitable for websites, apps, employee notices, AI system transparency statements, and customer-facing communications.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[NOTICE_TYPE]` | The type of notice or consent mechanism needed | e.g. Website privacy notice, App privacy notice, Employee privacy notice, AI system transparency notice, Cookie consent banner, Marketing consent form, Research participant consent form |
| `[ORGANISATION]` | Organisation name and type | e.g. Fintech Ltd, UK-based payments company; NHS Trust; global e-commerce retailer |
| `[DATA_SUBJECTS]` | Who the notice is addressed to | e.g. Website visitors and registered customers; employees and contractors; research participants aged 18+ |
| `[PROCESSING_ACTIVITIES]` | What personal data is collected and how it is used | e.g. Name, email, browsing behaviour for marketing personalisation and fraud prevention; employee work data for payroll, performance management, and IT monitoring |
| `[LEGAL_BASES]` | The legal bases for processing | e.g. Contract (account management), legitimate interests (fraud prevention), consent (marketing), legal obligation (payroll); or 'to be determined' |
| `[SPECIAL_FEATURES]` | Any special features requiring specific notice content | e.g. Automated decision-making including profiling; AI system making recommendations; special category data processed; international transfers to US processors; children may be users |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior data protection specialist and GDPR practitioner with 12 years of experience drafting privacy notices for regulated organisations, technology companies, and healthcare providers. Your notices are ICO-compliant, pass legal review, and are actually read by data subjects because they are clear, honest, and concise.
</role>

<context>
Notice type: [NOTICE_TYPE]
Organisation: [ORGANISATION]
Data subjects: [DATA_SUBJECTS]
Processing activities: [PROCESSING_ACTIVITIES]
Legal bases: [LEGAL_BASES]
Special features: [SPECIAL_FEATURES]
</context>

<instructions>
Step 1: Notice architecture. Determine the appropriate structure for this notice type: a single-layer full notice, a layered notice (short version plus full version), or a just-in-time notice at point of collection. State the recommended structure and why, based on the context.

Step 2: Draft the complete notice covering all mandatory GDPR Article 13 and 14 content:

- Identity and contact details of the controller
- Contact details of the DPO (if applicable)
- Purposes and legal bases for each processing activity
- Legitimate interests assessment summary (where legitimate interests is the legal basis)
- Categories of personal data collected
- Recipients and categories of recipients
- International transfers and safeguards
- Retention periods or criteria for determining them
- All data subject rights applicable to this processing
- Right to withdraw consent (where consent is the legal basis)
- Right to lodge a complaint with the ICO
- Whether provision of personal data is a statutory or contractual requirement
- Automated decision-making and profiling (if applicable)

Step 3: For any consent mechanism requested, draft the consent wording that meets GDPR requirements: specific, informed, unambiguous, freely given, and as easy to withdraw as to give. Include the visual presentation guidance (what the checkbox or button should say and how it should be presented).

Step 4: Plain English assessment. Review the drafted notice and flag any sentences that fail the plain English test for the stated audience. Rewrite flagged sentences.
</instructions>

<output_format>
Present Step 1 as a brief recommendation. The notice itself with each section as a bold heading in the correct legal order. Consent wording in a box with presentation guidance below it. Plain English flags as a separate section listing the revised sentences. Write in British English. No em dashes. The notice must be specific to the processing activities described - not a generic template. Legal bases must match the processing purposes stated.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The Step 1 architecture decision prevents the most common privacy notice failure: writing a 3,000-word single-layer notice when a layered approach would serve the data subject better and satisfy ICO guidance. The plain English assessment step catches the legalese that creeps into notice drafting and that ICO enforcement action frequently targets. The legitimate interests assessment summary is the element most notices omit and that the ICO increasingly scrutinises.

## Sample Output Fragment

```
HOW LONG WE KEEP YOUR DATA

We keep your account data for as long as you have an account with us and for 7 years after you close it. This is because we are required by financial regulations to retain records of transactions for this period.

We keep data we use only for marketing for 2 years from the date you last engaged with our communications, or until you ask us to stop, whichever comes first.

We keep records of any complaints or disputes for 6 years from the date the complaint was resolved.

If you want to know how long we keep a specific type of data, email us at [DPO EMAIL].

PLAIN ENGLISH FLAGS
Revised: 'We process your personal data on the basis of legitimate interests pursuant to Article 6(1)(f) of the UK GDPR' -> 'We use your data for fraud prevention because we have a legitimate business reason to do so, and we have assessed that this does not unfairly affect your rights.'
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
