---
name: agent-workflow-architect
description: "Prompt playbook for an agent workflow architect. Use when an agent workflow architect wants help with work tasks such as: process-to-agent decomposition; tool permission threat model; eval suite design; trace failure diagnosis; human oversight design for compliance; architecture decision record; stakeholder briefing on autonomy level; upskilling plan."
---

# Agent workflow architect prompts

Designs multi-step AI agent systems (orchestration, tool access via APIs and MCP servers, human approval gates, evals, logging) that automate real business processes, today inside platform, automation and AI engineering teams. AI helps most with decomposing processes into agent and tool boundaries, threat-modeling tool permissions, drafting eval suites and runbooks, and translating designs for risk, legal and business stakeholders.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Process-to-agent decomposition

**Task:** Turn a manual business process into a proposed agent workflow design

```text
You are a senior agent workflow architect. Here is a manual process our team runs today: [PROCESS DESCRIPTION, STEPS, SYSTEMS TOUCHED, VOLUME PER WEEK]. Propose an agent workflow design. Output: (1) a step table with columns step, deterministic code vs LLM call vs agent loop, tools/APIs needed, read or write access, human approval required (yes/no and why); (2) the simplest architecture that would work (single agent, fixed pipeline, or orchestrator with subagents) and why the alternatives are worse here; (3) the failure modes for each LLM step; (4) steps that should NOT be automated. Prefer plain code over an agent wherever a step is fully deterministic.
```

> **Caution:** Validate volume, error-cost and access assumptions with the process owners before building.

## 2. Tool permission threat model

**Task:** Threat-model an agent's tool access against prompt injection and excessive agency

```text
Act as a security reviewer for an LLM agent. The agent's job is [GOAL]. Its tools are: [TOOL LIST WITH SCOPES, e.g. MCP servers, API keys, file/DB access]. It reads untrusted content from [SOURCES, e.g. inbound email, web pages, tickets]. Using the OWASP Top 10 for LLM Applications (especially prompt injection and excessive agency) as a frame, produce a table: threat, attack path, worst-case impact, likelihood, mitigation (least-privilege scope, sandboxing, allowlists, human confirmation, output filtering). Then list the three changes with the biggest risk reduction. Flag where current defenses against indirect prompt injection are still an open problem rather than solved.
```

> **Caution:** This is a design review aid, not a substitute for a pen test or your security team's sign-off.

## 3. Eval suite design

**Task:** Build an evaluation plan before shipping or changing an agent

```text
I'm about to ship [CHANGE, e.g. new model version, new tool, rewritten system prompt] to an agent that [AGENT PURPOSE]. Design an evaluation plan. Include: (1) 15-25 test cases as a table (input scenario, expected behavior, pass criteria, category: happy path / edge case / adversarial / tool failure); (2) which checks are code-graded, which need an LLM-as-judge rubric (write the rubric), and which need human review; (3) metrics to track (task success, tool-call errors, cost and latency per task, escalation rate); (4) a go/no-go threshold relative to the current baseline of [BASELINE NUMBERS OR 'none'].
```

> **Caution:** LLM-judge scores drift and can be gamed; spot-check them against human labels.

## 4. Trace failure diagnosis

**Task:** Troubleshoot a failing or looping agent run from its trace

```text
You are debugging a production agent. Below is a trace of a failed run (system prompt excerpt, tool calls, tool results, model outputs): [PASTE TRACE, REDACTED]. Expected outcome: [WHAT SHOULD HAVE HAPPENED]. Diagnose the root cause. Classify it as: unclear instructions, missing/poor tool description, bad tool output format, context overflow or lost context, model reasoning error, or an external system fault. Quote the exact turn where it went wrong. Propose the smallest fix, a regression test case that would catch it, and say how confident you are and what extra logs would confirm it.
```

> **Caution:** Redact credentials, customer PII and secrets from traces before pasting.

## 5. Human oversight design for compliance

**Task:** Map an agent workflow to EU AI Act and NIST AI RMF oversight expectations

```text
Our agent workflow does [USE CASE] for [USERS/AFFECTED PEOPLE] in [JURISDICTIONS]. Help me prepare for a compliance review. (1) Give a provisional view of whether it may fall under an EU AI Act high-risk category (Annex III) or transparency obligations, with reasoning and what facts would change the answer. (2) Map our controls [LIST: approval gates, logging, kill switch, monitoring] to human oversight (Art. 14) and record-keeping (Art. 12) expectations and to the NIST AI RMF Govern/Map/Measure/Manage functions. (3) List gaps as a table: gap, risk, proposed control, owner. Mark where guidance or harmonised standards are still pending.
```

> **Caution:** Not legal advice; classification and obligations must be confirmed by counsel.

## 6. Architecture decision record

**Task:** Document a design choice as an ADR for the engineering wiki

```text
Write an Architecture Decision Record for this choice: [DECISION, e.g. moving from a single agent to orchestrator plus subagents / adopting MCP for internal tools / framework X vs custom loop]. Context: [CONSTRAINTS, TEAM SIZE, LATENCY AND COST BUDGET, EXISTING STACK]. Options considered: [OPTIONS]. Use the format: Title, Status, Context, Decision, Options considered with pros/cons, Consequences (cost, latency, reliability, observability, lock-in), Reversibility, and Open questions. Keep it under 600 words and state assumptions explicitly rather than inventing benchmark numbers.
```

## 7. Stakeholder briefing on autonomy level

**Task:** Explain to business and risk leaders what the agent will and won't do

```text
I need to brief [AUDIENCE, e.g. COO, risk committee, works council] on a proposed agent that automates [PROCESS]. They are not technical. Write a one-page briefing: what the agent does in plain language, what it can never do without a human approving, what happens when it is unsure or fails, how we will measure whether it works, expected effect on staff workload and roles, and the top three risks with mitigations. Include 5 likely tough questions with honest answers. Avoid hype; do not overstate accuracy beyond our pilot data: [PILOT RESULTS].
```

> **Caution:** Workforce impact claims should be checked with HR and affected teams, not just asserted.

## 8. Upskilling plan

**Task:** Build a learning plan to grow into the agent architect role

```text
I'm a [CURRENT ROLE, e.g. backend engineer / RPA developer / data scientist] moving into agent workflow architecture. I have [HOURS] per week for [WEEKS] weeks. Build a learning plan covering: LLM fundamentals (context windows, tool use, structured outputs), agent patterns (prompt chaining, routing, orchestrator-workers, evaluator-optimizer), Model Context Protocol, evals and observability, agent security, and governance (NIST AI RMF, ISO/IEC 42001, EU AI Act basics). For each week give goals, a hands-on mini-project, and how to verify I learned it. Point to primary sources (official docs, standards bodies) and flag topics where best practice is still changing fast.
```

> **Caution:** Verify links and versions yourself; frameworks and APIs change quickly.
