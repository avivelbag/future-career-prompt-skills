---
name: ai-liability-insurance-adjuster
description: "Prompt playbook for an AI liability insurance adjuster. Use when an AI liability insurance adjuster wants help with work tasks such as: first-notice triage of an AI claim; silent-AI wording analysis; incident timeline from system logs; governance gap review against standards; reserve and status report; plain-language claimant letter; aggregation and accumulation scenario planning; upskilling plan for AI claims."
---

# AI liability insurance adjuster prompts

Investigates and settles claims where an AI system caused a loss: a chatbot's wrong promise, a biased screening model, an agent's unauthorized transaction. Today this is done under AI-specific policies (e.g. Munich Re aiSure, Armilla's Lloyd's-backed cover) and 'silent AI' exposure in cyber, E&O and product liability policies. Claude helps most with mapping coverage, reconstructing incident timelines from logs, comparing evidence to standards like the NIST AI RMF and the EU AI Act, and drafting clear reserve reports and claimant letters, while the licensed adjuster keeps every coverage decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. First-notice triage of an AI claim

**Task:** Sort a new AI-related loss notice into coverage lines and list what to request first

```text
You are assisting a licensed claims adjuster handling a new first notice of loss involving an AI system. Insured: [INSURED / INDUSTRY]. AI system: [DESCRIPTION, e.g. customer-service LLM chatbot, credit-scoring model, autonomous agent with payment access]. Alleged loss: [CLAIMANT ALLEGATIONS AND DAMAGES]. Policies in force: [POLICY TYPES, e.g. tech E&O, cyber, CGL, AI performance warranty]. Produce: (1) a one-paragraph plain summary of the incident; (2) a table mapping each alleged harm to the policy lines that could respond, with the likely trigger and the first exclusion to check; (3) a prioritized list of documents and logs to request in the first 72 hours, including model version, prompts and outputs, guardrail settings and human-review records; (4) open questions. Don't make a coverage decision. Mark anything that depends on policy wording you haven't seen.
```

> **Caution:** Coverage decisions and reservation-of-rights letters stay with the adjuster and coverage counsel; claimant data shared with Claude must follow your carrier's data-handling rules.

## 2. Silent-AI wording analysis

**Task:** Check whether existing policy wording affirmatively covers, excludes or is silent on an AI-caused loss

```text
Act as a coverage analyst reviewing whether this policy responds to a loss caused by AI output or AI decision-making. Policy excerpts: [PASTE INSURING AGREEMENT, DEFINITIONS, EXCLUSIONS, ENDORSEMENTS]. Loss facts: [SHORT FACT PATTERN]. Jurisdiction: [STATE / COUNTRY]. For each relevant clause, quote it, explain how it might apply to an AI-caused loss, and name the arguments for and against coverage. Pay attention to the definitions of 'professional services', 'computer system', 'bodily injury' and 'occurrence', and to any AI, data or algorithm exclusions. End with a summary table: clause, effect (grants / restricts / ambiguous), and confidence. Flag where case law on AI-caused losses is thin or unsettled. Don't state that the ambiguity will be read against the insurer without naming the governing doctrine in [JURISDICTION].
```

> **Caution:** This is analysis to support counsel, not a legal opinion; verify any case cited before relying on it.

## 3. Incident timeline from system logs

**Task:** Reconstruct what the AI system did and when, from logs and transcripts

```text
You are helping an adjuster reconstruct the sequence of events in an AI incident. I will paste [LOG EXCERPTS / CHAT TRANSCRIPTS / AGENT TOOL-CALL TRACES / CHANGE-MANAGEMENT RECORDS] from the insured's system [SYSTEM NAME]. Build a timestamped timeline table: time, actor (model, human operator, end user, third-party API), action, evidence source, and a note. Then identify: the first point where output departed from expected or documented behavior; any human-in-the-loop checkpoint that was skipped, overridden or absent; model or prompt changes near the incident; and gaps in the record. List the follow-up evidence needed to close each gap. Don't infer intent and don't fill gaps with assumptions. Mark every inference as an inference.
```

> **Caution:** Preserve the original logs under chain-of-custody procedures; Claude's timeline is a working summary, not evidence.

## 4. Governance gap review against standards

**Task:** Compare the insured's AI controls to NIST AI RMF, ISO/IEC 42001 and warranty conditions

```text
You are supporting a claims investigation into whether the insured met the AI risk-management conditions in its policy. Policy conditions or warranties: [PASTE, e.g. required human review, testing, monitoring]. Insured's evidence: [MODEL CARDS, TEST REPORTS, AUDIT RESULTS, GOVERNANCE POLICIES, ISO/IEC 42001 CERTIFICATE IF ANY]. Use cases: [USE CASE AND WHETHER IT MAY BE HIGH-RISK UNDER EU AI ACT ANNEX III OR A STATE LAW SUCH AS COLORADO SB 24-205]. Map the evidence against the NIST AI RMF functions (Govern, Map, Measure, Manage) and the specific policy conditions. Output a table: requirement, evidence provided, gap or none, and relevance to causation of this loss. Separate gaps that plausibly contributed to the loss from paperwork gaps that did not. Note which legal obligations were actually in force on [INCIDENT DATE], since EU AI Act duties phase in over time.
```

> **Caution:** A control gap is not automatically a breach of warranty; materiality and causation rules vary by jurisdiction, so involve coverage counsel.

## 5. Reserve and status report

**Task:** Draft a reserve recommendation and status report for the claims manager or reinsurer

```text
Draft a claim status report for [AUDIENCE: claims manager / reinsurer / Lloyd's syndicate lead]. Facts to date: [SUMMARY]. Claimant demands: [AMOUNTS AND HEADS OF DAMAGE]. Defense counsel's view: [SUMMARY]. Comparable outcomes, if any: [e.g. settlements, rulings such as Moffatt v. Air Canada 2024 on chatbot misrepresentation]. Use this structure: Claim summary; Coverage position; Liability analysis; Damages exposure as low / likely / high with assumptions; Recommended indemnity and expense reserves with rationale; Aggregation question (could this be one of many claims from the same model defect?); Next steps with owners and dates. Keep it under two pages, in neutral, factual language. Flag every figure that rests on an assumption and not on a document.
```

> **Caution:** Reserve figures must be set and approved by the authorized adjuster under carrier authority limits.

## 6. Plain-language claimant letter

**Task:** Explain a claim decision or information request to a claimant clearly and compliantly

```text
Write a letter from an insurance adjuster to [CLAIMANT TYPE: individual consumer / small business] about a claim arising from [AI INCIDENT, e.g. a chatbot quoting an incorrect refund policy]. Purpose: [REQUEST FOR INFORMATION / PARTIAL ACCEPTANCE / DENIAL / RESERVATION OF RIGHTS]. Key points: [DECISION, POLICY PROVISIONS RELIED ON, DOCUMENTS NEEDED, DEADLINES]. Requirements: plain English at about an 8th-grade reading level; no jargon such as 'model drift' unless you explain it; quote the policy language relied on; state the claimant's right to ask questions, dispute the decision or contact [STATE INSURANCE DEPARTMENT]; empathetic but not apologetic about coverage. Then list the items that compliance should check against [STATE] unfair claims settlement practices rules before sending.
```

> **Caution:** Denial and reservation-of-rights letters need legal and compliance review; required notice language and timelines differ by state.

## 7. Aggregation and accumulation scenario planning

**Task:** Plan for many claims arising from one shared foundation model or vendor failure

```text
You are helping an AI liability claims team prepare for an accumulation event. Several insureds use [SHARED MODEL / VENDOR / API, described generically]. Portfolio facts: [NUMBER OF INSUREDS, INDUSTRIES, POLICY LIMITS, EVENT OR AGGREGATION WORDING]. Build three realistic scenarios (for example a defective model update, a prompt-injection campaign, a vendor outage), each with how losses spread, likely claim types and counts, and which policy wording decides whether losses aggregate as one event. Then draft a claims-surge playbook: triage criteria, a standard evidence request to the vendor, legal holds, reinsurer notification triggers, and staffing. Flag where 'one occurrence' doctrine for AI defects is untested in court.
```

> **Caution:** Keep scenarios at the level of loss mechanisms; don't write exploit details. Treat any numbers as illustrative, not actuarial estimates.

## 8. Upskilling plan for AI claims

**Task:** Build a study plan to understand AI systems well enough to investigate them

```text
I am a [YEARS]-year property-casualty / professional liability adjuster moving into AI liability claims. My technical background: [DESCRIBE]. Build a 10-week study plan, 4 hours a week, that gets me to the point of questioning an insured's ML engineers credibly. Cover: how LLMs, classifiers and agents fail (hallucination, drift, bias, prompt injection, tool misuse); reading model cards, eval reports and logs; NIST AI RMF and its Generative AI Profile (NIST AI 600-1); ISO/IEC 42001; EU AI Act risk tiers and the revised EU Product Liability Directive (2024/2853), which treats software as a product; US state laws; and emerging AI-insurance products and audit standards. For each week give the goal, free reading, a hands-on exercise and five self-test questions. Note which sources change quickly and need rechecking.
```

> **Caution:** Laws and standards in this field change fast (the EU AI Liability Directive was withdrawn in 2025), so check every source's current status.
