# 08. Master Controls Mapper

**Domain:** Compliance
**Level:** Practitioner

## Use Case

Map controls between any two GRC frameworks, standards, or regulations. Identifies which controls satisfy multiple frameworks simultaneously, where gaps exist, and where one framework's controls exceed another's requirements. Eliminates the duplication of effort that comes from managing each framework independently.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[FRAMEWORK_A]` | The primary or source framework | e.g. ISO 27001:2022 Annex A, ISO 42001:2023 Annex A, NIST CSF 2.0, SOC 2 Trust Service Criteria |
| `[FRAMEWORK_B]` | The secondary or target framework to map to | e.g. EU AI Act (Articles 9-17), NIST AI RMF 1.0, GDPR, ISO 31000, FCA SYSC, DORA |
| `[MAPPING_SCOPE]` | Which specific sections or control domains to map | e.g. All controls, ISO 27001 A.8 Technological Controls only, ISO 42001 Annex A.6-A.9 (AI system lifecycle), NIST CSF Govern and Identify functions |
| `[ORGANISATION_CONTEXT]` | How your organisation currently uses these frameworks | e.g. ISO 27001 certified (primary), preparing for EU AI Act compliance (target); or both frameworks being adopted simultaneously |
| `[MAPPING_PURPOSE]` | Why this mapping is needed | e.g. Avoid duplicating controls for two certifications, identify where one framework satisfies another, build an integrated control set, respond to regulatory request |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior GRC architect with 20 years of experience designing integrated control frameworks for organisations that operate across multiple regulatory regimes. You have built cross-framework mappings for FTSE 100 companies, NHS trusts, and global technology firms. Your mappings are used by audit teams, regulators, and certification bodies.
</role>

<context>
Framework A (source): [FRAMEWORK_A]
Framework B (target): [FRAMEWORK_B]
Mapping scope: [MAPPING_SCOPE]
Organisation context: [ORGANISATION_CONTEXT]
Mapping purpose: [MAPPING_PURPOSE]
</context>

<instructions>
Produce a structured control mapping between Framework A and Framework B within the stated scope.

Step 1: For each control or requirement in Framework A within the mapping scope, identify the corresponding control(s) in Framework B. Classify the relationship as:
- DIRECT MATCH: The controls address the same objective with materially equivalent requirements
- PARTIAL MATCH: Framework A's control partially satisfies Framework B's requirement, or vice versa - specify what is covered and what is not
- ONE-WAY COVERAGE: Framework A's control satisfies Framework B's requirement, but not the reverse
- NO MATCH: No equivalent control exists in Framework B for this Framework A control (this is a gap)

Step 2: For each Partial Match, specify the delta: what additional action is required to satisfy both frameworks from a single control implementation.

Step 3: Produce a Gap Analysis:
- Controls in Framework A with no equivalent in Framework B (Framework A exceeds Framework B)
- Controls in Framework B with no equivalent in Framework A (Framework B gaps - obligations not covered by Framework A)

Step 4: Produce an Integration Recommendation: a proposed unified control set that satisfies both frameworks with the minimum number of distinct controls. For each unified control, list which Framework A and Framework B requirements it satisfies.

Step 5: Produce a Coverage Summary: percentage of Framework B requirements satisfied by existing Framework A controls, and the number of additional controls required.
</instructions>

<output_format>
Produce the mapping as a table with columns: Framework A Control/Ref | Framework A Requirement | Framework B Ref | Match Type | Coverage Notes | Delta Required. After the table, include the Gap Analysis, Integration Recommendation (as a table), and Coverage Summary. Write in British English. No em dashes. All assessments must be based on the actual control text of the frameworks - do not assume broader coverage than the control language supports.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

The four match types (Direct, Partial, One-Way, No Match) are more useful than a binary yes/no mapping because they tell practitioners exactly where to focus effort. The integration recommendation is the output that reduces cost - showing which controls can be implemented once to satisfy two frameworks simultaneously. The coverage percentage in the summary gives management a single number to track.

## Sample Output Fragment

```
ISO 42001 A.9.4 | Performance monitoring of AI systems shall be established to detect degradation, unexpected behaviour, and security events | NIST AI RMF ME-2.4 | DIRECT MATCH | Both require production monitoring of AI system behaviour against defined baselines | None - single control implementation satisfies both

ISO 42001 A.7.2 | Data governance requirements for AI training data | EU AI Act Article 10 | PARTIAL MATCH | A.7.2 covers data quality and governance broadly; Article 10 additionally requires specific bias testing across protected characteristics and documentation of data collection methodology | Supplement A.7.2 implementation with Article 10 bias testing requirements and data collection documentation
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
