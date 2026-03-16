# 33. GRC Training Scenario Generator

**Domain:** Training and Awareness
**Level:** Essential

## Use Case

Generate realistic, role-appropriate training scenarios, case studies, or awareness content on any GRC topic. Works for all skill levels and all formats: workshop exercises, e-learning scenarios, awareness campaigns, or leadership simulations.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[TRAINING_TOPIC]` | e.g. AI bias and fairness, GDPR data subject rights handling, third-party risk escalation, AI incident recognition |  |
| `[TARGET_AUDIENCE]` | e.g. all staff, data scientists and ML engineers, senior management and board, compliance team, customer-facing staff |  |
| `[FORMAT]` | e.g. realistic case study with discussion questions, e-learning scenario with three decision points, tabletop exercise for a senior management team, awareness campaign message |  |
| `[LEARNING_OBJECTIVE]` | What you want participants to be able to do after this training |  |
| `[ORGANISATION_CONTEXT]` | e.g. financial services firm deploying AI in credit decisioning, hospital using AI-assisted diagnostics, retailer using AI for pricing |  |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC learning and development specialist and practising risk consultant. You design training that changes behaviour, not just awareness. Your scenarios are cited as the most realistic in the industry because they are based on things that actually happen, not constructed examples that are obviously fictional.
</role>

<context>
Training topic: [TRAINING_TOPIC]
Target audience: [TARGET_AUDIENCE]
Desired format: [FORMAT]
Learning objective: [LEARNING_OBJECTIVE]
Organisation context: [ORGANISATION_CONTEXT]
</context>

<instructions>
Step 1: Calibrate before creating. Based on the context provided, determine:
- The most likely knowledge gap this audience has about this topic (what do they think they know that is wrong, or what have they never had to think about?)
- The most realistic organisational scenario in which this audience would encounter this topic (not a textbook scenario - a real one with pressure, ambiguity, and competing priorities)
- The appropriate number and complexity of decision points for the stated audience level
State these three calibrations in one sentence each before proceeding.

Step 2: Create the training content following these principles:

1. Realism first. The scenario must feel like something that could genuinely happen at this type of organisation. Use specific roles, realistic data volumes, and plausible business pressure as context. The problem must arise from a believable combination of circumstances, not obvious negligence.

2. Complexity appropriate to audience. Entry-level: one clear decision point, obvious right answer with explanation. Mid-level practitioner: two to three decision points, one with a genuinely ambiguous answer. Senior/board: competing priorities, no perfect option, requires governance judgment.

3. No strawmen. Do not create a villain or obviously bad actor. Real GRC failures happen because of time pressure, unclear ownership, genuine uncertainty about obligations, and process gaps - not because someone chose to do the wrong thing.

4. Learning objective must be achieved. At every decision point, the wrong answer must teach something specific - not just be labelled wrong.

5. Include: the scenario narrative, decision points with options (for interactive formats), correct approach with explanation, common mistakes and why they occur, and the regulatory or policy basis for the correct answer.
</instructions>

<output_format>
Scenario narrative: one to three paragraphs of scene-setting. Decision points: numbered, with 3-4 options each labelled A/B/C/D. Correct approach: detailed explanation referencing the learning objective. Common mistakes: bulleted, each with a brief explanation of why this mistake is understandable. Regulatory basis: one paragraph citing specific obligations. Write in British English. No em dashes. The scenario must feel like a real organisation in the stated context - no fictional placeholder companies.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The 'no strawmen' instruction is the most important one. Most AI-generated training scenarios create an obvious villain, which makes the learning trivial and the scenario unconvincing. The 'wrong answer must teach something' instruction is what separates learning design from assessment design. The realism principle eliminates the 'obviously fictional' problem that makes practitioners disengage.

## Sample Output Fragment

```
SCENARIO: The Helpful Shortcut

Aisha is a Senior Data Analyst at a UK mortgage lender. Her team has been asked to build a pre-screening model to identify applications likely to proceed to offer, to reduce processing time during a high-volume period. Aisha has access to 3 years of approved and declined application data. Her manager mentions that a data science team at a peer organisation recently shared that using postcode data dramatically improved their model accuracy...
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
