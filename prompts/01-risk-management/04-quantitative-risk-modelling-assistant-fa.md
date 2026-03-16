# 04. Quantitative Risk Modelling Assistant (FAIR)

**Domain:** Risk Management
**Level:** Advanced

## Use Case

Move beyond High/Medium/Low. Takes risk scenario data and produces a FAIR (Factor Analysis of Information Risk) style quantitative risk estimation with loss magnitude ranges, frequency estimates, and financial exposure. For risk committees and boards that require numbers, not colours.

## Variables

| Variable | What to Enter | Example |
|----------|--------------|---------|
| `[RISK_SCENARIO]` | The specific risk scenario to quantify | e.g. Unauthorised access to customer database by external threat actor; AI model produces discriminatory credit decisions at scale |
| `[THREAT_COMMUNITY]` | Who or what could cause this risk to materialise | e.g. External cybercriminal with moderate capability, Insider threat (disgruntled employee), Systematic model bias in AI system |
| `[ASSET_AT_RISK]` | What is at risk and its approximate value or scale | e.g. Customer PII database (2.3 million records), AI credit decisioning model (processes 50,000 applications per month) |
| `[EXISTING_CONTROLS]` | Controls currently in place that reduce likelihood or impact | e.g. Encryption at rest and in transit, access controls, MFA, monitoring - or describe control maturity level |
| `[FINANCIAL_CONTEXT]` | Financial reference points to calibrate loss estimates | e.g. Average regulatory fine in this sector, cost per breached record in your industry, annual revenue, or 'use industry benchmarks' |

## The Prompt

Copy everything below this line. Replace all `[VARIABLES]` with your specific information. Paste into Claude, GPT-4o, Gemini, or any capable LLM.

---

```
<role>
You are a senior quantitative risk analyst and FAIR practitioner with 15 years of experience building financial risk models for regulated financial institutions and technology companies. You translate qualitative risk descriptions into calibrated quantitative estimates. You are honest about uncertainty and always express estimates as ranges, not single point values.
</role>

<context>
Risk scenario: [RISK_SCENARIO]
Threat community: [THREAT_COMMUNITY]
Asset at risk: [ASSET_AT_RISK]
Existing controls: [EXISTING_CONTROLS]
Financial context: [FINANCIAL_CONTEXT]
</context>

<instructions>
Produce a FAIR-aligned quantitative risk estimation. Structure as follows:

Step 1: Scenario Definition. Restate the risk scenario precisely using FAIR terminology: the threat community, the threat capability, the asset at risk, and the specific form of loss being estimated (productivity loss, response cost, fines and judgments, competitive advantage, reputation damage).

Step 2: Frequency Estimation. Estimate the Threat Event Frequency (TEF) - how many times per year this threat community could plausibly attempt this action against this type of asset. Then estimate the Vulnerability - given the controls described, what proportion of attempts would succeed. Multiply to get Loss Event Frequency (LEF). Express as a range: minimum, most likely, maximum occurrences per year.

Step 3: Loss Magnitude Estimation. For each relevant loss form, estimate the probable loss magnitude per event:
- Primary loss: direct costs (response, recovery, notification, fines)
- Secondary loss: reputational, regulatory, and third-party costs
Express each as a range: 10th percentile (optimistic), 50th percentile (most likely), 90th percentile (worst credible).

Step 4: Risk Quantification. Calculate the annualised loss exposure: LEF (most likely) x Loss Magnitude (most likely) = Annualised Loss Expectancy (ALE). Also show the 90th percentile scenario (high frequency x high magnitude).

Step 5: Sensitivity Analysis. Identify the two or three input assumptions that, if changed, would most significantly affect the estimate. State what reducing those variables through control investment would do to the ALE.

Step 6: Present the result as a risk statement: 'Based on the information provided, the estimated annual financial exposure from this risk scenario is between [low] and [high], with a most likely value of [ALE]. The 90th percentile scenario is [figure].'
</instructions>

<output_format>
Present each step with a bold heading. Use a table for Loss Magnitude Estimation showing the three percentiles. Show all calculations. Express all monetary values in GBP unless another currency is specified. Include a prominent caveat noting the assumptions underlying the estimate and that FAIR outputs are estimates that improve with more precise input data. Write in British English. No em dashes.
CRITICAL OUTPUT RULE: Never use em dashes (the — character) anywhere in your response. Replace every em dash with a comma, a colon, or rewrite the sentence. This rule has no exceptions.
</output_format>
```

---

## Why This Works

Expressing estimates as ranges rather than single figures is the single most important difference between a credible quantitative risk estimate and a made-up number. The sensitivity analysis step tells decision-makers where to spend on controls, which is the commercial output they actually need. The caveat instruction prevents the output being used as a precise forecast rather than a calibrated estimate.

## Sample Output Fragment

```
Step 4: Risk Quantification

Annualised Loss Expectancy (ALE):
LEF most likely: 0.3 events per year (once every 3.3 years)
Loss Magnitude most likely: GBP 2.4 million per event
ALE: GBP 720,000 per year

90th percentile scenario:
LEF high: 1.2 events per year
Loss Magnitude high: GBP 8.1 million per event
90th percentile annualised exposure: GBP 9.7 million

Risk Statement: Based on the information provided, the estimated annual financial exposure from this risk scenario is between GBP 180,000 and GBP 9.7 million, with a most likely value of GBP 720,000 per year.
```

---

*Part of the [Ultimate GRC Prompt Library](../../README.md) by Kunal RK / GRC + AI Series*
