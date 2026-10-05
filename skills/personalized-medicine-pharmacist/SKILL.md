---
name: personalized-medicine-pharmacist
description: "Prompt playbook for a personalized medicine pharmacist. Use when a personalized medicine pharmacist wants help with work tasks such as: pGx consult note draft; ambiguous result troubleshooting; cDS alert specification; patient result explainer; program business case; dPYD/UGT1A1 safety check; aI tool risk review; evidence update study plan."
---

# Personalized medicine pharmacist prompts

A clinical pharmacist, usually in a health system, PGx clinic or specialty pharmacy, who turns pharmacogenomic results, biomarkers and patient factors into individualized drug and dose recommendations using CPIC/DPWG guidelines, FDA labeling and EHR decision support. AI helps most with drafting consult notes, mapping genotypes to guideline actions for pharmacist verification, building CDS and education materials, and keeping up with fast-moving evidence; the pharmacist and prescriber stay accountable for every recommendation.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. PGx consult note draft

**Task:** Draft a pharmacogenomic medication review note from a lab report and med list

```text
You are assisting a clinical pharmacist with a pharmacogenomic consult. Using the de-identified data below, draft a consult note. Patient context: [AGE, SEX, INDICATION, RENAL/HEPATIC FUNCTION]. PGx results (star alleles/diplotypes and lab-assigned phenotypes): [RESULTS, e.g. CYP2C19 *2/*2]. Current and planned medications: [MED LIST WITH DOSES]. For each drug-gene pair, give: phenotype, the relevant CPIC (and DPWG if different) recommendation with guideline year and evidence strength, whether the FDA label mentions it, and a suggested action. Also flag drug-drug interactions that could cause phenoconversion (e.g. strong CYP2D6 inhibitors). Output: a table, then a 5-sentence assessment/plan for the prescriber. Mark anything you are unsure of as 'VERIFY' rather than guessing.
```

> **Caution:** Verify every recommendation against current CPIC/DPWG guidelines and the lab report; use de-identified data unless your tool is HIPAA-approved.

## 2. Ambiguous result troubleshooting

**Task:** Work through a confusing or conflicting genotype-to-phenotype result

```text
I'm a pharmacist reviewing a pharmacogenomic result that doesn't fit the clinical picture. Gene: [GENE]. Reported diplotype/phenotype: [RESULT]. Lab and assay: [LAB, PANEL, ALLELES TESTED]. Clinical observation: [e.g. no response to clopidogrel, toxicity at standard dose]. Concomitant meds and conditions: [LIST]. Walk me through possible explanations in ranked order: untested or rare alleles (per PharmVar and AMP minimum allele sets), CNV/hybrid alleles for CYP2D6, activity score conversion differences between labs, phenoconversion, adherence, and non-genetic factors. For each, state what evidence would confirm it and what follow-up (repeat testing, therapeutic drug monitoring, lab contact) is reasonable. Flag where expert consensus is unsettled.
```

> **Caution:** Differential reasoning only; discuss confirmatory testing with the lab and the prescriber before changing therapy.

## 3. CDS alert specification

**Task:** Spec an EHR clinical decision support rule for a drug-gene pair

```text
Act as a clinical informatics pharmacist. Draft a specification for an interruptive or passive EHR alert for [DRUG]-[GENE] in our [EHR, e.g. Epic/Cerner] environment. Include: trigger logic (order entry, genotype present as discrete result, phenotype values), alert text under 60 words for prescribers, recommended alternatives/dose per current CPIC guideline, override reasons, suppression rules to limit alert fatigue, pre-test alert option if no result exists, and data elements needed (consider HL7 FHIR Genomics and CDS Hooks where our system supports them). Finish with a test-case table (genotype, order, expected behavior) and metrics to monitor after go-live. Note assumptions about our system that I must confirm.
```

> **Caution:** CDS logic must be validated by your P&T/informatics committee and tested in a non-production environment.

## 4. Patient result explainer

**Task:** Explain a PGx result to a patient in plain language

```text
Write a one-page patient handout explaining a pharmacogenomic result. Patient reading level: [e.g. 6th grade]; language: [LANGUAGE]. Gene and phenotype: [e.g. CYP2C19 poor metabolizer]. Medications affected now or in future: [LIST]. Explain: what the gene does, what the result means and does not mean (it is not a disease diagnosis; it stays the same for life), which drug classes may be affected, why they should tell every prescriber and pharmacist, and that they must not stop or change meds on their own. Briefly mention privacy protections (GINA in the US and its limits, e.g. life insurance). End with 3 questions they could ask their doctor. Avoid jargon; define any term you must use.
```

> **Caution:** Have the handout reviewed by the pharmacist and checked against your institution's patient education standards.

## 5. Program business case

**Task:** Plan a pre-emptive PGx testing program for a health system

```text
I'm a pharmacist proposing a pharmacogenomics service at [INSTITUTION TYPE, SIZE]. Target population: [e.g. cardiology PCI patients, oncology starting fluoropyrimidines, behavioral health]. Help me build a phased implementation plan modeled on published programs (e.g. St. Jude PG4KDS, Vanderbilt PREDICT, Mayo RIGHT, U-PGx/PREPARE). Cover: test selection (single-gene vs panel; CLIA/CAP-accredited lab), result storage and re-use, CDS, pharmacist workflow and collaborative practice agreement, reimbursement landscape (e.g. Medicare MolDX coverage, payer variability), staffing, training, and outcome metrics. Output: phased timeline table, budget categories, top 5 risks with mitigations. Flag where cost-effectiveness evidence is weak or payer policy is uncertain.
```

> **Caution:** Reimbursement and coverage rules change often; confirm with your revenue cycle team and current payer policies.

## 6. DPYD/UGT1A1 safety check

**Task:** Build a pre-chemotherapy pharmacogenomic safety checklist

```text
Act as an oncology pharmacist. Create a pre-treatment checklist for patients starting [fluoropyrimidines / irinotecan / thiopurines / OTHER] at [INSTITUTION]. Include: which gene(s) to test (DPYD, UGT1A1, TPMT/NUDT15 as relevant), current FDA labeling language and CPIC dosing actions by phenotype/activity score, turnaround time considerations and what to do if results are pending, documentation fields, escalation steps when testing was missed, and toxicity monitoring. Output as a checklist plus a short rationale section citing guideline names and years. Clearly mark where guidelines differ (e.g. CPIC vs. DPWG vs. EMA) or evidence is evolving.
```

> **Caution:** Dosing decisions require oncologist and pharmacist sign-off; confirm against current guideline versions and labeling.

## 7. AI tool risk review

**Task:** Assess an AI or algorithmic dosing tool before adopting it

```text
Our pharmacy is evaluating [TOOL/VENDOR], which uses [DESCRIPTION, e.g. ML-based polygenic or multi-gene dosing recommendations]. Help me write a structured risk assessment. Address: intended use and whether it may be regulated as a medical device or clinical decision support software under FDA's CDS guidance (and EU MDR/IVDR and the AI Act's high-risk rules if used in the EU); validation evidence and populations studied, including ancestry diversity of training data; transparency of rationale to clinicians; data privacy (HIPAA, BAA); integration and failure modes; and who holds accountability for recommendations. Use the NIST AI RMF functions (Govern, Map, Measure, Manage) as a structure. Output: a risk table and a list of questions for the vendor. Note regulatory points that are unsettled.
```

> **Caution:** Not legal advice; involve compliance, legal and your P&T committee before adoption.

## 8. Evidence update study plan

**Task:** Stay current and upskill on new PGx guidelines and evidence

```text
I'm a [PharmD / BCPS / resident] pharmacist with [EXPERIENCE LEVEL] in pharmacogenomics, aiming to [GOAL, e.g. lead a PGx clinic in 12 months]. Build me a 12-week learning plan using real resources: CPIC guidelines and PharmGKB, PharmVar star-allele nomenclature, DPWG, FDA Table of Pharmacogenetic Associations, ASHP and ACCP resources, AMP allele recommendations, and relevant certificate programs. Each week: topic, reading, one hands-on exercise (e.g. translate a raw genotype report to phenotype and recommendation), and a self-check question. Add a section on emerging areas (polygenic scores, HLA-based hypersensitivity screening, multi-omics, AI decision support) with what's known vs. speculative. Don't invent course names; say 'search for' if unsure a resource exists.
```
