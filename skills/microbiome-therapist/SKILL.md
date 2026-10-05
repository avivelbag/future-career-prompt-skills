---
name: microbiome-therapist
description: "Prompt playbook for a microbiome therapist. Use when a microbiome therapist wants help with work tasks such as: translate a microbiome test report; recurrent C. diff therapy options brief; donor screening protocol gap check; personalized diet-microbiome plan; probiotic claim fact-check; informed consent and patient handout; adverse event and outcomes log review; field upskilling plan."
---

# Microbiome therapist prompts

A clinician (often a GI-trained physician, dietitian, nurse or pharmacist) who interprets gut microbiome data and delivers or coordinates microbiome-targeted care: diet plans, probiotics, and regulated live biotherapeutics such as FDA-approved Rebyota and Vowst or FMT for recurrent C. difficile. AI helps most in turning noisy sequencing reports into cautious plain-language summaries, tracking an evidence base that changes quickly, keeping documentation and consent compliant, and separating proven indications from marketing claims.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Translate a microbiome test report

**Task:** Turn a lab or direct-to-consumer stool sequencing report into a careful clinical summary and patient explanation

```text
You are assisting a microbiome therapist. Below is a de-identified stool microbiome report from [LAB/TEST NAME] using [16S rRNA / SHOTGUN METAGENOMICS], for a patient with [PRESENTING CONDITION]. [PASTE REPORT]. Produce: (1) a clinician summary table listing each finding, what the method can and cannot resolve (taxonomic level, relative vs absolute abundance), and the strength of evidence linking it to the condition (strong / emerging / speculative); (2) a 150-word plain-language explanation for the patient that avoids implying diagnosis; (3) findings that warrant standard work-up instead (e.g. calprotectin, C. diff testing, colonoscopy referral). Flag any reference ranges whose provenance is unclear.
```

> **Caution:** Most consumer microbiome tests are not validated diagnostics; do not change medication or diagnose based on them alone.

## 2. Recurrent C. diff therapy options brief

**Task:** Compare guideline-supported options for a patient with recurrent C. difficile infection

```text
Act as a clinical evidence assistant. My patient has had [NUMBER] C. difficile episodes; prior treatments: [LIST]; comorbidities: [LIST, e.g. immunosuppression, IBD]; setting: [COUNTRY/HEALTH SYSTEM]. Using the IDSA/SHEA 2021 focused update, ACG 2021 guidance and the FDA labels for fecal microbiota live-jslm (Rebyota) and fecal microbiota spores live-brpk (Vowst), compare options (fidaxomicin, vancomycin taper, bezlotoxumab status, approved microbiome products, conventional FMT under FDA enforcement discretion or local rules). Output a table: option, eligibility, key evidence, safety concerns, logistics/cost. Note where your knowledge may be outdated and what I should verify against current labels.
```

> **Caution:** Check current labels and guidance; bezlotoxumab was discontinued in the US in 2025 and product availability varies by country.

## 3. Donor screening protocol gap check

**Task:** Audit a stool donor screening SOP against published consensus

```text
You are a quality reviewer for a stool donor program at [INSTITUTION]. Here is our donor screening and testing SOP: [PASTE SOP]. Compare it against the FDA safety communications on FMT (including MDRO and SARS-CoV-2/mpox screening alerts), the 2019 international consensus on stool banking (Gut), and, if we operate in the EU, the SoHO Regulation (EU) 2024/1938. Produce a gap table: requirement, source, our current practice, gap severity (critical/major/minor), suggested fix. List requirements you are unsure of separately, and do not invent clauses or citation numbers.
```

> **Caution:** Final protocol decisions belong to the program's medical director and regulatory/IRB oversight.

## 4. Personalized diet-microbiome plan

**Task:** Draft a 6-week dietary intervention plan with monitoring checkpoints

```text
You are helping a microbiome therapist working with a registered dietitian. Patient: [AGE, SEX], diagnosis [e.g. IBS-D, post-antibiotic dysbiosis], current diet [SUMMARY], restrictions [ALLERGIES, CULTURAL/RELIGIOUS], medications [LIST]. Draft a 6-week plan (e.g. fiber diversification, low-FODMAP with structured reintroduction, fermented foods) as a weekly table: goals, specific foods/servings, symptom metrics to log, and red-flag symptoms needing medical review. Cite the trial or guideline behind each element and grade its evidence. Flag interactions or contraindications (e.g. fiber with strictures, fermented foods when immunocompromised).
```

> **Caution:** Low-FODMAP and restrictive diets carry malnutrition and disordered-eating risk; coordinate with a dietitian.

## 5. Probiotic claim fact-check

**Task:** Evaluate a supplement or company's microbiome claims for a patient or clinic newsletter

```text
A patient asked about [PRODUCT NAME], which claims: [PASTE CLAIMS]. Act as a skeptical evidence reviewer. For each claim: identify the strain(s) at strain level, whether strain-specific RCTs exist, population and outcome studied, and whether the claim matches the evidence (supported / partially / unsupported). Note its regulatory status (US dietary supplement under DSHEA with structure/function claims vs approved drug) and any relevant AGA 2020 or World Gastroenterology Organisation probiotic guidance. Finish with a 100-word neutral answer I can give the patient. Say clearly when you cannot verify a study exists.
```

> **Caution:** Do not cite studies you cannot verify; check references in PubMed before sharing.

## 6. Informed consent and patient handout

**Task:** Draft consent and aftercare material for a microbiome procedure

```text
Draft an informed consent document and a one-page aftercare handout for [PROCEDURE, e.g. FMT via colonoscopy / oral capsule live biotherapeutic] at [CLINIC TYPE, COUNTRY]. Reading level: grade 6-8. Include: purpose, regulatory status (approved product vs investigational/enforcement discretion), known risks including infection transmission and unknown long-term effects, alternatives, what donor screening covers and cannot rule out, data/sample retention, and when to call or seek emergency care. Output in plain headings with [CLINIC CONTACT] placeholders. Mark sections our legal or IRB team must review.
```

> **Caution:** Consent forms need institutional legal/IRB review; investigational use may require an IND.

## 7. Adverse event and outcomes log review

**Task:** Analyze a clinic's treatment outcomes and adverse events for trends and reporting duties

```text
You are a clinical quality analyst. Here is our de-identified outcomes log for [TREATMENT] over [DATE RANGE] with columns [LIST COLUMNS]: [PASTE DATA]. Calculate cure/recurrence rates at 8 weeks, adverse event frequency by type and severity, and any donor- or batch-linked clusters. Identify events that may require reporting (FDA MedWatch, IND safety reports, or [LOCAL AUTHORITY]) and flag them for my review. Present a summary table, a short trend narrative, and limitations (sample size, missing follow-up, confounders). Do not infer causation without stating uncertainty.
```

> **Caution:** Remove identifiers before pasting; reporting decisions rest with the responsible clinician.

## 8. Field upskilling plan

**Task:** Build a learning plan to keep up with a fast-moving microbiome evidence base

```text
I am a [BACKGROUND, e.g. gastroenterology nurse practitioner / dietitian] moving into microbiome-based care, with [HOURS] hours per week for [MONTHS] months. Build a learning plan covering: sequencing methods and their limits (16S vs shotgun, compositional data analysis), host-microbe mechanisms, live biotherapeutic regulation (FDA CBER, EMA, EU SoHO), C. diff and IBD/IBS trial evidence, and critical appraisal of microbiome studies. Format as a month-by-month table with resources (textbooks, society courses such as AGA/ISAPP, review papers by topic rather than invented titles), a hands-on exercise, and a self-test question each month. List open scientific questions I should track.
```
