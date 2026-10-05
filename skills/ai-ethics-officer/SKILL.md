---
name: ai-ethics-officer
description: "Prompt playbook for an AI ethics officer. Use when an AI ethics officer wants help with work tasks such as: use-case risk triage; algorithmic impact assessment draft; fairness metric review; launch go/no-go memo; aI policy and AIMS gap analysis; incident and complaint response; plain-language explainer for staff or public; upskilling plan and case study drill."
---

# AI ethics officer prompts

An AI ethics officer (often titled responsible AI lead or AI governance officer) sits in a company's legal, risk or product org and makes sure AI systems are built and deployed in line with law, standards like the EU AI Act, NIST AI RMF and ISO/IEC 42001, and the organization's own values. Claude helps most with mapping use cases to obligations, drafting impact assessments and policies, stress-testing launch decisions, and turning dense regulation into plain guidance for engineers and executives.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Use-case risk triage

**Task:** Classify a proposed AI use case and identify the obligations it triggers

```text
You are advising an AI ethics officer at [ORGANIZATION TYPE] operating in [JURISDICTIONS]. Proposed use case: [DESCRIPTION: purpose, users, affected people, data, model type, degree of automation]. Classify it under the EU AI Act risk tiers (prohibited, high-risk per Annex III, limited/transparency, minimal), and note any other laws that may apply (e.g. GDPR Art. 22, NYC Local Law 144, Colorado SB 24-205, sector rules like ECOA or HIPAA). Output a table: obligation, source, why it applies, confidence (high/medium/low), open question for counsel. Flag where implementation dates or guidance are still changing, and do not present your classification as legal advice.
```

> **Caution:** Regulatory timelines (EU AI Act high-risk dates, Colorado's AI Act) have shifted; confirm current status with counsel before relying on the classification.

## 2. Algorithmic impact assessment draft

**Task:** Draft a structured impact assessment for a model before launch

```text
Act as a responsible AI practitioner drafting an algorithmic impact assessment for [SYSTEM NAME], which [WHAT IT DOES] for [AFFECTED POPULATION]. Inputs: [MODEL CARD / DATA SHEET SUMMARY], [EVALUATION RESULTS], [HUMAN OVERSIGHT DESIGN]. Structure it using the NIST AI RMF functions (Govern, Map, Measure, Manage) and include: intended and foreseeable misuse, affected stakeholders, fairness and accuracy findings by subgroup, privacy and security risks, human oversight and appeal routes, residual risks, and mitigations with owners. Mark every claim you could not verify from my inputs as [NEEDS EVIDENCE] rather than filling gaps with assumptions.
```

> **Caution:** The assessment documents the team's evidence; Claude should not invent test results or subgroup metrics.

## 3. Fairness metric review

**Task:** Interpret bias testing results and pick appropriate fairness criteria

```text
I am an AI ethics officer reviewing bias testing for [MODEL PURPOSE, e.g. loan pre-screening]. Here are results by group: [TABLE: group, n, selection rate, TPR, FPR, calibration]. Protected attributes available: [LIST], proxy concerns: [LIST]. Explain what these numbers show, including the four-fifths impact ratio where relevant, and which fairness criteria (demographic parity, equalized odds, calibration) conflict here and why they can't all be satisfied. Note sample-size limits and intersectional gaps. End with 3 options for the product owner, the trade-off of each, and what additional analysis you'd want before deciding.
```

> **Caution:** Choosing a fairness criterion is a value and legal judgment for accountable humans; small subgroup samples can make metrics unreliable.

## 4. Launch go/no-go memo

**Task:** Prepare a decision memo for an executive review board

```text
Help me write a 1-page go/no-go memo for our AI review board on [SYSTEM/FEATURE]. Context: [FINDINGS FROM ASSESSMENT], [OPEN RISKS], [MITIGATIONS IN PLACE], [BUSINESS DEADLINE AND PRESSURE], [REGULATORY EXPOSURE]. Format: recommendation (go / go with conditions / no-go) stated up front; three strongest reasons; conditions with owners and dates; the best argument against my recommendation; what would change my mind; and escalation path if conditions are missed. Keep it neutral in tone and readable by non-technical executives. Ask me questions first if critical information is missing.
```

> **Caution:** The memo supports a decision; the board and named owners remain accountable for it.

## 5. AI policy and AIMS gap analysis

**Task:** Compare internal AI governance against ISO/IEC 42001 and NIST AI RMF

```text
You are helping an AI ethics officer prepare for possible ISO/IEC 42001 (AI management system) certification. Here is our current governance material: [PASTE POLICY EXCERPTS, RACI, REVIEW PROCESS, INVENTORY DESCRIPTION]. Produce a gap analysis table: requirement area (e.g. AI policy, roles, risk assessment, AI system impact assessment, data management, supplier/third-party AI, monitoring, internal audit, continual improvement), what we have, gap, suggested remediation, effort (S/M/L), priority. Cross-reference the matching NIST AI RMF subcategories where helpful. State clearly that you are working from general knowledge of the standard, not its licensed text, and list clauses I should verify against the official document.
```

> **Caution:** ISO standards are copyrighted; verify clause-level details against a purchased copy and an accredited auditor.

## 6. Incident and complaint response

**Task:** Triage an AI harm report and plan the response

```text
An AI-related incident has been reported: [WHAT HAPPENED, SYSTEM INVOLVED, WHO WAS AFFECTED, HOW IT WAS REPORTED, DATE]. As the AI ethics officer, I need a response plan. Provide: (1) immediate containment options and their costs; (2) facts to establish and who to ask; (3) whether this may be a reportable serious incident under EU AI Act Art. 73, a GDPR breach, or a sector-specific report, with uncertainty flagged; (4) affected-person communication principles; (5) a root-cause question list across data, model, deployment and oversight; (6) a timeline template. Compare to public cases in the AI Incident Database if relevant, without inventing details.
```

> **Caution:** Reporting deadlines are legally binding and fact-specific; involve legal and privacy teams immediately.

## 7. Plain-language explainer for staff or public

**Task:** Turn a governance decision or AI system into clear communication

```text
Rewrite the following for [AUDIENCE: e.g. frontline customer service staff / affected customers / general public]: [PASTE TECHNICAL OR LEGAL TEXT ABOUT THE AI SYSTEM OR POLICY]. Goals: explain what the system does and doesn't do, what data it uses, where humans are involved, how to question or appeal a decision, and who to contact. Reading level around grade 8, under [WORD LIMIT] words, no marketing language, no overclaiming accuracy or fairness. After the draft, list any statements that could be misleading or that legal should check, and note transparency obligations (e.g. EU AI Act Art. 50 disclosure that people are interacting with AI) it may help satisfy.
```

> **Caution:** Public statements about AI fairness or accuracy can create legal exposure (e.g. FTC deceptive-claims enforcement); have them reviewed.

## 8. Upskilling plan and case study drill

**Task:** Build a learning plan and practice judgment on real cases

```text
I'm [BACKGROUND, e.g. a compliance lawyer / data scientist] moving into an AI ethics officer role at [SECTOR]. Build a 12-week learning plan covering: ML basics for non-specialists (or ethics/law for technologists), EU AI Act, NIST AI RMF and its Generative AI Profile, ISO/IEC 42001 and 23894, fairness metrics, privacy techniques, red teaming, and model documentation (model cards, datasheets). Suggest real resources and credentials (e.g. IAPP AIGP) and weekly exercises. Then give me one realistic case study per month based on publicly documented incidents (e.g. COMPAS, Amazon's recruiting tool, Dutch childcare benefits scandal) with questions to answer, and critique my answers when I reply.
```

> **Caution:** Check that recommended courses and certifications are current; the field and its credentials change quickly.
