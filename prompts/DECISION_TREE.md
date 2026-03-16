# When to Use What: GRC Prompt Decision Guide

Not sure which prompt to use? Find your situation below.

---

## Risk Management

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Build a risk register for an AI system or project | [01 - AI Risk Register Builder](01-risk-management/01-ai-risk-register-builder.md) | Structured RAG-scored register with owners and treatment plan |
| Conduct a formal operational or project risk assessment | [02 - Operational Risk Assessment](01-risk-management/02-operational-risk-assessment.md) | Full assessment with inherent/residual scoring and go/no-go disposition |
| Turn risk findings into an actionable remediation plan | [03 - Remediation Plan Builder](01-risk-management/03-remediation-plan-builder.md) | Groups by root cause, assigns owners, evidence-of-completion standard |
| Quantify risk in financial terms for a board or insurer | [04 - Quantitative Risk Modelling (FAIR)](01-risk-management/04-quantitative-risk-modelling-fair.md) | FAIR-aligned model with loss ranges and sensitivity analysis |

---

## Compliance

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Assess gaps against a regulation or standard | [05 - Regulatory Gap Analysis](02-compliance/05-regulatory-gap-analysis.md) | Parses obligations first, maps current state, flags ambiguous requirements |
| Map a regulation to your existing controls | [06 - Regulatory Obligation Mapper](02-compliance/06-regulatory-obligation-mapper.md) | Identifies covered, partial, and unaddressed obligations |
| Prepare a DPIA for a new processing activity or AI system | [07 - DPIA Writer](02-compliance/07-dpia-writer.md) | Necessity and proportionality analysis, risk identification, DPO record |
| Map controls between two frameworks | [08 - Master Controls Mapper](02-compliance/08-master-controls-mapper.md) | Four match types with integration recommendation to reduce duplication |
| Draft a GDPR privacy notice or consent mechanism | [09 - Privacy Notice Drafter](02-compliance/09-privacy-notice-drafter.md) | All Article 13/14 content with plain English assessment |

---

## Audit and Assurance

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Write up an audit finding professionally | [10 - Audit Finding Writer](03-audit-and-assurance/10-audit-finding-and-recommendation-writer.md) | CCCER structure, root cause decomposition, do-not-soften instruction |
| Design a control and write its test script | [11 - Control Design and Test Script](03-audit-and-assurance/11-control-design-and-test-script-writer.md) | Separates design from testing - two testers reach the same result |
| Build a compliance evidence checklist before an audit | [12 - Evidence Checklist Generator](03-audit-and-assurance/12-compliance-evidence-checklist-generator.md) | What to gather, where to find it, what auditor looks for |
| Send a self-assessment questionnaire to a control owner | [13 - CSA Questionnaire](03-audit-and-assurance/13-control-self-assessment-csa-questionnaire.md) | Existence, operation, effectiveness questions with HIGH RISK flags |
| Design a tabletop exercise | [14 - Tabletop Exercise Guide](03-audit-and-assurance/14-tabletop-exercise-facilitator-guide.md) | Full facilitator guide with injects, evaluation criteria, debrief |

---

## AI Governance

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Draft an AI governance or acceptable use policy | [15 - AI Policy Drafter](04-ai-governance/15-ai-policy-drafter.md) | Correct section structure for the AI policy type, framework-cited throughout |
| Explain an AI system to non-technical users or regulators | [16 - XAI Translator](04-ai-governance/16-ai-explainability-xai-translator.md) | Transparency statement plus Article 13 technical summary |
| Find Shadow AI (unauthorised LLM use) in a department | [17 - Shadow AI Discovery Interviewer](04-ai-governance/17-shadow-ai-discovery-interviewer.md) | Task-based interview guide - surfaces AI use without defensiveness |
| Audit training data for quality and copyright | [18 - Data Lineage and Provenance Auditor](04-ai-governance/18-data-lineage-and-provenance-auditor.md) | Six dimensions: provenance, representativeness, quality, copyright, bias |
| Design a human-in-the-loop oversight workflow | [19 - HITL Workflow Architect](04-ai-governance/19-human-in-the-loop-hitl-workflow-archite.md) | Tier model, override protocol, audit trail - ISO 42001 A.9.2 |
| Build an AI governance implementation roadmap | [20 - AI Governance Roadmap](04-ai-governance/20-ai-governance-implementation-roadmap.md) | Phased programme, critical path, quick wins - realistic against constraints |

---

## Information Security

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Assess ISO 27001:2022 gaps or prepare for certification | [21 - ISO 27001 Control Gap Assessor](05-information-security/21-iso-27001-control-gap-assessor.md) | Four-theme structure, 2022 transition flags, certification readiness assessment |
| Write a formal cyber security incident report | [27 - Cyber Security Incident Report Writer](07-incident-response/27-cyber-security-incident-report-writer.md) | Raw incident timeline to board-ready report with Five Whys root cause |

---

## Third-Party Risk

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Assess a new AI vendor before onboarding | [22 - AI Vendor Risk Assessment](06-third-party-risk/22-ai-vendor-risk-assessment.md) | Tier-calibrated: Tier 1 gets all 7 domains, Tier 3 gets core 4 only |
| Get specific contract clauses for a supplier agreement | [23 - Supplier Contract Clause Generator](06-third-party-risk/23-supplier-contract-clause-generator.md) | Preferred clause plus fallback - covers AI model change notifications |
| Conduct a periodic review of an existing supplier | [24 - Third-Party Ongoing Monitoring](06-third-party-risk/24-third-party-ongoing-monitoring-and-revi.md) | Change impact assessment, paper vs real remediation check |
| Send a due diligence questionnaire to a supplier | [25 - DDQ Builder](06-third-party-risk/25-third-party-due-diligence-questionnaire-.md) | Calibrated DDQ with HIGH RISK flags and evidence requirements |

---

## Incident Response

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Build an AI incident response playbook | [26 - AI Incident Response Playbook](07-incident-response/26-ai-incident-response-playbook.md) | 7-phase structure, IF/THEN decision points, Summary Response Card |
| Write a formal cyber security incident report | [27 - Cyber Security Incident Report Writer](07-incident-response/27-cyber-security-incident-report-writer.md) | Raw timeline to board-ready report with Five Whys root cause |

---

## Business Continuity

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Build a Business Continuity Plan for any function or system | [28 - BCP Builder](08-business-continuity/28-business-continuity-plan-bcp-builder.md) | ISO 22301 aligned, BIA, recovery strategies, 12-month exercise programme |

---

## Board Reporting

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Prepare a board paper on AI risk or regulation | [29 - AI Governance Board Briefing](09-board-reporting/29-ai-governance-board-briefing.md) | Purpose-first structure, options table, specific decisions required |
| Write a quarterly risk and compliance committee report | [30 - Committee Report](09-board-reporting/30-risk-and-compliance-committee-report.md) | RAG status, 150-word exec summary limit, metric-based risk position |

---

## Policy Writing

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Draft any policy (AUP, Change Management, Data Retention, etc.) | [31 - Universal Policy Maker](10-policy-writing/31-universal-policy-maker.md) | Any policy type, org-specific, production-ready, board-approvable |
| Write a job description for a GRC role | [32 - GRC Job Description Writer](10-policy-writing/32-grc-job-description-writer.md) | Market-calibrated, verb-led responsibilities, with interview questions |

---

## Training and Awareness

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Create GRC training scenarios or case studies | [33 - Training Scenario Generator](11-training-and-awareness/33-grc-training-scenario-generator.md) | No strawmen - realistic scenarios where wrong answers teach something |
| Assess AI literacy across the workforce | [34 - AI Literacy Assessment Generator](11-training-and-awareness/34-ai-literacy-assessment-generator.md) | 30% of questions test escalation and error-flagging, not just recall |

---

## Implementation

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Get help with a framework at any stage | [35 - Framework Implementation Assistant](12-implementation/35-framework-implementation-assistant.md) | Any framework, any blocker - diagnoses before advising |
| Get expert mentoring when stuck | [36 - GRC Implementation Mentor](12-implementation/36-grc-implementation-mentor-conversationa.md) | Socratic guidance that builds capability rather than just giving answers |
| Get a specific implementation deliverable produced now | [37 - GRC Implementation Consultant](12-implementation/37-grc-implementation-consultant-deliverab.md) | Produces the actual finished document, not guidance on how to write it |

---

## Career and Development

> No other GRC prompt library has these.

| When you need to... | Use Prompt | Why |
|---------------------|-----------|-----|
| Get a study plan for a GRC certification | [38 - Certification Study Plan Builder](13-career-and-development/38-grc-certification-study-plan-builder.md) | Exam intelligence, gap analysis, week-by-week plan for real hours available |
| Plan your GRC career progression | [39 - Career Pathway Advisor](13-career-and-development/39-grc-career-pathway-advisor.md) | Honest gap assessment, phased roadmap, 90-day immediate actions |
| Prepare for a GRC interview | [40 - Interview Preparation Coach](13-career-and-development/40-grc-interview-preparation-coach.md) | Anticipated questions, model answers, specific concern coaching |
| Get practice questions for a certification exam | [41 - Certification Exam Simulator](13-career-and-development/41-grc-certification-exam-simulator.md) | Exam-standard questions with why-wrong explanations for each distractor |
| Write your professional development plan | [42 - PDP Writer](13-career-and-development/42-grc-professional-development-plan-pdp-w.md) | Genuinely SMART objectives with evidence standard for appraisal |
| Get salary or market positioning advice | [43 - Salary and Market Positioning Analyser](13-career-and-development/43-grc-salary-and-market-positioning-analy.md) | Percentile ranges, negotiation strategy, alternative levers |
| Build a GRC resume that gets past ATS screening | [44 - Resume Architect (ATS Killer)](13-career-and-development/44-grc-resume-architect-ats-killer.md) | JD deconstruction, keyword injection, impact-led achievement bullets |
| Start a GRC company or consultancy | [45 - Company and Startup Founder Mentor](13-career-and-development/45-grc-company-and-startup-founder-mentor.md) | Founder diagnostic, market stress-tests, ideation engine, pricing strategy |

---

*Back to [README](../README.md)*
