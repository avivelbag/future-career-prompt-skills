---
name: ai-incident-investigator
description: "Prompt playbook for an AI incident investigator. Use when an AI incident investigator wants help with work tasks such as: incident triage and severity; evidence preservation plan; timeline reconstruction; systemic causal analysis; reproduction test plan; regulator and internal report; plain-language public summary; incident pattern review; investigator upskilling plan."
---

# AI incident investigator prompts

Investigates failures and harms caused by deployed AI systems (wrong decisions, unsafe outputs, agent mishaps, misuse) for AI providers, deployers, insurers or regulators, much as NTSB or aviation safety investigators do for accidents. AI helps most with timeline reconstruction from logs, structuring causal analysis, mapping incidents to reporting obligations such as EU AI Act Article 73, and drafting clear reports for different audiences.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Incident triage and severity

**Task:** Classify a fresh AI incident report and decide immediate next steps

```text
You are an AI incident investigator at [ORGANIZATION / ROLE: provider, deployer, insurer]. A new report just came in: [PASTE REPORT, USER COMPLAINT OR ALERT]. The system involved is [SYSTEM, MODEL, USE CASE, DEPLOYMENT CONTEXT]. Produce a triage note with: (1) a one-paragraph factual summary separating confirmed facts from allegations; (2) a provisional harm classification (physical, financial, rights/discrimination, privacy, security, reputational) and severity using [INTERNAL SEVERITY SCALE, or propose a 4-level one]; (3) whether it could meet the EU AI Act Article 73 'serious incident' definition or other duties in [JURISDICTIONS], flagged as needing legal confirmation; (4) evidence to preserve now; (5) containment options. Mark every assumption.
```

> **Caution:** Reporting deadlines and legal thresholds must be confirmed by counsel; Claude's classification is provisional.

## 2. Evidence preservation plan

**Task:** Decide what logs, model versions and artifacts to freeze before they disappear

```text
Act as an AI forensics lead. We are investigating [INCIDENT SUMMARY] involving [SYSTEM ARCHITECTURE: model and version, prompts/system prompt, retrieval sources, tools/agents, guardrails, human-in-the-loop steps]. Our logging setup is [LOGGING / RETENTION DETAILS]. Write an evidence preservation checklist as a table: artifact, where it lives, why it matters causally, retention risk (will it be overwritten or rotated?), owner, and privacy or legal-hold notes. Include model weights or version pins, configuration and feature flags, prompt templates, retrieval index snapshots, tool-call traces, eval results before release, and change history. Note the EU AI Act Article 73 caution against altering the system in ways that hinder evaluation before authorities are informed, and list gaps where our logging would leave us blind.
```

> **Caution:** Personal data in logs stays subject to GDPR or other privacy law; involve your DPO before copying or sharing it.

## 3. Timeline reconstruction

**Task:** Turn raw logs and traces into a sequenced incident timeline

```text
You are helping me reconstruct the timeline of an AI incident. Below are [LOG EXCERPTS / AGENT TRACES / TICKETS / CHAT TRANSCRIPTS], with timestamps in [TIMEZONE(S)]. Build a chronological table with columns: time (normalized to UTC), actor (user, model, tool, human operator, automated system), event, source document and line, and confidence (confirmed / inferred). Then list: gaps where events are missing, contradictions between sources, the earliest point where the outcome could have been prevented, and questions I should ask witnesses or engineers. Do not fill gaps with guesses; label them clearly.

[PASTE DATA]
```

> **Caution:** Redact personal data and secrets before pasting logs; verify every inferred step against the source.

## 4. Systemic causal analysis

**Task:** Go beyond 'the model hallucinated' to contributing factors and control failures

```text
Act as a safety investigator trained in systems methods such as CAST/STPA and the Swiss cheese model. Incident: [SUMMARY AND TIMELINE]. Socio-technical context: [TRAINING / FINE-TUNING, GUARDRAILS, PRODUCT DESIGN, OPERATOR PROCEDURES, INCENTIVES, ORGANIZATIONAL FACTORS]. Produce: (1) the control structure as a list of controllers and feedback loops; (2) unsafe control actions or missing controls at each level, from model behavior up to management and procurement; (3) contributing factors ranked by evidence strength; (4) candidate root causes versus proximate triggers; (5) alternative hypotheses still not ruled out and the test that would discriminate each. Avoid blaming an individual where a design or process factor explains the behavior.
```

> **Caution:** Causal claims about model internals are often unverifiable; state what was actually tested.

## 5. Reproduction test plan

**Task:** Design controlled tests to reproduce and bound a model failure

```text
You are an AI evaluation engineer supporting an incident investigation. The suspected failure is [DESCRIBE BEHAVIOR, e.g. biased denial, unsafe instruction, tool misuse, prompt injection via retrieved document], seen in [SYSTEM / MODEL VERSION / SETTINGS]. Design a reproduction and scoping test plan: hypotheses, test cases including paraphrases and edge cases, controls, sampling settings and number of runs needed given non-determinism, metrics, pass/fail criteria, and how to check whether other versions or customers are affected. Reference relevant frameworks where useful (NIST AI RMF Measure function, OWASP Top 10 for LLM Applications, MITRE ATLAS). Output as a numbered plan plus a test-case table.
```

> **Caution:** Run reproduction in an isolated environment; do not re-expose real users or generate harmful content beyond what is needed to confirm the failure mode.

## 6. Regulator and internal report

**Task:** Draft the formal investigation report in a recognized structure

```text
Act as the lead author of an AI incident investigation report for [AUDIENCE: market surveillance authority / board / client / internal safety review]. Using my notes [PASTE FINDINGS, TIMELINE, CAUSES, ACTIONS], draft a report with sections: executive summary; system description and intended purpose; what happened; impact and affected parties; analysis and contributing factors; findings stated as numbered facts; corrective and preventive actions with owners and dates; open questions. Use neutral, non-speculative language modeled on NTSB/AAIB reports. Where [JURISDICTION] has a required format (e.g. EU AI Act Article 73 reporting, or a template from the national authority), list fields I still need to supply. Flag any statement that could be read as an admission of liability for legal review.
```

> **Caution:** Final report content and any legal admissions are the investigator's and counsel's responsibility, not Claude's.

## 7. Plain-language public summary

**Task:** Explain the incident to affected users or the public honestly

```text
You are a communications partner for an AI incident investigator. Rewrite the technical findings below as a public or affected-user notice for [AUDIENCE] at a [READING LEVEL] reading level, under [WORD LIMIT] words. It must say plainly what happened, who was affected and how, what we know versus are still investigating, what we have changed, what affected people can do (including how to appeal or contact a human), and when we will update next. No minimizing language, no blaming users, no jargon like 'hallucination' without explanation. Then list three questions journalists or affected people are likely to ask, with honest draft answers.

Findings: [PASTE]
```

> **Caution:** Coordinate with legal and any regulator before publishing; do not disclose exploit details that would enable copycat misuse.

## 8. Incident pattern review

**Task:** Spot trends across an incident register and compare to public databases

```text
Act as an AI risk analyst. Here is our incident register for [PERIOD]: [PASTE TABLE OR SUMMARIES: date, system, harm type, severity, root cause, status]. Analyze it for recurring failure modes, systems or teams with clusters, time-to-detect and time-to-close trends, and corrective actions that did not prevent recurrence. Map categories to a shared taxonomy such as the AI Incident Database / CSET taxonomy or the OECD AI Incidents Monitor so we can compare with public cases, and suggest which public incidents are analogous and worth reading. Output: key findings, a table of patterns, and five prioritized recommendations for our AI risk management system (e.g. under ISO/IEC 42001 or NIST AI RMF).
```

> **Caution:** Small incident counts make trends noisy; check suggested public incidents actually exist in the database before citing them.

## 9. Investigator upskilling plan

**Task:** Build a learning path for the skills this emerging role needs

```text
I am moving into AI incident investigation from [BACKGROUND, e.g. software QA, aviation safety, compliance, security IR]. I have [HOURS PER WEEK] for [MONTHS]. Create a learning plan covering: how modern ML and LLM agent systems fail; evaluation and red-teaming methods; safety investigation methods (STPA/CAST, human factors, just culture); security incident response (NIST SP 800-61) and its overlap with AI; governing frameworks (EU AI Act incident and post-market monitoring duties, NIST AI RMF and the Generative AI Profile, ISO/IEC 42001 and 23894); and report writing. For each module give goals, real reading or courses to look up, a hands-on exercise, and a self-check. Note which areas are still unsettled (e.g. regulator guidance, liability rules) and how to track them.
```

> **Caution:** Verify that each recommended course and document is current; AI regulation is changing quickly.
