---
name: genetic-counselor-for-embryo-screening
description: "Prompt playbook for a genetic counselor for embryo screening. Use when a genetic counselor for embryo screening wants help with work tasks such as: pre-test PGT counseling outline; mosaic embryo result explainer; pGT-M case workup from pedigree; polygenic embryo screening (PGT-P) consult prep; result disclosure and grief communication; report QA and discrepancy check; consent form and policy review; upskilling study plan for emerging methods."
---

# Genetic counselor for embryo screening prompts

A genetic counselor at an IVF clinic, PGT lab or telehealth service who helps patients understand preimplantation genetic testing (PGT-A, PGT-M, PGT-SR and the contested polygenic PGT-P), interpret reports, and make embryo transfer decisions. Today they work under ASRM, ACMG, ESHRE, PGDIS and HFEA guidance. AI helps most with drafting plain-language explanations, organizing pedigrees and lab reports, comparing guidelines, and preparing for hard conversations. The counselor and physician still make every clinical decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Pre-test PGT counseling outline

**Task:** Prepare a pre-test counseling session for a couple considering PGT

```text
You are assisting a board-certified genetic counselor at an IVF clinic. Draft a pre-test counseling outline for patients considering [PGT-A / PGT-M for CONDITION / PGT-SR for TRANSLOCATION]. Context: [AGES, INDICATION, NUMBER OF PRIOR CYCLES, LAB USED]. Cover what the test can and cannot detect, accuracy limits (false positives/negatives, mosaicism, no-result rate), the embryo biopsy itself, possible outcomes including having no transferable embryos, cost, and confirmatory prenatal testing (CVS/amniocentesis). Where the evidence is contested, say so, for example the benefit of PGT-A by age group according to ASRM committee opinions. Output: a section-by-section outline with talking points and 5 teach-back questions. Mark anything I should check against the lab's own validation data.
```

> **Caution:** Lab-specific sensitivity and no-call rates must come from the lab's report, not from Claude.

## 2. Mosaic embryo result explainer

**Task:** Explain a mosaic PGT-A result and help the patient think through transfer options

```text
Act as a genetic counseling assistant. A PGT-A report shows: [EMBRYO ID, CHROMOSOME(S), WHOLE/SEGMENTAL, MOSAICISM LEVEL %, PLATFORM e.g. NGS]. The patient has [NUMBER] other embryos: [SUMMARY]. Using the PGDIS position statements and current ASRM guidance on mosaic embryo transfer, summarize: how the result is generated and how uncertain it is, what published data say about implantation, miscarriage and outcomes by mosaic type and level, any chromosome-specific concerns (e.g. imprinting or uniparental disomy risk on [CHROMOSOME]), and the recommended prenatal follow-up. Write two versions: a clinical note for the physician and a 250-word plain-language summary for the patient. Cite the guidance you rely on and flag where the data are thin.
```

> **Caution:** Ranking and transfer decisions belong to the patient and physician; check the cited outcome figures against the source papers.

## 3. PGT-M case workup from pedigree

**Task:** Organize family history and variant data before ordering PGT-M

```text
I am a genetic counselor preparing a PGT-M case. Variant(s): [GENE, HGVS NOTATION, ZYGOSITY, CLASSIFICATION, LAB]. Family history: [DE-IDENTIFIED PEDIGREE IN TEXT]. Condition: [CONDITION, INHERITANCE]. Produce: (1) a checklist of what the PGT lab will need, e.g. confirmed variant reports and relatives' DNA for linkage/haplotyping; (2) the reproductive risk per embryo, with your working shown; (3) open issues such as VUS status, reduced penetrance, de novo variants without informative relatives, or HLA matching requests; (4) whether the condition appears on the HFEA approved PGT-M list, if the patient is in the UK. Use a table for the risk calculation. Do not reclassify the variant yourself; list questions to send to the lab.
```

> **Caution:** Use de-identified data only. Variant classification stays with the accredited lab under ACMG/AMP criteria.

## 4. Polygenic embryo screening (PGT-P) consult prep

**Task:** Prepare a balanced response to a patient asking about polygenic risk scores for embryos

```text
A patient asks about polygenic embryo screening from [COMPANY, e.g. Orchid / Genomic Prediction LifeView] for [TRAITS/DISEASES]. Their ancestry: [ANCESTRY]. Help me prepare a balanced, non-directive response. Summarize the professional positions, including ACMG's 2024 points-to-consider statement, ESHG and ESHRE views, and the regulatory status in [JURISDICTION]. Explain why the absolute risk reduction among sibling embryos is small, how predictive accuracy drops for non-European ancestries, pleiotropy, and the limited number of embryos to choose between. Explain the ethical concerns, including trait selection. Output: a one-page briefing with a 'what the evidence supports / does not support / unknown' table and suggested wording. Flag claims you could not verify.
```

> **Caution:** This field changes fast and is contested. Check current society statements and the vendor's validation papers yourself.

## 5. Result disclosure and grief communication

**Task:** Draft a sensitive message or script for delivering bad PGT news

```text
I need to tell a patient that [OUTCOME, e.g. no euploid embryos / all embryos affected for CONDITION / only mosaic embryos]. Background: [CYCLE HISTORY, EMOTIONAL CONTEXT, LANGUAGE/CULTURAL NOTES]. Draft (a) a phone call script with an opening, the key facts, pauses for questions, and next steps such as another cycle, donor gametes, adoption, or stopping treatment; and (b) a short follow-up portal message that is warm, clear, and free of jargon. Use trauma-informed, non-directive language and do not offer false reassurance. List 5 questions the patient is likely to ask, each with an honest answer, and mark which ones should go to the REI physician or a mental health professional.
```

> **Caution:** Fit the scripts to the person. Hard news should be delivered live, not only through the portal.

## 6. Report QA and discrepancy check

**Task:** Cross-check a PGT lab report against the referral and prior results

```text
Review these de-identified documents for discrepancies before I counsel the patient: the referral/requisition [PASTE], the PGT lab report [PASTE], and prior carrier screening or karyotype results [PASTE]. Check whether the embryo IDs and counts match the embryology log [PASTE], whether the tested indication matches the order, whether the variant or translocation tested matches the family's confirmed result, what the no-call and inconclusive results are and why, and whether there are sex chromosome findings or incidental results the patient did or did not consent to receive. Output: a table of each discrepancy, its severity (critical/moderate/minor), and the person to contact (lab, embryology, physician). Don't infer results that aren't stated.
```

> **Caution:** Escalate any sample identity concern under the clinic's chain-of-custody procedure. Claude does not replace lab QA.

## 7. Consent form and policy review

**Task:** Assess clinic consent and policies for PGT against current guidance and law

```text
I'm reviewing our clinic's PGT consent form and embryo disposition policy [PASTE TEXT] for practice in [STATE/COUNTRY]. Compare it with ESHRE PGT Consortium good practice recommendations, ASRM ethics committee opinions, NSGC practice resources, and in the UK the HFEA Code of Practice. Check that the following are disclosed: test limitations, mosaicism handling, nonmedical sex selection policy, data retention and secondary research use of genomic data, the option of not learning certain results, and what happens to untested or abnormal embryos. Note any post-Dobbs state laws on embryo status that I should raise with legal counsel. Output: a gap table (requirement, current text, suggested revision, source). Flag anything that needs a lawyer.
```

> **Caution:** This is not legal advice. State embryo laws are changing, so have counsel confirm.

## 8. Upskilling study plan for emerging methods

**Task:** Build a learning plan on new PGT technologies and their evidence

```text
I am a genetic counselor with [YEARS] of experience in [PRENATAL / GENERAL / REPRODUCTIVE] counseling, moving into embryo screening. Build me a 6-week study plan covering: PGT-A platforms (NGS, SNP arrays) and how they detect mosaicism; haplotype-based PGT-M; niPGT-A using spent culture media; whole-genome embryo sequencing; polygenic scores and their statistics (relative vs absolute risk, ancestry portability); and the ethics of embryo selection. For each week, list key guidelines and landmark studies (only ones you are confident exist; mark uncertain citations), one case to practice, and 3 self-test questions. Mention ABGC continuing education options and NSGC special interest groups that cover this area.
```

> **Caution:** Check every citation before relying on it.
