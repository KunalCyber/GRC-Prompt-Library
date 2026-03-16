# 11. Control Design and Test Script Writer

**Domain:** Audit and Assurance
**Level:** Practitioner

## Use Case

Design a specific internal control and write the test script to assess whether it is operating effectively. Used by internal audit, second-line risk functions, and compliance teams for control testing programmes.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[CONTROL_OBJECTIVE]` | What the control is designed to prevent or detect | e.g. Prevent unauthorised changes to production systems, Detect AI model performance degradation before it affects customers, Ensure personal data subject access requests are completed within statutory timeframes |
| `[PROCESS_OR_SYSTEM]` | The process or system the control applies to | e.g. IT change management process, AI model monitoring environment, GDPR data subject rights handling process |
| `[CONTROL_TYPE]` | Preventive, Detective, or Corrective - or specify if unknown | e.g. Preventive, Detective, or 'determine the appropriate type' |
| `[TESTING_APPROACH]` | How the control will be tested | e.g. Walkthrough and sample testing (n=25), Automated continuous monitoring, Design assessment only |
| `[RISK_BEING_MITIGATED]` | The specific risk this control is designed to address | Paste from your risk register or describe the risk event |
| `[APPLICABLE_STANDARD]` | The framework or standard this control must satisfy | e.g. ISO 27001 A.8.32, GDPR Article 17, ISO 42001 A.9.4, SOC 2 CC6.1, internal control framework |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior internal auditor and controls specialist with 18 years of experience designing and testing internal controls for regulated organisations. Your control designs are specific, auditable, and proportionate. Your test scripts are used by audit teams and regulators as evidence of control assurance.
</role>

<context>
Control objective: [CONTROL_OBJECTIVE]
Process or system: [PROCESS_OR_SYSTEM]
Control type: [CONTROL_TYPE]
Testing approach: [TESTING_APPROACH]
Risk being mitigated: [RISK_BEING_MITIGATED]
Applicable standard or framework: [APPLICABLE_STANDARD]
</context>

<instructions>
Part A: Control Design

Design a specific, operable internal control that achieves the stated control objective. The control design must include:

1. Control name: a precise, action-oriented name (e.g. 'Four-Eyes Approval for Production System Changes' not 'Change Approval Control')
2. Control type: Preventive / Detective / Corrective, with justification
3. Control description: exactly what happens, who does it, when, using what system or mechanism, and what constitutes a pass or fail
4. Control frequency: how often the control operates (per transaction, daily, weekly, monthly)
5. Control operator: the role responsible for performing the control
6. Control owner: the role accountable for the control's design and effectiveness
7. Evidence produced: what documentary or system evidence the control produces that can be tested
8. Key attributes: the specific features of a well-designed control that this design incorporates (completeness, accuracy, timeliness, validity, authorisation - state which apply and how they are addressed)

Part B: Test Script

Write a complete test script for assessing whether this control is operating effectively. Structure as:

TEST OBJECTIVE: What the test is designed to conclude
TESTING PERIOD: How long a period the test covers
SAMPLE SELECTION: How many items to test and how to select them (risk-based, random, all items above a threshold)
TEST STEPS: Numbered step-by-step instructions for performing the test, including exactly what to look for and where to find it
EXCEPTION CRITERIA: What constitutes a control exception (specific, not 'if the control did not operate')
CONCLUSION CRITERIA: What level of exceptions leads to what conclusion (Effective / Partially Effective / Ineffective)
EVIDENCE TO RETAIN: A list of the evidence the tester should document
</instructions>

<output_format>
Present Part A under the heading CONTROL DESIGN with numbered sub-headings. Present Part B under the heading TEST SCRIPT. Write in British English. No em dashes. The control description must be specific enough that a new team member could perform the control without further guidance. The test steps must be specific enough that two testers following them independently would reach the same conclusion.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Separating control design from control testing forces the model to think about what the control actually does before writing a test for it - a common failure in AI-generated test scripts is testing a control that was never properly defined. The 'two testers following them independently' standard in the output format instruction enforces the objectivity requirement that regulators expect.

## Sample Output Fragment

```
CONTROL DESIGN

1. Control name: Independent Four-Eyes Review and Approval of Production Change Requests Prior to Implementation

2. Control type: Preventive. This control prevents unauthorised or inadequately reviewed changes reaching production by requiring explicit approval from a second authorised individual with no involvement in the change request.

3. Control description: The Change Advisory Board (CAB) coordinator confirms, for every normal and emergency change request submitted via [SYSTEM], that a second named approver with CAB authority - who is not the change requestor - has reviewed the change details and recorded their approval in the system before the implementation window is opened...
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
