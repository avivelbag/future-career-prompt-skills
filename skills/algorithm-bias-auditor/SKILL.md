---
name: algorithm-bias-auditor
description: "Prompt playbook for an algorithm bias auditor. Use when an algorithm bias auditor wants help with work tasks such as: audit scoping and test plan; fairness metric selection; disparity results analysis; proxy and data-lineage review; audit report and public summary; executive findings briefing; remediation and monitoring plan; regulatory upskilling path."
---

# Algorithm bias auditor prompts

Algorithm bias auditors test hiring, lending, insurance, housing and public-sector models for discriminatory outcomes. They work in-house, at audit firms, or as the independent auditors that rules like NYC Local Law 144, the EU AI Act and the Colorado AI Act require. Claude helps most with scoping audits, choosing and explaining fairness metrics, mapping findings to regulations and standards, and turning statistics into reports that regulators, executives and affected people can read.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Audit scoping and test plan

**Task:** Turn a new engagement into a scoped, defensible bias audit plan

```text
You are a senior algorithmic bias auditor. Draft a scoped audit plan for [SYSTEM NAME], which [WHAT IT DECIDES, e.g. ranks job applicants] for [DEPLOYER] in [JURISDICTIONS]. Inputs: [MODEL TYPE], [TRAINING/OUTCOME DATA AVAILABLE], [PROTECTED ATTRIBUTES COLLECTED OR INFERRED]. Output: (1) the legal and standards drivers that likely apply (e.g. NYC Local Law 144, EU AI Act Annex III, Colorado SB 24-205, ECOA/Reg B, EEOC Uniform Guidelines), each marked confirmed or needs counsel review; (2) the groups and intersections to test; (3) the metrics, with a reason for each; (4) data requests; (5) what is out of scope; (6) independence and conflict-of-interest checks. Flag any requirement that is still being set by rulemaking or has a delayed effective date.
```

> **Caution:** Laws and effective dates change. Have counsel confirm which obligations apply before the plan is final.

## 2. Fairness metric selection

**Task:** Choose and justify fairness metrics for a specific decision context

```text
Act as a fairness methodologist. For a [CLASSIFIER/RANKER/SCORE] used to [DECISION] where a positive outcome means [OUTCOME] and the base rates between groups [ARE/ARE NOT] known to differ, compare these metrics: selection-rate impact ratio (four-fifths rule), demographic parity difference, equalized odds, equal opportunity, predictive parity/calibration within groups, and any ranking metric that fits. Give a table with columns for metric, what it protects against, data it needs, and known conflicts (cite the Kleinberg/Chouldechova impossibility results). Recommend a primary metric and secondary metrics for [JURISDICTION/REGULATOR], and state which choices are value judgments the client must own rather than technical facts.
```

> **Caution:** Choosing a metric is a policy decision. Write down who made it and why.

## 3. Disparity results analysis

**Task:** Interpret computed disparity results and spot statistical pitfalls

```text
You are reviewing bias test output for [SYSTEM]. Here are the results from [Fairlearn/AIF360/Aequitas/custom code]: [PASTE TABLE OF GROUP COUNTS, SELECTION RATES, ERROR RATES, CONFIDENCE INTERVALS]. Check for: small-sample groups where the ratios are unstable (suggest Fisher's exact test or bootstrap intervals), Simpson's paradox across [STRATA, e.g. job family], missing or imputed demographic data, proxy variables, and differences between intersectional and single-axis results. Output: a ranked list of findings with severity and your confidence in each, follow-up analyses to run (with Python pseudocode), and anything the data cannot support. Do not call a result discriminatory under law; describe it statistically.
```

> **Caution:** Remove direct identifiers before pasting. Whether a disparity is legally discriminatory is for counsel to decide.

## 4. Proxy and data-lineage review

**Task:** Find features and data sources that may act as proxies for protected traits

```text
As a bias auditor focused on data governance (EU AI Act Article 10, NIST SP 1270), review this feature list and data lineage for [MODEL]: [PASTE FEATURES, DESCRIPTIONS, SOURCES, AND HOW LABELS WERE GENERATED]. Identify likely proxies for [PROTECTED ATTRIBUTES], such as ZIP code, school, employment gaps or device type. Also identify label bias, where historical decisions are used as ground truth, along with sampling and representation gaps and measurement bias. For each issue, give the mechanism, a test that would confirm it (e.g. predicting the protected attribute from the feature, or ablation), and remediation options with their trade-offs. End with questions for the data owner.
```

> **Caution:** Do not recommend inferring protected attributes, for example with BISG, unless that use is lawful and documented for this audit.

## 5. Audit report and public summary

**Task:** Draft the formal audit report plus a plain-language public summary

```text
Draft a bias audit report for [SYSTEM] audited for [CLIENT] between [DATES]. Findings: [PASTE FINDINGS, METRICS, LIMITATIONS]. Produce two documents. (A) A formal report with these sections: scope, independence statement, data and method, results tables, limitations, findings by severity, recommendations, and management response placeholders. Follow [NYC LL144 summary requirements / ISO/IEC 42001 internal-audit evidence / CLIENT TEMPLATE]. (B) A public summary of at most 300 words at an 8th-grade reading level that states the audit date, the impact ratios by category, and how to request an alternative process. Every limitation must stay in both versions, and the public summary must not overstate how fair the system is.
```

> **Caution:** The auditor signs the report and is accountable for every number in it. Recheck all figures against the source analysis.

## 6. Executive findings briefing

**Task:** Explain a hard finding to executives and legal without minimizing it

```text
I have to brief [AUDIENCE, e.g. CHRO, general counsel, product VP] about this finding: [FINDING AND METRICS]. They will probably push back with [EXPECTED OBJECTION, e.g. 'the model doesn't use race']. Write: a 5-bullet briefing memo (what we found, why it matters legally and reputationally, what it doesn't prove, options, decision needed by [DATE]); evidence-based answers to the three most likely objections; and a one-slide outline. Keep the tone neutral and firm. The finding must not be softened, and the remediation must not be overstated.
```

> **Caution:** Keep the facts of the finding and the client's business preferences separate. The auditor's independence depends on it.

## 7. Remediation and monitoring plan

**Task:** Design mitigations and ongoing drift monitoring after an audit

```text
Act as a responsible-AI engineer advising on remediation for [SYSTEM], where the audit found [FINDINGS]. Compare pre-processing (reweighing, resampling), in-processing (fairness constraints, e.g. Fairlearn reductions) and post-processing options (threshold adjustment). Do not recommend anything that would amount to unlawful use of protected traits in decisions, such as race-norming under Title VII §703(l); where legality is unclear, flag it. Estimate the accuracy and fairness trade-offs to test. Then design production monitoring: metrics, cadence, group-level alert thresholds, minimum sample sizes, owners, and what triggers re-audit. Output a table and a 90-day action plan.
```

> **Caution:** The legality of a mitigation varies by jurisdiction and sector. Get legal sign-off before anything is deployed.

## 8. Regulatory upskilling path

**Task:** Build a study plan on evolving AI bias law and standards

```text
I am a [BACKGROUND, e.g. data scientist / compliance analyst] moving into algorithmic bias auditing, with [HOURS/WEEK] to study over [WEEKS]. Build a curriculum covering: fairness statistics; US anti-discrimination law (disparate impact, ECOA/Reg B, FHA, EEOC guidance); NYC Local Law 144; the EU AI Act's high-risk obligations and timelines; the Colorado AI Act; the NIST AI RMF and SP 1270; ISO/IEC 42001 and ISO/IEC TR 24027; and audit practice such as IAASB/IIA-style evidence and independence. For each week, list primary sources to read, one hands-on exercise using a public dataset (e.g. Folktables, COMPAS with its known caveats), and a self-check question. Mark which areas are unsettled or changing fast, and say how I should keep up with them.
```

> **Caution:** Verify statute status and dates against official sources. Claude's knowledge may lag recent amendments or delays.
