---
name: privacy-engineer
description: "Prompt playbook for a privacy engineer. Use when a privacy engineer wants help with work tasks such as: lINDDUN threat model for a new feature; dPIA first draft; code and schema privacy review; de-identification strategy; explaining a privacy tradeoff to product leads; regulatory change impact scan; privacy incident triage; pETs and AI privacy study plan."
---

# Privacy engineer prompts

Privacy engineers turn laws like GDPR, CPRA and the EU AI Act, and frameworks like the NIST Privacy Framework and ISO/IEC 27701, into the design of real systems: data maps, retention, consent flows, de-identification and privacy-enhancing technologies. They work at tech companies, healthcare and finance firms, and consultancies. Claude helps most with threat modeling, design and code review, drafting DPIAs, and explaining tradeoffs to engineers and lawyers. Legal conclusions stay with counsel.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. LINDDUN threat model for a new feature

**Task:** Run a privacy threat model on a design doc before launch

```text
You are a senior privacy engineer. Do a LINDDUN privacy threat model (Linking, Identifying, Non-repudiation, Detecting, Data disclosure, Unawareness, Non-compliance) of this feature: [FEATURE DESCRIPTION], data flows: [DATA FLOW DIAGRAM OR LIST OF SOURCES, STORES, PROCESSORS, THIRD PARTIES], user populations: [E.G. EU CONSUMERS, MINORS, PATIENTS]. Output a table with these columns: threat category, specific threat, affected data element, likelihood (low/med/high), impact, and recommended mitigation (prefer data minimization, then technical controls, then policy). After the table, list the 3 highest-priority fixes and any assumptions you had to make about the design. Mark anything that needs legal review.
```

> **Caution:** A threat model is only as good as the data flow map behind it, so check the flows with the engineering owners.

## 2. DPIA first draft

**Task:** Draft a GDPR Article 35 data protection impact assessment

```text
Help me draft a Data Protection Impact Assessment under GDPR Article 35 for [PROCESSING ACTIVITY]. Context: controller [COMPANY/ROLE], purposes [PURPOSES], lawful basis claimed [BASIS], data categories [INCLUDING ANY ARTICLE 9 SPECIAL CATEGORIES], data subjects [WHO], retention [PERIOD], processors and transfers [VENDORS, COUNTRIES, TRANSFER MECHANISM]. Follow the structure of the ICO/EDPB DPIA guidance: description of processing, necessity and proportionality, risks to individuals (likelihood x severity), and measures to reduce risk. Where my inputs are thin or the lawful basis looks weak, write a [GAP] note instead of inventing facts. Finish with open questions for the DPO and counsel.
```

> **Caution:** This is a draft for the DPO and counsel to review. Claude cannot decide whether the processing is lawful or whether you must consult the supervisory authority.

## 3. Code and schema privacy review

**Task:** Review a pull request or schema for personal data handling problems

```text
Act as a privacy-focused code reviewer. Review this [LANGUAGE/FRAMEWORK] change: [PASTE DIFF, SCHEMA, OR LOGGING CONFIG]. Look for: personal data written to logs, analytics events or error trackers; identifiers that don't need to be persistent or joinable; missing retention/TTL; fields that bypass the deletion/DSAR pipeline [DESCRIBE PIPELINE]; over-collection beyond the stated purpose [PURPOSE]; unhashed or weakly hashed identifiers (e.g. unsalted email hashes); and data sent to third-party SDKs. For each finding give file/line, the risk, a concrete code-level fix, and severity. Note any findings that also affect app-store privacy labels (Apple privacy nutrition labels, Google Play Data safety).
```

> **Caution:** Remove secrets and real customer data from snippets before pasting them.

## 4. De-identification strategy

**Task:** Pick and size a de-identification or differential privacy approach for a data release

```text
I need to share [DATASET DESCRIPTION: ROWS, COLUMNS, QUASI-IDENTIFIERS] with [RECIPIENT: INTERNAL ANALYTICS / RESEARCH PARTNER / PUBLIC] for [PURPOSE]. Applicable regime: [E.G. HIPAA SAFE HARBOR VS EXPERT DETERMINATION, GDPR ANONYMIZATION STANDARD, CPRA DEIDENTIFIED DATA]. Compare suitable options: suppression/generalization with k-anonymity and l-diversity, pseudonymization, synthetic data, and differential privacy (e.g. OpenDP or Google's DP library), including what each costs in utility. For DP, suggest a starting epsilon range with reasoning and explain privacy budget accounting across repeated queries. Name the re-identification attacks that matter here, such as linkage and membership inference. State clearly which options still count as personal data under the regime I named.
```

> **Caution:** Whether data is legally anonymous depends on context. Have an expert or counsel check any public release.

## 5. Explaining a privacy tradeoff to product leads

**Task:** Write a stakeholder memo pushing back on a data-hungry feature

```text
Write a one-page memo from me (privacy engineer) to [AUDIENCE: PM, ENG DIRECTOR, VP] about [FEATURE/REQUEST, e.g. retaining raw location history for 2 years for ML]. Their goal: [BUSINESS GOAL]. My concern: [CONCERN]. Use a collaborative tone, not a gatekeeping one. Structure: what they want to achieve, the specific privacy and regulatory risk in plain language (cite [RELEVANT LAWS, e.g. GDPR storage limitation, state privacy laws on precise geolocation as sensitive data]), 2-3 alternative designs that meet most of the goal with less data (aggregation, on-device processing, shorter retention, federated learning), the cost of each, and the decision I need from them by [DATE].
```

## 6. Regulatory change impact scan

**Task:** Turn a new law or rule into an engineering backlog

```text
Act as a privacy engineer tracking regulation. A new requirement is coming: [LAW/RULE/STANDARD, e.g. a new US state privacy law, EU AI Act Article 10 data governance duties, an update to the NIST Privacy Framework], effective [DATE]. Our stack and practices: [SYSTEMS, DATA TYPES, CONSENT/GPC HANDLING, DSAR TOOLING, REGIONS SERVED]. Compare it with what we already do and produce a gap analysis table: requirement, our current state, gap, engineering work needed, owner team, effort (S/M/L). Only cite provisions you are confident exist. Mark anything uncertain or still awaiting rules or guidance as [VERIFY], and list the questions to send to counsel.
```

> **Caution:** Laws change and Claude's knowledge has a cutoff date. Check every citation against the official text.

## 7. Privacy incident triage

**Task:** Triage a suspected personal data exposure and prepare for the notification decision

```text
Help me triage a possible privacy incident. Facts so far: [WHAT HAPPENED, e.g. S3 bucket public, PII in logs shipped to vendor, wrong-recipient email], data elements involved [LIST], estimated records/people affected [N], jurisdictions [LIST], discovered [TIMESTAMP], current containment [STATUS]. Produce: (1) immediate containment and evidence-preservation steps, (2) questions to answer for the risk-of-harm assessment, (3) a table of notification regimes that may apply (e.g. GDPR Art. 33 72-hour clock, state breach laws, HIPAA, contractual duties) with deadlines starting from discovery, each marked 'likely/possible/unlikely' and why, and (4) a factual timeline template. Don't conclude whether notification is legally required.
```

> **Caution:** Whether to notify, and when, is decided by counsel and the incident lead. Bring them in right away.

## 8. PETs and AI privacy study plan

**Task:** Upskill on privacy-enhancing technologies and AI-specific privacy risks

```text
I'm a privacy engineer with background in [CURRENT SKILLS, e.g. GDPR compliance, data mapping, basic Python] and want to get good at [TARGET AREA: differential privacy, secure multiparty computation, homomorphic encryption, federated learning, LLM training data memorization and machine unlearning]. I have [HOURS/WEEK] for [WEEKS]. Build a week-by-week plan with: core concepts, one primary resource per week (real textbooks, papers, courses or open-source libraries such as OpenDP, OpenMined, Microsoft SEAL), a small hands-on exercise, and a self-check question. End with a capstone project relevant to [MY INDUSTRY]. Say which areas are mature and deployable now, and which are still research with open problems.
```

> **Caution:** Check that links and resources still exist, since Claude can suggest outdated ones.
