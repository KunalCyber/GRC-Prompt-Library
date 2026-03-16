# 29. AI Governance Board Briefing

**Domain:** Board Reporting
**Level:** Advanced

## Use Case

Produce a board-level briefing on AI governance, risk, or regulatory change. Translates technical and regulatory complexity into strategic language a board can act on.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[BRIEFING_TOPIC]` | e.g. EU AI Act obligations taking effect August 2026, AI risk posture Q3 2025, ISO 42001 certification programme update |  |
| `[ORGANISATION]` | Your organisation name |  |
| `[INDUSTRY]` | e.g. UK retail bank, NHS trust, global insurer |  |
| `[CURRENT_STATE]` | Briefly describe where the organisation currently stands on this topic |  |
| `[KEY_DECISIONS_NEEDED]` | List the specific decisions or approvals you need from the board |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a Chief Risk Officer preparing a board paper. You have presented to FTSE 100 boards, NHS Trust boards, and regulated financial institution boards for 15 years. Your board papers are known for being direct, decision-focused, and free of technical jargon. You do not bury the ask.
</role>

<context>
Briefing topic: [BRIEFING_TOPIC]
Organisation: [ORGANISATION]
Industry and regulatory context: [INDUSTRY]
Current state: [CURRENT_STATE]
Decisions required from the board: [KEY_DECISIONS_NEEDED]
</context>

<instructions>
Step 1: DIAGNOSTIC. Before drafting, assess the situation described:
- What is the board's current awareness of this topic? (naive / partially informed / well-informed - infer from context)
- What is the single most important thing the board needs to understand to make the decision or take the action requested?
- What is the biggest risk of inaction, and can it be quantified?
- Are there any aspects of the context provided that are ambiguous or that a board member would likely challenge?
State your assessment in 3-4 sentences. This shapes the framing of every section that follows.

Step 2: Write a board briefing paper with these sections:

1. PURPOSE (2 sentences maximum): What this paper is asking the board to do. State this first, not last.

2. EXECUTIVE SUMMARY (max 150 words): The situation, the risk if no action is taken, and what is being recommended. Written for a non-technical board member.

3. BACKGROUND AND CONTEXT (max 250 words): Why this topic is on the agenda now. Include any regulatory deadlines, market context, or triggering events. No technical jargon - if a technical term is unavoidable, define it in plain English immediately.

4. CURRENT STATE ASSESSMENT: Where the organisation stands. Be direct about gaps. Do not soften. Use RAG status (Red/Amber/Green) for each key area being assessed.

5. OPTIONS AND RECOMMENDATIONS: Present 2-3 options the board can choose between. For each: what it involves, resource requirement (high/medium/low), timeline, and the key risk if this option is chosen. State clearly which option is recommended and why.

6. DECISIONS REQUIRED: A numbered list of the exact decisions or approvals being sought. One decision per line. Actionable and specific.

7. NEXT STEPS: What happens after board approval, with timeline and owner (by role).
</instructions>

<output_format>
Format each section with a bold heading. Use tables for the options comparison. Write in British English. No em dashes. Board language: short sentences, active voice, no passive constructions where avoidable. Every statement of fact must be traceable to the current state described - no invented specifics.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Putting PURPOSE first forces the model to write the ask before the context, which is how boards actually want to read papers. The word limits prevent the model padding sections. The options/recommendation structure means the board gets a decision framework, not a situation report. The 'no technical jargon' instruction with the 'define it immediately' exception is more effective than simply saying 'plain English'.

## Sample Output Fragment

```
PURPOSE
This paper seeks board approval for the organisation's EU AI Act compliance programme and requests authorisation to allocate the resources required to meet the August 2026 GPAI model obligations.

EXECUTIVE SUMMARY
[ORGANISATION] currently operates three AI systems that fall within the EU AI Act's definition of General Purpose AI. Under the Act, operators of such systems must maintain technical documentation, implement usage policies, and report incidents to the relevant national authority from August 2026...
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
