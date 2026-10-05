---
name: digital-therapeutics-prescriber
description: "Prompt playbook for a digital therapeutics prescriber. Use when a digital therapeutics prescriber wants help with work tasks such as: evidence appraisal of a DTx product; patient suitability screen; engagement dashboard triage; prior authorization and coverage letter; patient onboarding explainer; adverse event and malfunction reporting; clinic DTx program plan; regulatory and reimbursement briefing."
---

# Digital therapeutics prescriber prompts

A licensed clinician (physician, NP, psychologist or pharmacist) who selects, prescribes, onboards and monitors patients on regulated software treatments such as FDA-cleared prescription digital therapeutics (e.g. Somryst, Rejoyn, EndeavorRx) or Germany's DiGA apps, and handles evidence review, reimbursement and engagement follow-up. AI helps most with appraising trial evidence, making sense of engagement data, drafting prior-auth and patient materials, and tracking a fast-changing regulatory and payer landscape, while the clinician keeps every treatment decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Evidence appraisal of a DTx product

**Task:** Decide whether a digital therapeutic's evidence justifies adding it to your prescribing formulary

```text
You are a clinical evidence reviewer helping a [SPECIALTY] clinician evaluate the prescription digital therapeutic [PRODUCT NAME] for [INDICATION]. Using the pasted materials ([FDA 510(k)/De Novo summary, DiGA directory entry, published trial abstracts]), produce: 1) a table of pivotal studies (design, comparator, N, primary endpoint, effect size, attrition); 2) a critique of control conditions (sham app vs waitlist vs usual care), blinding and engagement-dependent results; 3) how closely trial populations match my patients ([PATIENT POPULATION]); 4) a bottom-line rating of strength of evidence with open questions. Quote only what is in the materials, and mark anything you infer or cannot verify.
```

> **Caution:** Verify claims against the original FDA decision summary or BfArM listing; marketing materials often overstate results.

## 2. Patient suitability screen

**Task:** Check whether a specific patient is an appropriate candidate before prescribing

```text
Act as a clinical decision-support assistant for a clinician considering [PRODUCT NAME] for a patient. De-identified details: age [AGE], diagnosis [DIAGNOSIS], comorbidities [LIST], current medications [LIST], smartphone/internet access [DETAILS], literacy/language [DETAILS], prior treatments [LIST]. Using the product's labeled indications, contraindications and warnings (pasted: [LABEL TEXT]), list: on-label vs off-label considerations, red flags (e.g. suicidality screening needs, seizure risk, sleep-restriction risk in bipolar disorder or untreated sleep apnea), practical barriers to engagement, and questions I should ask the patient. Output a checklist; do not make the final decision.
```

> **Caution:** Use de-identified data only; the prescribing decision and safety screening remain the clinician's responsibility.

## 3. Engagement dashboard triage

**Task:** Review a panel of patients' app engagement data and decide who needs outreach

```text
You are helping me triage my digital therapeutics panel. Below is an export from the [PRODUCT/PLATFORM] clinician dashboard: [PASTE DE-IDENTIFIED TABLE: patient ID, start date, modules completed, last login, symptom scores such as PHQ-9/ISI, flagged events]. Sort patients into: urgent clinical review (worsening scores, safety flags), engagement outreach (stalled >[N] days), on track, and ready for end-of-course review. For each group give a one-line reason per patient and a suggested next action. Note any data patterns that look like sync errors rather than real disengagement.
```

> **Caution:** Any safety flag (e.g. suicidal ideation item) must go to immediate clinician review under your clinic's protocol, not an AI-sorted queue.

## 4. Prior authorization and coverage letter

**Task:** Draft a letter of medical necessity for payer coverage

```text
Draft a letter of medical necessity to [PAYER NAME] for [PRODUCT NAME] for my patient with [DIAGNOSIS, ICD-10 CODE]. Include: regulatory status ([FDA clearance type and number]), relevant billing codes I will supply ([HCPCS/CPT codes, e.g. CMS digital mental health treatment codes G0552-G0554 if applicable]), prior treatments tried and why they were insufficient ([DETAILS]), the clinical evidence summary ([PASTE]), and the monitoring plan. Keep it under one page, professional tone, with placeholders for signature and NPI. Afterwards list which payer policy criteria I should double-check, since coverage rules for DTx vary widely and change often.
```

> **Caution:** Confirm current code descriptors and payer policy yourself; do not let the letter state anything not in the chart.

## 5. Patient onboarding explainer

**Task:** Create plain-language onboarding instructions and expectations for a patient

```text
Write a patient handout for someone starting [PRODUCT NAME] for [CONDITION]. Reading level: grade [6-8]; language: [LANGUAGE]. Cover: what the program is and that it is a prescribed treatment, not a wellness app; how long it takes ([PROGRAM LENGTH], [MINUTES/DAY]); what to expect (e.g. sleep restriction may make you sleepier at first); how their data is used and who sees it ([PRIVACY DETAILS FROM VENDOR]); when to contact the clinic vs emergency services; and how to get tech support. End with 3 teach-back questions I can ask. Use only facts I provided; flag anything you assumed.
```

> **Caution:** Have the handout reviewed against the product's official patient labeling before use.

## 6. Adverse event and malfunction reporting

**Task:** Document and route a suspected adverse event or software malfunction

```text
A patient using [PRODUCT NAME] experienced [EVENT DESCRIPTION] on [DATE]; app behavior observed: [DETAILS, e.g. crash, wrong module, missed safety alert]. Help me: 1) write an objective chart note; 2) decide which reporting pathways may apply (manufacturer complaint, FDA MedWatch voluntary report in the US, or the national competent authority / BfArM in the EU) and what each needs; 3) draft the MedWatch narrative fields from the facts given; 4) list information I still need to collect. Distinguish clinical harm from software defects, and state where my institution's policy should govern.
```

> **Caution:** Reporting obligations differ for user facilities vs individual clinicians; confirm with your risk management office.

## 7. Clinic DTx program plan

**Task:** Plan the workflow and governance for launching a digital therapeutics service in a clinic

```text
I am setting up a digital therapeutics prescribing program at [CLINIC TYPE] with [STAFF RESOURCES], starting with [PRODUCTS]. Draft an implementation plan with: product vetting criteria (regulatory status, evidence, data security, EHR integration, vendor financial stability, given that vendors such as Pear Therapeutics have gone bankrupt mid-treatment); prescribing and onboarding workflow; monitoring cadence and escalation rules; billing and documentation requirements for [COUNTRY/PAYER MIX]; HIPAA/GDPR data-sharing agreements; outcome metrics to track; and a 90-day pilot timeline. Present as a phased table plus a risk register. Flag areas where regulation or reimbursement is still unsettled.
```

## 8. Regulatory and reimbursement briefing

**Task:** Stay current on the fast-changing DTx regulatory and payment landscape

```text
Teach me, a practicing [CLINICIAN TYPE] in [COUNTRY], the current landscape for prescribing digital therapeutics. Explain: how FDA regulates software as a medical device (510(k), De Novo, Digital Health Advisory Committee, enforcement discretion for wellness apps); Germany's DiGA fast-track and how other countries (e.g. France's PECAN) compare; US billing options (remote therapeutic monitoring codes, CMS digital mental health treatment codes); how the EU AI Act and MDR could apply to AI-driven DTx; and the main ethical issues (equity, data privacy, engagement-as-dose). Then give me a 5-question self-quiz. State your knowledge cutoff and mark items likely to have changed.
```

> **Caution:** Check FDA, CMS and BfArM sources directly; rules and codes are updated yearly.
