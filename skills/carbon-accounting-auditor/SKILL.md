---
name: carbon-accounting-auditor
description: "Prompt playbook for a carbon accounting auditor. Use when a carbon accounting auditor wants help with work tasks such as: scope 1 and 2 analytical review; scope 3 materiality and sampling plan; carbon credit claim due diligence; draft findings and management letter; regulatory scope check; data control walkthrough; explain results to a board; upskilling study plan."
---

# Carbon accounting auditor prompts

Carbon accounting auditors give independent limited or reasonable assurance over companies' greenhouse gas inventories, climate disclosures and carbon credit claims, working to the GHG Protocol, ISO 14064-3, ISAE 3410 / ISSA 5000 and regimes like CSRD, California SB 253, EU ETS and CBAM. AI helps most with mapping messy client data to standards, designing sampling and analytical tests, drafting findings and management letters, and keeping up with fast-moving rules, while the auditor keeps the professional judgment and signs the opinion.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Scope 1 and 2 analytical review

**Task:** Spot anomalies in a client's emissions inventory before detailed testing

```text
You are a senior GHG assurance auditor working to ISO 14064-3 and ISAE 3410. Below is a client's Scope 1 and 2 inventory for [REPORTING YEAR] and [PRIOR YEAR], by site and source: [PASTE TABLE: site, activity data, units, emission factor, factor source, tCO2e]. Perform an analytical review: recalculate each line, check unit conversions and GWP set (AR5 vs AR6), compare location- vs market-based Scope 2, and flag year-on-year changes above [THRESHOLD %] or emission factors inconsistent with [EXPECTED SOURCE, e.g. DEFRA 2024, EPA eGRID]. Output a table: line, issue, likely cause, suggested follow-up procedure, risk rating. List questions to ask management.
```

> **Caution:** Recalculations are a starting point; verify factors against the official source documents before relying on them.

## 2. Scope 3 materiality and sampling plan

**Task:** Plan which Scope 3 categories to test and how

```text
Act as an assurance manager planning a [LIMITED/REASONABLE] assurance engagement over Scope 3 emissions for a [INDUSTRY] company reporting under [FRAMEWORK, e.g. ESRS E1, IFRS S2, SB 253]. Their reported categories and methods: [PASTE: category, tCO2e, method (spend-based, supplier-specific, average-data), data source]. Using the GHG Protocol Scope 3 Standard, propose an overall materiality threshold, rank categories by risk of material misstatement, and for each high-risk category specify procedures and a sample size rationale. Note where spend-based EEIO factors (e.g. USEEIO, EXIOBASE) create estimation uncertainty. Output as a planning memo with a risk-procedure matrix.
```

> **Caution:** Materiality and sample sizes must follow your firm's methodology and professional standards; treat this as a draft for review.

## 3. Carbon credit claim due diligence

**Task:** Assess whether offset or removal credits support a client's net-zero claim

```text
You are reviewing a client's claim that [CLAIM, e.g. 'carbon neutral operations in 2025'] using retired credits: [PASTE: registry (Verra, Gold Standard, ACR, Puro.earth), project ID, type, vintage, quantity, retirement serial]. Assess each credit against the ICVCM Core Carbon Principles, typical additionality, permanence, leakage and baseline-inflation risks for that project type, and double-counting / corresponding-adjustment issues under Article 6. Check whether the claim wording aligns with ISO 14068-1, SBTi guidance on beyond-value-chain mitigation, and anti-greenwashing rules such as the EU Green Claims and Empowering Consumers directives. Output a credit-by-credit risk table and a recommended wording for the claim. Flag areas where guidance is still unsettled.
```

> **Caution:** Verify retirement serials directly on the registry; Claude cannot access registries and project ratings change.

## 4. Draft findings and management letter

**Task:** Turn workpaper notes into clear findings for the client

```text
You are a carbon accounting auditor writing a management letter after a [ENGAGEMENT TYPE] engagement for [CLIENT TYPE]. My rough workpaper notes: [PASTE NOTES: issue, evidence, quantified impact in tCO2e, management response]. For each issue, write a finding with: condition, criteria (cite the specific requirement, e.g. GHG Protocol Corporate Standard boundary rules, ISO 14064-1 clause), cause, effect (quantified, and whether above materiality of [THRESHOLD]), and recommendation. Classify each as misstatement, control deficiency or improvement point. Use plain, neutral professional tone. Do not draft the assurance opinion itself.
```

> **Caution:** Remove client-identifying data if your confidentiality obligations prohibit sharing it with external tools.

## 5. Regulatory scope check

**Task:** Determine which climate disclosure and assurance rules apply to a client

```text
Act as a climate regulatory specialist. Client profile: [HQ COUNTRY], operations in [COUNTRIES/STATES], revenue [AMOUNT], employees [NUMBER], listed on [EXCHANGE or private], exports to EU of [CBAM GOODS, if any]. Identify which regimes may apply - e.g. CSRD/ESRS (as amended by the EU Omnibus simplification), California SB 253 and SB 261, ISSB-based local rules (UK SRS, Australia AASB S2, Japan SSBJ), EU ETS/CBAM MRV - with first reporting year, scope coverage and required assurance level. Output a table and a timeline. Clearly mark items that are proposed, delayed, litigated or that I should verify against the latest official text as of [TODAY'S DATE].
```

> **Caution:** Climate disclosure rules have changed repeatedly since 2024; always confirm against current official sources and legal counsel.

## 6. Data control walkthrough

**Task:** Evaluate the controls behind a client's emissions data pipeline

```text
You are an assurance auditor evaluating internal controls over GHG reporting. The client's process: [DESCRIBE: data sources such as utility bills, fuel cards, meters, ERP extracts; tools like Persefoni, Watershed, Sphera, Excel; who prepares, reviews and approves]. Map the process end to end, identify where errors or manipulation could enter (manual keying, factor library updates, estimation for missing months, boundary changes, acquisitions), and suggest key controls and test-of-controls procedures for each risk, aligned to COSO-style control objectives. Output a risk-control matrix plus a list of walkthrough questions.
```

## 7. Explain results to a board

**Task:** Communicate assurance results and their limits to non-specialists

```text
I am a carbon accounting auditor presenting to the audit committee of [COMPANY]. We issued a [LIMITED/REASONABLE] assurance conclusion on [SCOPE OF SUBJECT MATTER] with these key matters: [LIST FINDINGS AND ESTIMATION UNCERTAINTIES]. Draft a 5-minute briefing in plain language explaining: what limited vs reasonable assurance actually means, what we did and did not cover, the biggest sources of uncertainty (e.g. Scope 3 spend-based estimates), what the findings mean for upcoming [REGULATION] requirements, and three questions the committee should ask management. Avoid jargon; keep it factual and do not overstate assurance.
```

> **Caution:** Ensure the briefing matches the signed assurance report wording exactly.

## 8. Upskilling study plan

**Task:** Build a learning path from financial audit into GHG assurance

```text
I am a [CURRENT ROLE, e.g. financial auditor, environmental engineer] moving into carbon accounting assurance, with about [HOURS/WEEK] for [WEEKS] weeks. Build a structured study plan covering: GHG Protocol Corporate, Scope 2 and Scope 3 standards (and the ongoing revisions), ISO 14064-1/-3 and ISO 14065, ISAE 3410 and ISSA 5000, ESRS E1 and IFRS S2, PCAF for financed emissions, and EU ETS verification basics. For each week give topics, primary sources to read, a practical exercise (e.g. recalculating a sample inventory), and self-test questions. Include relevant credentials (e.g. GHG Management Institute courses, IEMA, GARP SCR) and note which are widely recognized versus emerging.
```

> **Caution:** Check standard versions and course offerings, since several standards are under revision.
