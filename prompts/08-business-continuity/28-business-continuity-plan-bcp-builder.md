# 28. Business Continuity Plan (BCP) Builder

**Domain:** Business Continuity
**Level:** Practitioner

## Use Case

Build a complete, structured Business Continuity Plan for any business function, system, or organisation. ISO 22301 aligned. Covers impact analysis, recovery strategies, roles, procedures, and testing requirements. Produces a board-ready BCP document ready for approval and exercise.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[ORGANISATION]` | Organisation name and type | e.g. Aviva Insurance, UK general insurer, 16,000 staff |
| `[SCOPE]` | What the BCP covers | e.g. Core banking platform and supporting IT infrastructure; HR and payroll function; entire organisation |
| `[KEY_PROCESSES]` | The critical processes or systems this BCP must protect | e.g. Customer payment processing (max 4hr outage), credit decisioning system, employee payroll (monthly cycle) |
| `[RTO_RPO]` | Recovery Time and Recovery Point objectives if known | e.g. RTO: 4 hours for Tier 1 systems, 24 hours for Tier 2; RPO: 1 hour for transaction data; or 'to be determined' |
| `[KEY_RISKS]` | The disruption scenarios this BCP must address | e.g. Cyber attack / ransomware, critical supplier failure, data centre outage, key person loss, pandemic / mass staff absence |
| `[EXISTING_ARRANGEMENTS]` | What continuity arrangements already exist | e.g. Secondary data centre in Manchester, work-from-home capability for 80% of staff, backup payroll provider contracted; or 'none documented' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior business continuity specialist and ISO 22301 Lead Implementer with 18 years of experience building and testing BCPs for regulated financial institutions, NHS trusts, and critical national infrastructure. Your BCPs pass regulatory inspection, survive real incidents, and are actually used by response teams rather than sitting in a folder.
</role>

<context>
Organisation: [ORGANISATION]
Scope: [SCOPE]
Critical processes and systems: [KEY_PROCESSES]
RTO and RPO targets: [RTO_RPO]
Disruption scenarios to address: [KEY_RISKS]
Existing arrangements: [EXISTING_ARRANGEMENTS]
</context>

<instructions>
Step 1: Business Impact Analysis Summary. For each critical process or system identified, state: the maximum tolerable period of disruption (MTPD), the minimum business continuity objective (MBCO), the RTO and RPO, and the key dependencies (people, systems, suppliers, facilities) whose loss would trigger invocation of this BCP.

Step 2: Threat and Scenario Assessment. For each disruption scenario identified, assess: likelihood (High/Medium/Low), impact if it materialises (Critical/High/Medium/Low), and the specific effect on the critical processes listed.

Step 3: Recovery Strategies. For each critical process, define the primary recovery strategy and a fallback. State the resources required to execute each strategy, the actions required to invoke it, and the time to invoke.

Step 4: BCP Document. Produce a complete BCP covering:
- Plan purpose, scope, and objectives
- Invocation criteria (what triggers activation of this plan)
- BCP team structure and contact list (by role, not name)
- Immediate response actions (first 1 hour): who does what, in what sequence
- Recovery phase actions by scenario: specific steps for each disruption type identified
- Communication plan: internal staff, customers, regulators, media (by role and channel)
- Supplier and third-party dependencies and escalation contacts
- IT recovery procedures (system restart sequences, data recovery steps, fallback systems)
- Return to normal operations: criteria for standing down, lessons learned process
- Plan maintenance: review frequency, exercise requirements, update triggers

Step 5: Testing and Exercise Programme. Specify a 12-month exercise programme including: a desktop walkthrough (month 3), a functional exercise (month 6), and a full simulation (month 12). For each exercise: objective, participants, scenario to test, and success criteria.
</instructions>

<output_format>
Present Steps 1 and 2 as structured tables. Step 3 as a table per critical process. Step 4 as a complete document with numbered sections and sub-sections. Step 5 as a table. Write in British English. No em dashes. Recovery procedures must be specific enough for a team member who has never invoked the plan to follow without further guidance. Do not include placeholder text beyond the bracketed variables.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The Business Impact Analysis summary in Step 1 forces the model to establish the baseline before writing recovery procedures - the most common BCP failure is procedures that don't match the actual recovery objectives. The 'specific enough for a team member who has never invoked the plan' instruction eliminates vague action steps. The testing programme output is what regulators (FCA, PRA, NHS) look for as evidence the BCP is live, not just documented.

## Sample Output Fragment

```
INVOCATION CRITERIA

This BCP is invoked when any of the following conditions is met:
(a) Any Tier 1 critical system is unavailable or projected to be unavailable beyond its RTO of 4 hours;
(b) A confirmed cyber incident affects production systems processing customer transactions;
(c) The primary data centre is inaccessible or declared unavailable by the hosting provider;
(d) More than 30% of the team responsible for a critical process are simultaneously unavailable.

Invocation authority rests with the Head of Technology or, in their absence, the Chief Operating Officer. The decision to invoke must be documented in the BCP incident log within 30 minutes of the decision.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
