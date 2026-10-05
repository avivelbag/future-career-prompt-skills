---
name: ai-red-teamer
description: "Prompt playbook for an AI red teamer. Use when an AI red teamer wants help with work tasks such as: scoped test plan from a threat model; triage a batch of test transcripts; write a findings report; prompt injection risk review for an agent; compliance mapping for adversarial testing; executive briefing on red-team results; design a regression eval suite; upskilling roadmap."
---

# AI red teamer prompts

AI red teamers adversarially test models and AI-powered products (prompt injection, jailbreaks, data leakage, agent misuse, bias, dangerous-capability evals) for AI labs, government safety institutes, consultancies and enterprises, increasingly to meet the EU AI Act's GPAI adversarial-testing duties and NIST AI RMF expectations. AI helps most with test planning and threat modeling against MITRE ATLAS and the OWASP LLM Top 10, triaging large volumes of transcripts, building eval harnesses, and writing clear findings reports, while humans keep authorization, scope and disclosure decisions.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Scoped test plan from a threat model

**Task:** Turn a system description into an authorized, scoped red-team plan

```text
You are a senior AI red team lead. Draft a test plan for [SYSTEM NAME], a [LLM APP / AGENT / RAG CHATBOT] that [WHAT IT DOES], with access to [TOOLS, DATA SOURCES, PERMISSIONS] and used by [USER POPULATION]. Authorized scope: [IN-SCOPE / OUT-OF-SCOPE], timeline [DATES]. Map likely attack surfaces to the OWASP Top 10 for LLM Applications (2025) and MITRE ATLAS tactics. Output: (1) a threat-model table (asset, threat actor, attack surface, ATLAS/OWASP ID, impact, likelihood), (2) prioritized test areas with rationale, (3) rules of engagement and stop conditions, (4) what evidence to log per finding. Flag any items needing legal or system-owner sign-off.
```

> **Caution:** Only test systems you are explicitly authorized to test; get written scope and rules of engagement first.

## 2. Triage a batch of test transcripts

**Task:** Classify and deduplicate outputs from an automated red-team run

```text
Act as a red-team analyst triaging results from an automated run using [TOOL, e.g. PyRIT / garak / promptfoo / Inspect] against [MODEL/APP]. Below are [N] transcript excerpts with the attack category each targeted. For each, classify: clear failure, partial failure, refusal/pass, or ambiguous; give a one-line reason and the policy or requirement violated ([POLICY DOC]). Then cluster duplicates into distinct root-cause issues, estimate severity using [SEVERITY RUBRIC], and list the ambiguous cases a human must review. Output as a table, then a short cluster summary. Do not reproduce harmful content verbatim; describe it. Transcripts: [PASTE REDACTED EXCERPTS]
```

> **Caution:** Automated graders and LLM judges miss and over-flag; a human must confirm every high-severity call.

## 3. Write a findings report

**Task:** Convert raw notes into a reproducible, actionable vulnerability report

```text
You are writing a red-team finding for the engineering team at [ORG]. From my notes below, produce a report with: title, severity (with justification against [RUBRIC, e.g. CVSS-style or internal]), affected component and version, OWASP LLM / MITRE ATLAS mapping, preconditions, high-level reproduction steps (redact exact exploit strings into [REDACTED PAYLOAD] references to our secure evidence store), observed vs expected behavior, impact on users or data, recommended mitigations (layered: model, system prompt, tool permissions, output filtering, monitoring), and suggested regression test. Keep it factual and under 600 words. Notes: [PASTE NOTES]
```

> **Caution:** Store working exploit payloads in access-controlled evidence systems, not in widely shared reports.

## 4. Prompt injection risk review for an agent

**Task:** Analyze an agentic workflow for indirect prompt injection and excessive agency

```text
Act as an AI security reviewer. Here is the architecture of our agent: [DESCRIBE: model, tools/MCP servers, data it reads (email, web, docs), actions it can take, approval steps, credentials]. Identify where untrusted content enters the context, which tool calls could be triggered by injected instructions, and where data could be exfiltrated (e.g. via URLs, markdown images, tool arguments). Output a table of trust boundaries and risks, then defensive recommendations ranked by risk reduction vs effort (least privilege, human confirmation, content isolation, egress controls, logging). Describe attack classes conceptually; do not write working payloads. Note which defenses are still unproven in the field.
```

> **Caution:** No mitigation fully prevents prompt injection today; treat recommendations as risk reduction, not guarantees.

## 5. Compliance mapping for adversarial testing

**Task:** Map a red-team program to EU AI Act, NIST and ISO expectations

```text
You are an AI governance advisor. Our organization [ROLE: GPAI provider / high-risk system provider / deployer] operates [SYSTEM] in [JURISDICTIONS]. Map our current red-team program [DESCRIBE: cadence, scope, tooling, external testers, reporting] against: EU AI Act obligations (incl. Art. 55 adversarial testing for GPAI with systemic risk and the GPAI Code of Practice), NIST AI RMF 1.0 and the Generative AI Profile (NIST AI 600-1), and ISO/IEC 42001. Output a gap table (requirement, source, current state, gap, suggested evidence). Clearly mark where guidance is still evolving, where you are unsure of the current text, and what we should confirm with counsel.
```

> **Caution:** Regulatory guidance is changing quickly; verify against current official texts and legal counsel.

## 6. Executive briefing on red-team results

**Task:** Explain findings and residual risk to non-technical leadership

```text
You are briefing [AUDIENCE: CEO / board / product VP] on the red-team exercise for [SYSTEM] ahead of [LAUNCH / DECISION, DATE]. Findings summary: [PASTE: count by severity, top issues, fixed vs open]. Write a one-page brief: bottom line up front (ship / ship with conditions / hold, as my recommendation is [RECOMMENDATION]), top 3 risks in plain language with real-world consequences, what was fixed, residual risk and monitoring plan, and what testing did NOT cover. Avoid jargon and exploit details. End with the decisions needed from leadership. Do not overstate assurance: red teaming shows presence of flaws, not their absence.
```

> **Caution:** The launch decision and risk acceptance belong to accountable leaders, not the red team or the AI.

## 7. Design a regression eval suite

**Task:** Turn past findings into a repeatable automated evaluation

```text
Act as an ML evaluation engineer. Using these confirmed past findings [PASTE: finding IDs, categories, short descriptions], design a regression eval suite for [MODEL/APP] to run on every [RELEASE / PROMPT CHANGE] in [FRAMEWORK, e.g. Inspect / promptfoo / custom pytest]. Output: (1) test case schema (fields, metadata, expected behavior), (2) scoring approach per category (rule-based vs model-graded, with known grader pitfalls), (3) how to generate benign variants to avoid overfitting to exact strings, (4) pass/fail thresholds and alerting, (5) a starter config skeleton with placeholder payload references. Keep sensitive payloads as references to a restricted dataset.
```

> **Caution:** Passing a fixed regression suite does not mean the system is robust to novel attacks.

## 8. Upskilling roadmap

**Task:** Build a personal learning plan for AI red teaming

```text
You are a mentor to AI red teamers. My background: [e.g. pentester / ML engineer / trust & safety analyst], strengths [X], gaps [Y], [HOURS] per week for [MONTHS]. Build a learning plan covering: LLM internals and failure modes, OWASP LLM Top 10 and MITRE ATLAS, agent and tool-use security, evaluation methodology and statistics, open-source tooling (PyRIT, garak, promptfoo, Inspect), responsible disclosure norms, and relevant regulation (EU AI Act, NIST AI RMF). For each month list goals, free resources I should verify exist, a hands-on lab using legal practice targets (e.g. CTF-style challenges or my own local models), and a portfolio artifact. Flag areas where the field lacks settled best practice.
```

> **Caution:** Practice only on your own systems, sanctioned CTFs or bug bounty programs within their stated rules.
