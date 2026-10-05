---
name: machine-to-human-explainer-for-regulated-decisions
description: "Prompt playbook for a machine-to-human explainer for regulated decisions. Use when a machine-to-human explainer for regulated decisions wants help with work tasks such as: reason codes to adverse action notice; actionable counterfactual explanation; cross-jurisdiction explanation obligations map; explanation template readability test; complaint and appeal response; explanation fidelity and drift check; regulator or audit briefing pack; upskilling plan for the explainer role."
---

# Machine-to-human explainer for regulated decisions prompts

Works inside lenders, insurers, health plans, employers and public agencies to turn automated or AI-assisted decisions (credit denials, claim rejections, benefit cuts, hiring screens) into explanations that satisfy rules like ECOA/Reg B adverse action notices, GDPR Art. 15/22 and the EU AI Act's Art. 86 right to explanation, and that people can actually act on. Claude helps most with translating model outputs (reason codes, SHAP values, counterfactuals) into plain language, drafting and testing notice templates, mapping obligations across jurisdictions, and preparing for complaints and regulator reviews, while the human checks accuracy against the real model and keeps sign-off.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Reason codes to adverse action notice

**Task:** Turn model output into specific, accurate principal reasons for a denial notice

```text
You are helping me draft the principal-reasons section of an adverse action notice under ECOA/Regulation B (and FCRA if a credit report was used). Product: [PRODUCT]. Model type: [MODEL TYPE]. For this applicant, the top contributing factors with attribution values are: [FEATURE: VALUE: DIRECTION LIST]. Our current reason-code library is: [REASON CODES]. Following CFPB Circulars 2022-03 and 2023-03 (reasons must be specific and accurate, not generic checklist items), give: 1) up to four reasons in plain language at roughly a 6th-8th grade reading level, 2) for each, which feature(s) it maps to and whether any existing code is too vague to use, 3) any factor that could be a proxy for a protected class and needs legal review. Flag anything you can't verify from the data given.
```

> **Caution:** Attribution values can be unstable or misleading. Check the reasons against the real model and have compliance counsel approve the notice before it is sent.

## 2. Actionable counterfactual explanation

**Task:** Write a 'what would change the outcome' explanation without misleading the person

```text
Act as an explainability specialist. An automated system made this decision: [DECISION] about [DOMAIN, e.g. insurance claim, benefit eligibility]. Inputs used: [INPUT FIELDS AND VALUES]. Counterfactuals our tool produced: [COUNTERFACTUAL LIST]. Draft a short explanation for the affected person that: names the main factors, gives one to three realistic changes that could lead to a different result, and says plainly what they can't change or what isn't guaranteed. Exclude counterfactuals that rely on immutable or protected attributes, or that would push someone toward harmful actions (e.g. taking on debt to change a ratio). Then list which counterfactuals you excluded and why, and any wording a regulator could read as a promise.
```

> **Caution:** Counterfactuals describe the model, not a guarantee. Check that each one actually flips the decision in the production model.

## 3. Cross-jurisdiction explanation obligations map

**Task:** Map which explanation and notice duties apply to a given automated decision

```text
I'm scoping explanation obligations for [DECISION SYSTEM], used for [USE CASE] in [JURISDICTIONS, e.g. EU, UK, US-federal, Colorado, New York City]. Humans are involved like this: [HUMAN REVIEW DESCRIPTION]. Build a table with columns: instrument (e.g. GDPR Arts. 13-15 and 22, EU AI Act Art. 86 and high-risk Annex III, UK GDPR/ICO guidance, ECOA/Reg B, FCRA, Colorado AI Act, NYC Local Law 144), whether it likely applies and why, what it requires to be disclosed and when, and what triggers it. Note where the law is still unsettled, has delayed or proposed-amended dates, or depends on court rulings such as CJEU C-203/22 (Dun & Bradstreet Austria). End with questions for counsel. Don't state effective dates you aren't sure of.
```

> **Caution:** This is a starting map for counsel, not legal advice. Effective dates and EU AI Act timelines have been moving, so check against current official sources.

## 4. Explanation template readability test

**Task:** Stress-test a notice template for comprehension and fairness before rollout

```text
Review this decision-explanation template, which will go to [AUDIENCE, e.g. Medicaid applicants, small-business loan applicants] in [LANGUAGES]: [TEMPLATE TEXT]. Assess it as both a plain-language expert and a consumer-protection examiner. Return: 1) estimated reading grade, plus the five hardest sentences rewritten, 2) jargon or model terms a layperson would misread (e.g. 'score', 'confidence', 'risk'), 3) whether it clearly explains how to contest, get human review, or correct data, with deadlines, 4) accessibility issues (screen readers, low literacy, translation risks), 5) three short comprehension questions I can use in user testing. Keep the original legal content unless you flag the change.
```

> **Caution:** Run real user testing with affected groups. Readability scores are not the same as people understanding the notice.

## 5. Complaint and appeal response

**Task:** Answer a person who disputes an automated decision

```text
You are helping me respond to a complaint about an automated decision. Decision and date: [DECISION]. Their message: [COMPLAINT TEXT, REDACTED]. What our records show about the inputs and reasons: [CASE FACTS]. Human review already done: [REVIEW STATUS]. Draft a respectful reply that: acknowledges their specific points, explains the main reasons in plain language, says whether a human reviewed or will review the decision, explains how to correct inaccurate data and how to escalate (internal appeal, regulator such as [REGULATOR], ombudsman), and gives timelines. Don't speculate about the model or admit or deny liability. Separately, list any facts that suggest the decision might be wrong and should go back for re-review.
```

> **Caution:** Remove personal data before pasting. A qualified human makes the final call on the appeal and approves the reply.

## 6. Explanation fidelity and drift check

**Task:** Monitor whether explanations still match model behavior after updates

```text
I monitor explanation quality for [MODEL NAME/VERSION] used in [DECISION TYPE]. Since the last release: [CHANGE SUMMARY]. Metrics: reason-code frequency this month vs. baseline [TABLE], SHAP/attribution stability across retrains [DATA], share of appeals citing 'reasons didn't make sense' [RATE], fidelity of the surrogate or explainer to the production model [METRIC]. Analyze this the way an SR 11-7 model-risk reviewer would: what changed, which reasons may now be inaccurate or too generic, possible causes (data drift, feature changes, explainer limits), and what to check next. Output a one-page monitoring memo with severity ratings and owners. Say where the data can't support a conclusion.
```

> **Caution:** Post-hoc explainers like SHAP and LIME estimate model behavior and can diverge from it. Confirm any finding against the production model.

## 7. Regulator or audit briefing pack

**Task:** Prepare documentation explaining how the system's explanations are produced

```text
Help me prepare a briefing pack for [REGULATOR/AUDITOR, e.g. state insurance department, CFPB exam, EU market surveillance authority] on how [ORGANIZATION] explains decisions from [SYSTEM]. Source material: model documentation [SUMMARY], explanation method [METHOD], notice templates [TEMPLATES], human-review process [PROCESS], appeal statistics [STATS]. Produce: 1) a two-page narrative of how the explanation pipeline works, from model output to the notice the person receives, 2) a control table mapping each step to relevant frameworks (NIST AI RMF Map/Measure/Manage, ISO/IEC 42001, ICO-Turing 'Explaining decisions made with AI'), 3) known limitations stated honestly, 4) the ten questions an examiner is most likely to ask, with evidence we should have ready.
```

> **Caution:** Don't overstate what the controls do. Every claim in the pack needs evidence behind it and sign-off from legal and compliance.

## 8. Upskilling plan for the explainer role

**Task:** Build a learning plan covering the law, the math and the communication skills

```text
I'm moving into a role explaining automated decisions in [SECTOR] after working as [CURRENT BACKGROUND]. Build a 12-week study plan of about [HOURS] hours a week covering: interpretable ML and post-hoc methods (SHAP, LIME, counterfactuals, monotonic constraints) and their failure modes; the law (GDPR Art. 22, EU AI Act transparency and Art. 86, ECOA/Reg B, FCRA, sector rules for [SECTOR]); fairness metrics and proxy discrimination; plain-language and risk communication. For each week, give goals, well-known free resources (official guidance, textbooks such as Molnar's 'Interpretable Machine Learning'), and one hands-on exercise using a public dataset. Mark which topics are settled and which are still being decided by courts or regulators.
```

> **Caution:** Only use resources you can find and check yourself, and don't rely on links you haven't verified.
