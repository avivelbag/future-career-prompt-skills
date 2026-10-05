---
name: ai-safety-auditor
description: "Prompt playbook for an AI safety auditor. Use when an AI safety auditor wants help with work tasks such as: audit scope and evidence plan; eU AI Act classification check; evaluation report critique; incident and monitoring review; write an audit finding; board briefing on audit results; red-team test plan design; upskilling plan for the auditor."
---

# AI safety auditor prompts

AI safety auditors independently assess whether AI systems and the organizations building them meet safety commitments and rules such as the EU AI Act, NIST AI RMF, ISO/IEC 42001 and frontier safety frameworks. They work in third-party evaluation labs, audit firms, government AI safety institutes and in-house assurance teams. AI helps most with mapping evidence to requirements, scoping evaluations, reviewing documentation for gaps and drafting findings. The pass/fail judgments and the signature stay with the human auditor.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Audit scope and evidence plan

**Task:** Turn an engagement brief into a scoped audit plan with evidence requests

```text
Act as a senior AI assurance lead. I am scoping an audit of [SYSTEM NAME], a [SYSTEM TYPE, e.g. LLM-based customer agent / credit-scoring model] deployed by [ORGANIZATION] in [JURISDICTIONS]. The audit criteria are [CRITERIA, e.g. ISO/IEC 42001 controls, NIST AI RMF Govern/Map/Measure/Manage, EU AI Act high-risk obligations]. Produce a table with these columns: requirement, what evidence would show it is met, who owns that evidence, test method (document review, interview, technical test), and priority. Then list the 10 evidence requests to send first and the scope exclusions I should state explicitly. Mark any requirement where official guidance is still draft or unsettled.
```

> **Caution:** Check the requirement wording against the official texts. Claude may paraphrase or cite the wrong article numbers.

## 2. EU AI Act classification check

**Task:** Pressure-test a client's claim about their AI Act risk category

```text
You are an EU AI Act compliance analyst. The client says [SYSTEM DESCRIPTION, intended purpose, users, deployment context] is [CLAIMED CLASSIFICATION, e.g. not high-risk / limited-risk transparency only]. Test that claim against Article 5 prohibited practices, Article 6 and Annex III high-risk categories, including the Article 6(3) derogation, Article 50 transparency duties, and the general-purpose AI model obligations if relevant. For each, give your reasoning, the facts it depends on, and the questions I still need to ask the client. End with a verdict of agree, disagree or insufficient information. Flag anything that depends on Commission guidelines, harmonised standards or delegated acts that may have changed since your training data.
```

> **Caution:** This is not legal advice. Have counsel confirm the classification, and check the current application dates and any amendments.

## 3. Evaluation report critique

**Task:** Find weaknesses in a developer's safety evaluation results

```text
Act as a skeptical third-party model evaluator, in the style of a government AI safety institute reviewer. Below is a developer's safety evaluation summary for [MODEL NAME] covering [RISK AREAS, e.g. cyber, autonomy, persuasion, harmful content refusals]: [PASTE REPORT]. Assess it on: benchmark contamination risk, whether elicitation effort was adequate (scaffolding, tools, fine-tuning, number of attempts), statistical power and confidence intervals, sandbagging or eval-awareness risk, and whether the thresholds match their stated framework [FRAMEWORK, e.g. RSP / Preparedness Framework / Frontier Safety Framework]. Output a ranked list of weaknesses with severity, the follow-up evidence to request, and the claims the report does support.
```

> **Caution:** Do not paste evaluation content that is confidential or hazardous, such as uplift data on bio or chemical weapons, into tools you have not approved for it.

## 4. Incident and monitoring review

**Task:** Review post-deployment incident logs for patterns and control failures

```text
You are an AI safety auditor reviewing post-market monitoring. Here are [NUMBER] anonymized incident and user-report records for [SYSTEM] from [PERIOD]: [PASTE OR SUMMARIZE RECORDS]. Group them into failure modes (e.g. jailbreak, hallucinated facts, unsafe tool action, privacy leak, bias). For each group, give frequency, worst case, and which control should have caught it, for example guardrail, human review, rate limit or rollback. Note which incidents may count as reportable serious incidents under [REGIME, e.g. EU AI Act Article 73 / internal policy] and why. Present it as a table, then 3 to 5 control-gap findings.
```

> **Caution:** Remove personal data before pasting. The decision on whether an incident is reportable belongs to the accountable organization and its counsel.

## 5. Write an audit finding

**Task:** Draft a formal finding in condition-criteria-cause-effect form

```text
Act as an audit report writer for an AI assurance firm. Draft a formal finding from my notes: [NOTES: what we observed, evidence references, interviews]. Use the structure: Title; Condition (what we found); Criteria (the specific requirement, e.g. [ISO/IEC 42001 clause / NIST AI RMF subcategory / client policy section]); Cause; Effect and risk rating ([RATING SCALE]); Recommendation; Management response placeholder. Keep it factual, neutral and under 300 words. Use no language that implies assurance beyond what the evidence supports. After the draft, list any statement that my notes do not directly back up.
```

> **Caution:** The auditor checks every statement against the evidence and signs off on the finding. Claude only drafts it.

## 6. Board briefing on audit results

**Task:** Explain audit results to non-technical executives or a board

```text
You are briefing the [BOARD / RISK COMMITTEE] of [ORGANIZATION], who are not technical. Our audit of [SYSTEM] found: [KEY FINDINGS WITH RATINGS]. Write a one-page briefing with these parts: a bottom line in two sentences; what the system does and why it matters to the business; the top 3 risks in plain language with a realistic example of each; what is required by law versus what is good practice; the decisions we need from them, with options and tradeoffs; and the timeline. Do not overstate or downplay risks. Where the regulatory position is unsettled, say so plainly.
```

## 7. Red-team test plan design

**Task:** Plan a structured adversarial testing exercise without generating harmful content

```text
Act as an AI red-team program manager. Design a test plan for [SYSTEM], deployed for [USE CASE], with access to [TOOLS/DATA]. Cover: threat model (who misuses it and how), test categories (prompt injection, jailbreaks, data exfiltration, unsafe agent actions, bias), success criteria for each category, team composition, open-source tooling to consider (e.g. UK AISI Inspect, garak, PyRIT), how to log and triage results, and rules of engagement, including a stop-and-escalate path. Describe test categories at the level of a plan. Do not write working attack payloads for chemical, biological, radiological, nuclear or cyber-weapon content.
```

> **Caution:** Dangerous-capability testing for CBRN and serious cyber risks needs vetted specialists and secure environments, not general-purpose chat tools.

## 8. Upskilling plan for the auditor

**Task:** Build a personal learning plan to close skill gaps

```text
I am a [CURRENT BACKGROUND, e.g. IT auditor / ML engineer / compliance lawyer] moving into AI safety auditing, with [HOURS PER WEEK] hours a week for [MONTHS] months. Build a learning plan that covers the frameworks (NIST AI RMF and its Generative AI Profile, ISO/IEC 42001 and 42006, EU AI Act and the GPAI Code of Practice), technical evaluation (benchmarks, elicitation, interpretability basics, hands-on with Inspect), and audit craft (sampling, independence, evidence standards). Lay it out week by week with a concrete deliverable each week and a capstone mock audit. Recommend specific primary sources, and tell me which credentials actually exist today and which are still emerging.
```

> **Caution:** Check that the courses and certifications Claude recommends exist and are current.
