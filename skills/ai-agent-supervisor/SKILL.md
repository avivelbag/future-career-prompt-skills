---
name: ai-agent-supervisor
description: "Prompt playbook for an AI agent supervisor. Use when an AI agent supervisor wants help with work tasks such as: agent trace triage; shift oversight dashboard review; approval and escalation policy; agent incident report; prompt injection and misuse red-team plan; explaining an agent decision to a customer; evaluation suite for a new agent version; supervisor upskilling plan."
---

# AI agent supervisor prompts

Oversees fleets of autonomous AI agents doing real work (support tickets, coding, back-office ops), approving high-risk actions, triaging failures and owning the human-oversight duties that frameworks like EU AI Act Article 14 and the NIST AI RMF describe. Claude helps most with reading agent traces, drafting escalation and approval rules, writing incident reports and keeping oversight documentation audit-ready.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Agent trace triage

**Task:** Diagnose why an agent run went wrong from its logs

```text
You are a senior AI agent supervisor reviewing a failed or suspicious agent run. Below is the trace (prompts, tool calls, tool outputs, final answer) from [AGENT NAME / FRAMEWORK, e.g. LangGraph, OpenAI Agents SDK, Claude Agent SDK] doing [TASK]. Expected outcome: [EXPECTED]. Actual outcome: [ACTUAL]. Trace: [PASTE TRACE]. Identify the first step where the run diverged, classify the root cause (bad instructions, tool error, hallucinated argument, retrieval gap, prompt injection in tool output, loop/timeout, permission issue), quote the evidence, and give a severity (low/med/high). Output a table: step | what happened | why it matters, then 3 concrete fixes ranked by effort. Say clearly where the trace is insufficient to be sure.
```

> **Caution:** Redact customer PII and secrets from traces before pasting them.

## 2. Shift oversight dashboard review

**Task:** Summarize a shift's agent metrics and flag anomalies

```text
Act as an operations analyst for a team supervising [NUMBER] AI agents handling [WORKLOAD, e.g. tier-1 billing tickets]. Here are this shift's metrics in CSV: [PASTE: agent_id, tasks, success rate, human escalations, overrides, avg cost, avg latency, tool errors]. Baseline from last 4 weeks: [PASTE BASELINE]. Flag agents or metrics that deviate meaningfully from baseline, suggest likely causes, and separate 'needs action this shift' from 'watch'. Output: a 5-line handoff summary for the next supervisor, then a bullet list of flagged items with the metric, the deviation, and a recommended check. Do not over-interpret small samples; note sample size where relevant.
```

## 3. Approval and escalation policy

**Task:** Draft rules for which agent actions need human sign-off

```text
You are helping an AI agent supervisor design a human-in-the-loop policy. Our agents can take these actions: [LIST TOOLS/ACTIONS, e.g. issue refunds, send external email, merge code, change user permissions]. Business context: [INDUSTRY, RISK TOLERANCE, VOLUMES]. Draft a tiered policy: (1) actions agents may take autonomously, (2) actions requiring human approval before execution, (3) actions prohibited, with thresholds (e.g. dollar amounts, data sensitivity, reversibility). For each tier give the rationale, the logging requirement, and an override/kill-switch procedure. Reference how this supports human-oversight expectations in EU AI Act Article 14 and the NIST AI RMF 'Govern' and 'Manage' functions, and flag where our use may or may not be high-risk under the Act.
```

> **Caution:** Whether a system is high-risk under the EU AI Act is a legal determination; confirm with counsel.

## 4. Agent incident report

**Task:** Write a blameless post-incident report after an agent caused harm

```text
Act as an incident response writer. An AI agent [AGENT/ROLE] did [WHAT HAPPENED] on [DATE], affecting [WHO/WHAT, SCALE]. Timeline notes: [PASTE NOTES]. Detection method: [HOW IT WAS CAUGHT]. Containment steps taken: [STEPS]. Write a blameless post-incident review with sections: summary, impact, timeline (UTC), root cause and contributing factors (including oversight gaps, not just model behavior), what went well, action items with owners and due dates as placeholders, and whether this may be reportable (e.g. a 'serious incident' under EU AI Act Article 73, GDPR breach notification, sector regulators). Mark any reporting question as needing legal confirmation rather than deciding it.
```

> **Caution:** Regulatory reporting deadlines can be short; involve legal/compliance immediately, not after the write-up.

## 5. Prompt injection and misuse red-team plan

**Task:** Plan adversarial tests before giving agents a new tool

```text
You are a security-minded AI agent supervisor preparing to give our agent access to [NEW TOOL / DATA SOURCE, e.g. inbound email, web browsing, a payments API]. Agent purpose: [PURPOSE]. Using the OWASP Top 10 for LLM Applications and MITRE ATLAS as frameworks, list the most relevant threats (e.g. indirect prompt injection, excessive agency, sensitive data disclosure, insecure output handling). For each, give 2 concrete test scenarios we can run in a sandbox, the expected safe behavior, and a mitigation (least-privilege scopes, allowlists, output validation, approval gates). Output as a table plus a go/no-go checklist for launch.
```

> **Caution:** Run tests only in sandboxed environments against systems you own or are authorized to test.

## 6. Explaining an agent decision to a customer

**Task:** Draft a plain-language explanation and remedy for an affected person

```text
You are writing on behalf of [COMPANY] to a customer affected by a decision or action taken by an AI agent. What happened: [DESCRIPTION]. Outcome for the customer: [IMPACT]. Human review result: [WHAT THE SUPERVISOR CONCLUDED]. Remedy offered: [REMEDY]. Write a clear, honest message (150-220 words) at a grade-8 reading level that: discloses that an automated system was involved, explains the main reasons for the outcome without jargon, states what a human reviewed and decided, explains how to contest or appeal, and avoids admitting legal liability beyond the facts. Then give a 2-line internal note on anything the message should not promise.
```

> **Caution:** Have customer-facing messages about errors reviewed by legal or support leads before sending.

## 7. Evaluation suite for a new agent version

**Task:** Design regression and acceptance tests before rollout

```text
Act as an evaluation lead. We are upgrading [AGENT] from [OLD MODEL/PROMPT VERSION] to [NEW VERSION]. It performs [TASKS]. Past failure modes: [LIST]. Design an evaluation plan: (1) a golden test set structure with categories and approximate counts, (2) scoring method for each category (exact match, rubric graded by humans, LLM-as-judge with spot-check rate), (3) safety and policy tests, (4) cost and latency budgets, (5) rollout plan (shadow mode, canary percentage, rollback trigger). Output as a numbered plan with a one-page acceptance criteria table. Note the known weaknesses of LLM-as-judge and how to calibrate it against human labels.
```

## 8. Supervisor upskilling plan

**Task:** Build a learning path for agent oversight skills

```text
I am [CURRENT ROLE, e.g. support team lead / SRE / QA analyst] moving into supervising autonomous AI agents at [COMPANY TYPE]. I know [EXISTING SKILLS] and have [HOURS] per week for [WEEKS] weeks. Build a learning plan covering: how LLM agents and tool calling work, reading traces in observability tools (e.g. LangSmith, Langfuse, Arize Phoenix), evaluation methods, AI risk frameworks (NIST AI RMF, ISO/IEC 42001, EU AI Act basics), and incident handling. For each week give goals, 2-3 specific free resources or official documents, and a hands-on exercise. Be explicit that this job title and its credentials are still forming, and suggest how to demonstrate competence without a formal certification.
```

> **Caution:** Verify resource links and current versions of standards; the regulatory landscape is changing quickly.
