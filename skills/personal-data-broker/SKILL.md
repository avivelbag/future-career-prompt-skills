---
name: personal-data-broker
description: "Prompt playbook for a personal data broker. Use when a personal data broker wants help with work tasks such as: data licensing offer review; deletion request campaign; consent ledger audit; client explainer letter; intermediary compliance map; re-identification risk check; recipient monitoring runbook; upskilling study plan."
---

# Personal data broker prompts

A personal data broker works for individuals rather than against them. Acting as a consent-based intermediary, they manage a client's personal data store or data cooperative membership, license data on the client's terms and enforce deletion rights against commercial brokers. Today's closest analogues are EU Data Governance Act data intermediation services, Solid pods, MyData operators and data-removal services using California's Delete Act DROP platform. AI helps most with parsing contracts and consent terms, mapping obligations across jurisdictions, drafting rights requests and explaining trade-offs to clients in plain language.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Data licensing offer review

**Task:** Evaluate a buyer's request to license a client's personal data before recommending it

```text
You are advising me as a personal data broker. I represent individuals and license their data only with their informed consent. Review this data access offer from [BUYER NAME / SECTOR]: [PASTE TERMS: data categories, purpose, retention, onward sharing, price, revocation clause]. My client's preferences are [CLIENT PREFERENCES]. Produce: (1) a plain-language summary of what the buyer would get and could do; (2) a red-flag table (clause | risk to client | severity | suggested redline), covering purpose limitation, re-identification, onward transfer, sensitive categories under GDPR Art. 9 or US state laws, and revocation; (3) a fair-value comment; (4) questions to put to the buyer. Mark anything that depends on jurisdiction-specific legal interpretation as needing counsel review.
```

> **Caution:** Not legal advice. The client makes the final consent decision, and sensitive-category deals need a lawyer's review.

## 2. Deletion request campaign

**Task:** Plan and draft opt-out or deletion requests to commercial data brokers for a client

```text
I help clients remove their profiles from commercial data brokers. The client lives in [STATE/COUNTRY] and wants deletion from [LIST OF BROKERS or 'all registered brokers']. Explain which mechanisms apply: for example, California's Delete Act and the DROP platform, CCPA/CPRA deletion rights, GDPR Art. 17, or the state registries in Vermont, Texas and Oregon. Then draft (1) a step-by-step campaign plan with deadlines and the statutory response windows; (2) a reusable deletion/opt-out request template with [PLACEHOLDERS] for identity verification, written to minimise the extra personal data disclosed; (3) a tracking table schema. If you are unsure whether a law currently applies or has an effective date, say so.
```

> **Caution:** Verify current statutory deadlines and DROP availability. Share only the minimum identity data needed for verification, and only with the client's authorization.

## 3. Consent ledger audit

**Task:** Find gaps in a client portfolio's consent records

```text
Act as a privacy compliance reviewer for a personal data intermediary. Here is an export of our consent ledger (fields: client ID, data category, recipient, purpose, consent date, expiry, revocation status, legal basis): [PASTE CSV OR SUMMARY]. Look for: consents that have expired but are still active, purpose drift between the recorded purpose and the recipient's stated use [RECIPIENT USE NOTES], missing revocation propagation, sensitive categories without explicit consent, and children's data. Output a findings table (record | issue | rule implicated, e.g. GDPR Art. 7, CPRA, COPPA | remediation | priority), then a short summary of systemic patterns. Do not infer identities from the client IDs.
```

> **Caution:** Use pseudonymised exports. Before taking any remediation step, confirm each finding against the source records.

## 4. Client explainer letter

**Task:** Explain a data deal or incident to a non-technical client

```text
I am a personal data broker writing to my client [CLIENT FIRST NAME], who is not technical. Situation: [DESCRIBE, e.g. 'a research lab wants 12 months of your fitness tracker data for $X' or 'recipient Y reported a breach affecting your shared data']. Write a letter of under 300 words at about an 8th-grade reading level that covers: what happened or is proposed, what data is involved, the realistic benefits and risks (including re-identification risk of 'anonymised' data), what the client's options are, my recommendation and why, and how to say yes, no or revoke later. Keep the tone neutral, without pressure to accept. Also give a 3-bullet version for SMS.
```

> **Caution:** Deal letters must not nudge the client toward accepting. A breach notice may also have legal content and timing requirements.

## 5. Intermediary compliance map

**Task:** Map regulatory obligations when launching a data intermediary service

```text
I am setting up a personal data brokerage that acts for individuals and operates in [JURISDICTIONS, e.g. EU, California, Texas]. Model: [DESCRIBE: personal data stores, pooled cooperative, revenue share, B2B buyers]. Map the obligations that may apply, for example EU Data Governance Act data intermediation rules (notification, neutrality, separate legal entity), GDPR controller/processor roles, the EU Data Act, CCPA/CPRA and the state data broker registration laws, the FTC Act Section 5, and the 2024 US Protecting Americans' Data from Foreign Adversaries Act. Output a matrix (obligation | source | triggers | what we must do | open questions). Flag areas where the law is unsettled or where our model might make us a 'data broker' in the regulated sense.
```

> **Caution:** This is a starting map, not a legal opinion, and these regimes change often. Have counsel check it.

## 6. Re-identification risk check

**Task:** Assess whether a de-identified dataset is safe to release to a buyer

```text
Act as a privacy engineer reviewing a dataset my brokerage plans to share with consent. Schema and summary statistics: [PASTE COLUMNS, CARDINALITIES, ROW COUNT, GEOGRAPHIC/TIME GRANULARITY]. Intended recipient and use: [RECIPIENT/USE]. Assess the risk of re-identification using quasi-identifiers, linkage with public datasets and location/time traces. Reference recognised approaches such as k-anonymity, differential privacy, the HIPAA Safe Harbor/Expert Determination methods and NIST SP 800-188. Output: a risk rating with reasoning, the specific columns to generalise, suppress or add noise to, a recommended release mechanism (aggregate, synthetic, query-only enclave), and the residual risks to disclose to clients. Do not attempt to re-identify anyone.
```

> **Caution:** Use only schema and aggregate statistics, never raw records. For health or high-risk data, get a formal expert determination.

## 7. Recipient monitoring runbook

**Task:** Set up ongoing monitoring of how licensed data is used

```text
My brokerage has licensed client data to [NUMBER] recipients under contracts with audit rights, purpose limits and deletion-at-term clauses. Draft an operational runbook for monitoring them that includes: a recurring checklist (attestations, deletion certificates, sub-processor changes, breach notices, news and enforcement alerts); signals that should trigger investigation; a severity matrix and escalation path; steps for revoking access and notifying clients; and a quarterly report template for clients. Make it fit a [TEAM SIZE]-person team using [TOOLS, e.g. ticketing system, consent-management platform]. Point out where technical enforcement (data clean rooms, query-only access, watermarking) would be better than contractual trust.
```

> **Caution:** Contract audit rights are only as good as how they are enforced. Clients remain accountable for their own consent decisions.

## 8. Upskilling study plan

**Task:** Build a learning plan for entering the personal data brokerage field

```text
I'm moving into personal data brokerage (acting for individuals) from [CURRENT BACKGROUND]. I have [HOURS/WEEK] for [WEEKS] weeks. Build a study plan that covers privacy law (GDPR, CCPA/CPRA, state broker laws, the EU Data Governance Act), privacy engineering (de-identification, differential privacy, consent management, Solid/personal data stores), data valuation and contracts, and ethics, including how data markets fail. For each week give goals, specific resources (e.g. the IAPP CIPP/E or CIPT body of knowledge, NIST Privacy Framework, MyData Declaration), and a practical exercise. Finish with a portfolio project idea, and point out which areas of the field are speculative and which are established.
```
