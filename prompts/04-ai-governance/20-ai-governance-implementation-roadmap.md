# 20. AI Governance Implementation Roadmap

**Domain:** AI Governance
**Level:** Advanced

## Use Case

Design a phased, practical implementation roadmap for any AI governance framework - ISO 42001, NIST AI RMF, EU AI Act, or a custom AI governance programme. Produces a board-ready programme plan with phases, workstreams, milestones, resource requirements, and critical path. The deliverable that gets an AI governance programme funded and started.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[TARGET_FRAMEWORK]` | The framework or regulation being implemented | e.g. ISO 42001:2023 (target: certification in 18 months), EU AI Act (high-risk AI provider obligations by August 2026), NIST AI RMF 1.0 (voluntary adoption), Custom AI governance programme |
| `[ORGANISATION]` | Organisation name and type | e.g. Nationwide Building Society, UK mutual financial institution, 18,000 staff |
| `[CURRENT_MATURITY]` | Current AI governance maturity | e.g. No formal AI governance in place; ad-hoc AI deployments without oversight; existing ISO 27001 certification that can be leveraged; prior failed attempt at ISO 42001 implementation |
| `[AI_SYSTEMS_IN_SCOPE]` | AI systems the programme must cover | e.g. 7 AI systems in production (3 customer-facing, 4 internal); 2 under development; procurement pipeline includes 3 third-party AI tools |
| `[CONSTRAINTS]` | Key constraints on the programme | e.g. No dedicated AI governance headcount; CTO sponsor but no board mandate yet; budget of GBP 200k; must not disrupt live AI systems; target certification by Q4 2026 |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior AI governance programme director with 20 years of experience designing and delivering GRC transformation programmes for regulated organisations. You have led ISO 42001 implementations, EU AI Act readiness programmes, and AI governance framework builds from zero. Your roadmaps get funded, get delivered, and achieve their objectives.
</role>

<context>
Target framework: [TARGET_FRAMEWORK]
Organisation: [ORGANISATION]
Current maturity: [CURRENT_MATURITY]
AI systems in scope: [AI_SYSTEMS_IN_SCOPE]
Constraints: [CONSTRAINTS]
</context>

<instructions>
Design a complete, phased AI governance implementation roadmap.

Step 1: Programme Foundation Assessment
Based on the current maturity and constraints described, identify: the starting point (what exists that can be leveraged), the critical blockers (what must be resolved before implementation can progress), and the top three risks to programme delivery.

Step 2: Programme Architecture
Define 3-5 implementation phases. For each phase:
- Phase name and objective (what this phase achieves)
- Duration (realistic, given the constraints)
- Key workstreams within the phase
- Critical milestones and their completion criteria
- Dependencies (what must be complete before this phase starts)
- Resources required (roles, approximate effort in days, any specialist skills needed)
- Governance outputs (what documents, registers, or structures are produced)

Step 3: Workstream Detail
For the two most critical workstreams, provide a detailed activity list showing: the activity, who does it, estimated effort, and the output produced.

Step 4: Critical Path
Identify the sequence of activities that determines the earliest possible completion date. State which three activities, if delayed, would push back the programme completion date.

Step 5: Quick Wins
Identify three to five actions that can be completed in the first 30 days that will demonstrate progress to stakeholders and reduce risk before the full programme is underway.

Step 6: Resource and Budget Summary
A table showing total resource requirement by phase and a rough budget estimate by cost category (internal staff time, external consultants, tooling, certification body fees).
</instructions>

<output_format>
Present each step with a bold heading. Use tables for phase timelines and resource summaries. Write in British English. No em dashes. The roadmap must be realistic given the constraints described - do not produce an idealised programme that ignores the stated limitations. If a constraint makes a deadline unachievable, say so and state what would need to change.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The critical path identification is the element most implementation plans omit - and it is what programme sponsors most need to understand. The quick wins section is commercially essential: it gives the programme team something to show stakeholders in the first month, which maintains sponsorship through the harder middle phases. The 'if a constraint makes a deadline unachievable, say so' instruction prevents the most damaging type of implementation plan: one that promises what cannot be delivered.

## Sample Output Fragment

```
QUICK WINS (First 30 Days)

1. AI system inventory (Week 1-2): Conduct a structured survey of all departments to produce the first version of the AI system register. This satisfies ISO 42001 Clause 4.3 and EU AI Act classification requirements and creates the scope baseline the rest of the programme depends on. Effort: 3-5 days. Output: AI System Register v0.1.

2. Senior sponsor alignment (Week 1): Facilitate a 90-minute session with the CTO and at least one board member to confirm programme scope, risk appetite, and escalation authority. Without this, the programme will stall at the first contested decision. Output: Programme mandate document.

3. Regulatory deadline mapping (Week 2): Map all applicable regulatory deadlines (EU AI Act, sector-specific requirements) to a single calendar. This immediately prioritises the workstreams and gives the programme a credible urgency narrative for stakeholder engagement.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
