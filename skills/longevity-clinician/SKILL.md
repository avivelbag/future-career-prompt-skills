---
name: longevity-clinician
description: "Prompt playbook for a longevity clinician. Use when a longevity clinician wants help with work tasks such as: annual panel synthesis; evidence check on an intervention; plain-language care plan; off-label prescribing documentation; marketing and claims compliance review; incidental-finding triage plan; clinic outcomes registry design; geroscience upskilling plan."
---

# Longevity clinician prompts

A licensed physician or advanced practitioner (today in concierge practices, longevity clinics like Fountain Life or Human Longevity, and academic healthy-aging programs) who manages long-horizon risk reduction using biomarkers, imaging, fitness testing and, increasingly, off-label or trial-stage geroprotective interventions. AI helps most with synthesizing large multi-test patient panels, appraising fast-moving and hype-prone evidence, drafting plain-language care plans, and keeping consent, claims and off-label documentation defensible.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Annual panel synthesis

**Task:** Turn a patient's yearly multi-test results into a prioritized risk summary

```text
You are assisting a licensed longevity physician. Below are de-identified results for a [AGE]-year-old [SEX] patient: labs [PASTE LABS incl. ApoB, Lp(a), HbA1c, fasting insulin, hs-CRP, eGFR/cystatin C], DEXA [RESULTS], VO2max [VALUE], CGM summary [METRICS], family history [DETAILS], current meds/supplements [LIST]. Produce: (1) a table of findings vs. reference ranges and vs. last year [PRIOR VALUES]; (2) the top 5 modifiable risks ranked by evidence-based impact (cardiovascular, metabolic, cancer, neurodegenerative, musculoskeletal), citing the guideline or risk tool used (e.g., PREVENT, ACC/AHA); (3) items needing confirmation or specialist referral. Mark anything based on non-validated tests (e.g., epigenetic clocks) as exploratory.
```

> **Caution:** Decision support only; the clinician verifies values and owns all diagnoses and orders. Remove identifiers unless using a HIPAA-covered, BAA-backed tool.

## 2. Evidence check on an intervention

**Task:** Appraise the evidence for a geroprotector or protocol a patient asks about

```text
Act as a skeptical clinical evidence reviewer. A patient asks about [INTERVENTION, e.g., rapamycin, metformin, NAD+ precursors, GLP-1 agonist for non-diabetic use, senolytics] for [GOAL]. Summarize the evidence in a table: study, design (animal, observational, RCT), population, endpoint (hard outcome vs. biomarker), effect size, key limitations. Then give a GRADE-style certainty rating, known harms and interactions with [PATIENT MEDS], regulatory status (FDA-approved indication vs. off-label vs. supplement), and relevant ongoing trials (e.g., TAME, PEARL). Say clearly where you are unsure and list citations I should pull and verify myself.
```

> **Caution:** LLM citations can be wrong or invented; check every reference in PubMed before relying on it.

## 3. Plain-language care plan

**Task:** Draft a patient-facing longevity plan from the clinician's decisions

```text
I am a longevity clinician. Using my plan below, draft a patient-facing care plan at about an 8th-grade reading level for [PATIENT FIRST NAME OR 'the patient']. My decisions: [EXERCISE TARGETS, e.g., Zone 2 minutes, strength sessions], [NUTRITION/PROTEIN TARGETS], [SLEEP], [MEDICATIONS STARTED/CHANGED], [SCREENINGS ORDERED], [FOLLOW-UP DATES]. Format: a one-paragraph 'why this matters' summary, a weekly checklist, what to measure at home, warning signs that mean call us or seek urgent care, and what we are NOT recommending and why. Avoid promising added years of life; describe benefits in terms of risk reduction and function.
```

> **Caution:** Do not add interventions the clinician did not choose; review before sending.

## 4. Off-label prescribing documentation

**Task:** Draft informed-consent and chart notes for off-label or experimental use

```text
Help me document an off-label prescription of [DRUG, DOSE] for [INDICATION/RATIONALE] in a [STATE/COUNTRY] practice. Draft (1) a chart note covering clinical rationale, evidence level, alternatives discussed, baseline labs, contraindication screening, and monitoring schedule; and (2) a patient informed-consent document in plain language covering off-label status, uncertain benefit, known risks, cost, and right to stop. Flag points where state medical board guidance, compounding pharmacy rules, or my malpractice carrier's requirements may differ and that I should confirm.
```

> **Caution:** Not legal advice; have consent templates reviewed by counsel and your carrier.

## 5. Marketing and claims compliance review

**Task:** Check clinic website or newsletter copy for misleading health claims

```text
You are a healthcare compliance reviewer. Review this marketing copy from our longevity clinic: [PASTE TEXT]. Identify claims that could be unsubstantiated or misleading under FTC health-claims guidance (competent and reliable scientific evidence), FDA rules on drug/supplement claims, state medical advertising rules for [STATE], and testimonial/endorsement rules. For each issue give: quote, why it's risky, and a compliant rewrite. Pay special attention to 'reverse aging', biological-age numbers, diagnostic accuracy of whole-body MRI or multi-cancer early detection tests, and outcome promises.
```

> **Caution:** Flags risk only; final sign-off belongs to counsel or the compliance officer.

## 6. Incidental-finding triage plan

**Task:** Plan follow-up for incidental findings from whole-body MRI or broad screening

```text
A patient's elective screening [TEST, e.g., whole-body MRI, coronary CAC, multi-cancer early detection blood test] returned: [FINDINGS]. As a clinical decision-support assistant, for each finding outline: likely significance, the relevant evidence-based follow-up pathway (e.g., Fleischner criteria for lung nodules, ACR incidental-findings white papers, Bosniak for renal cysts), urgency, and the risk of overdiagnosis or cascade testing. Then draft a short, calm script for discussing results with the patient that explains uncertainty honestly. List any finding where guidance is unclear and specialist input is needed.
```

> **Caution:** Radiology and specialist reports take precedence; clinician decides all follow-up.

## 7. Clinic outcomes registry design

**Task:** Plan how the practice tracks whether its interventions actually help

```text
Help me design a simple outcomes registry for a longevity practice of [N] patients. Goals: track whether our protocols change [OUTCOMES, e.g., ApoB, VO2max, lean mass, HbA1c, falls, hospitalizations] over [TIMEFRAME]. Propose: a minimal data dictionary (variable, unit, frequency, source such as EHR, wearable, lab), how to handle confounding and selection bias in a self-selected wealthy cohort, privacy safeguards under HIPAA (and GDPR if [EU PATIENTS]), when IRB review would be needed if we want to publish, and a quarterly dashboard layout. Note limits of what non-randomized clinic data can show.
```

> **Caution:** Publishing or generalizable research typically needs IRB review; check before collecting data for that purpose.

## 8. Geroscience upskilling plan

**Task:** Build a study plan to keep current in a fast-moving field

```text
I am a [SPECIALTY, e.g., internist, family physician, NP] moving into longevity medicine with about [HOURS] hours per week. Create a 12-week study plan covering: hallmarks of aging, exercise physiology and VO2max testing, lipidology (ApoB, Lp(a)), body composition, sleep, menopause/andropause management, aging biomarkers and their validation status (e.g., DunedinPACE, GrimAge, proteomic clocks), and evidence appraisal. For each week give learning goals, 2-3 types of sources (guidelines, review journals like Nature Aging, courses such as those from the Healthy Longevity Medicine Society or A4M, noting which are CME-accredited), and a practice case. Flag areas where consensus does not yet exist.
```

> **Caution:** Verify course accreditation and current curriculum; some longevity training is commercially driven.
