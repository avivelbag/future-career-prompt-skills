---
name: human-ai-teaming-coach
description: "Prompt playbook for a Human-AI teaming coach. Use when a Human-AI teaming coach wants help with work tasks such as: human-AI task allocation map; automation bias drill design; team AI usage diagnostic; human oversight playbook; aI literacy programme plan; agent handoff protocol; change communication to a wary team; coach upskilling plan."
---

# Human-AI teaming coach prompts

Human-AI teaming coaches help teams work well with AI copilots and agents. They decide who does what, train people to calibrate trust and avoid automation bias, and build the AI-literacy and human-oversight practices that frameworks like EU AI Act Articles 4 and 14 and the NIST AI RMF expect. Claude helps most with designing workflows and trainings, analysing team usage and error data, and drafting the playbooks, coaching materials and reports.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Human-AI task allocation map

**Task:** Decide which steps of a team workflow the AI does, which it assists with, and which stay human-only

```text
You are an experienced human-AI teaming coach who draws on levels-of-automation research (Parasuraman, Sheridan & Wickens) and the NIST AI RMF. My team is [TEAM/FUNCTION] using [AI TOOL/AGENT]. Here is the workflow, step by step: [WORKFLOW STEPS]. Here are the stakes and constraints: [REGULATORY CONTEXT, ERROR COST, DATA SENSITIVITY]. Build a table with these columns: step, recommended mode (human-only / AI-suggests-human-decides / AI-acts-human-reviews / AI-autonomous), rationale, main failure risk, required human check, and the signal that would justify moving to a higher or lower level of automation. Then list the 3 steps where you are least confident and the information you would need to decide them.
```

> **Caution:** Treat the allocation as a starting hypothesis to pilot and review with the people doing the work. A named person stays accountable for each decision.

## 2. Automation bias drill design

**Task:** Build a practice exercise that trains staff to catch confident but wrong AI output

```text
Act as a training designer who specialises in automation bias and trust calibration (Lee & See, 2004). Design a 45-minute drill for [ROLE, e.g. claims reviewers] who use [AI TOOL] for [TASK]. Include: 10 realistic scenario cards, of which about 3 contain plausible AI errors of different types (fabricated fact, outdated rule, subtle misread of input, overconfident edge case); the cues a careful reviewer should notice; a facilitator answer key; and debrief questions about why errors were missed. Base the scenarios on these anonymised examples: [REAL EXAMPLES OR DOMAIN DETAILS]. Do not tell participants in advance how many cards contain errors.
```

> **Caution:** Use synthetic or properly de-identified data, and present the drill as practice, not as a performance evaluation.

## 3. Team AI usage diagnostic

**Task:** Analyse survey and log data to find where a team over-relies on or under-uses AI

```text
You are a human-AI teaming analyst. Below is data from [TEAM]: AI suggestion acceptance rates by task type, override rates, error and rework counts, time on task, and survey answers on trust and workload (NASA-TLX style). [PASTE DATA OR SUMMARY]. Identify patterns that suggest overtrust (high acceptance with rising errors), undertrust (frequent overrides of correct outputs, workarounds), or uneven adoption across people or tasks. Give your findings as: key patterns with supporting numbers, plausible causes, alternative explanations, the further data needed to confirm, and 3 to 5 coaching interventions ranked by expected impact. Mark which conclusions are tentative given the sample size.
```

> **Caution:** Report at team level and avoid singling out individuals from usage logs. Check your organisation's privacy and works-council rules before you analyse employee monitoring data.

## 4. Human oversight playbook

**Task:** Draft the team's procedures for monitoring and intervening in an AI system

```text
Act as a compliance-minded human-AI teaming coach. Draft a human oversight playbook for [AI SYSTEM] used by [TEAM] for [PURPOSE]. Use EU AI Act Article 14 (human oversight) as a reference for what good oversight looks like, and say clearly whether the system is likely to be high-risk under Annex III or whether you are applying Article 14 as voluntary good practice. Cover: oversight roles and RACI; what reviewers must understand about the system's capabilities and limits; checks on automation bias; when and how to override, pause or stop the system; escalation paths; logging; and refresher training. Format it as a numbered document with headings, plus a 1-page quick-reference card. Flag anything that needs legal review.
```

> **Caution:** This is a working draft, not legal advice. Counsel should confirm risk classification and obligations, and Article 14 interpretations are still settling through standards and guidance.

## 5. AI literacy programme plan

**Task:** Plan role-based AI literacy training that meets EU AI Act Article 4 and actually changes how people work

```text
You are a learning and development lead who specialises in human-AI teaming. Design a role-based AI literacy programme for [ORGANISATION] with these roles: [ROLES AND HEADCOUNTS]. The AI tools in use are [TOOLS]. Article 4 of the EU AI Act requires providers and deployers to take measures to ensure a sufficient level of AI literacy among their staff. Produce: learning objectives for each role, module outlines (format, duration), hands-on exercises using our real workflows, how we will measure behaviour change (Kirkpatrick levels 1 to 4), records to keep as evidence, and a 6-month rollout timeline. Note where guidance on what counts as 'sufficient' is still unclear.
```

> **Caution:** Article 4 sets no fixed curriculum. Check the European Commission's AI literacy guidance and FAQs before treating this plan as evidence of compliance.

## 6. Agent handoff protocol

**Task:** Design clear handoffs between autonomous AI agents and human team members

```text
Act as a human-AI teaming coach who draws on crew resource management and team situation awareness research. Our team uses [AI AGENT] to [AGENT TASKS], and humans take over when [CURRENT HANDOFF TRIGGERS]. The problems we see are: [e.g. missing context, duplicated work, unclear ownership]. Design a handoff protocol with: explicit triggers in both directions (agent to human and human to agent); a structured handoff summary template the agent should produce (adapted from SBAR); what the human must confirm before accepting a handoff; how ownership is recorded; and how to handle a handoff nobody picks up. Finish with 3 tabletop scenarios for testing the protocol.
```

> **Caution:** Pilot the protocol in a low-stakes setting first. Unacknowledged handoffs are a known failure mode, so a time-based escalation must always be in place.

## 7. Change communication to a wary team

**Task:** Explain a new AI teaming arrangement honestly to staff worried about jobs and deskilling

```text
You are helping a human-AI teaming coach communicate with [TEAM], who are about to start working with [AI TOOL] for [TASKS]. Their concerns include [CONCERNS, e.g. job loss, being blamed for AI errors, losing skills, surveillance]. These are the facts leadership has confirmed: [CONFIRMED COMMITMENTS]. Draft: (1) a plain-language announcement of about 300 words, (2) an FAQ with honest answers, which says 'not yet decided' wherever that is true, and (3) a facilitation guide for a 30-minute team conversation. Do not promise anything that is not in the confirmed facts, and point out any commitments that leadership should make explicit.
```

> **Caution:** Do not overstate job security or understate monitoring. Make sure HR and leadership approve every commitment before you share it.

## 8. Coach upskilling plan

**Task:** Build a personal learning plan to deepen expertise in human-AI teaming

```text
Act as a mentor for someone becoming a human-AI teaming coach. My background is [BACKGROUND, e.g. organisational psychology / UX / operations], and I mostly coach [SECTOR] teams. Create a 12-week study plan that covers: the foundations of human-automation interaction (automation bias, trust calibration, levels of automation, the 'ironies of automation'); how LLMs and agents fail in practice; evaluation methods; the NIST AI RMF and ISO/IEC 42001; EU AI Act Articles 4 and 14; and coaching and facilitation skills. For each week, give: the topic, 2 to 3 well-known canonical sources (name only the ones you are confident exist), a practical exercise with real AI tools, and a reflection question. Then list the open research questions in this field that I should keep following.
```

> **Caution:** Check every citation before relying on it, and look up current versions of the standards and regulatory guidance.
