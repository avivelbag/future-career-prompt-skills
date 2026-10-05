---
name: organ-bioprinting-technician
description: "Prompt playbook for an organ bioprinting technician. Use when an organ bioprinting technician wants help with work tasks such as: print run troubleshooting; batch record review; deviation and CAPA write-up; protocol to SOP; construct QC plan; regulatory landscape brief; explaining the work to patients or visitors; upskilling plan."
---

# Organ bioprinting technician prompts

Operates and maintains extrusion, inkjet and light-based bioprinters that build living tissue constructs, today mostly for research, drug testing and early clinical trials (e.g. 3DBio's AuriNovo ear implant, United Therapeutics/3D Systems lung scaffolds, ARPA-H PRINT), and later for patient-specific organs made under cGMP. AI helps most with batch records and deviation write-ups, troubleshooting print and viability problems, turning protocols into SOPs, and keeping up with fast-moving FDA/EMA rules for cell and tissue products.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Print run troubleshooting

**Task:** Diagnose a failed or degraded bioprint run from process data

```text
You are a senior bioprinting process engineer. My [PRINTER MODEL, e.g. BIO X6 / extrusion / DLP] run of [CONSTRUCT TYPE] using [BIOINK, e.g. GelMA 7% + cells at X M/mL] failed: [SYMPTOMS, e.g. filament breakup, nozzle clogging, layer collapse, low post-print viability of X%]. Parameters: nozzle [GAUGE], pressure [kPa], speed [mm/s], printhead/bed temp [C], crosslinking [UV dose / ionic method], time from cell mixing to print [min]. Give a ranked list of likely root causes (rheology, shear stress, temperature, crosslinking, cell handling), the evidence that would confirm or rule out each, and one controlled test per cause I can run with minimal cell use. Flag anything that would need a formal deviation.
```

> **Caution:** Suggestions are hypotheses; confirm against your validated process and record changes through change control.

## 2. Batch record review

**Task:** Pre-check a completed batch production record before QA review

```text
Act as a QA reviewer for a cell and tissue product made under 21 CFR 1271 (CGTP) and 21 CFR 210/211-style cGMP. Below is my completed batch record for lot [LOT NUMBER] of [CONSTRUCT]: [PASTE BATCH RECORD TEXT, REDACTED OF DONOR/PATIENT IDENTIFIERS]. Check for: missing entries or signatures, out-of-range values versus the specs I list here [SPECS], ALCOA+ data-integrity gaps, unexplained timing gaps (e.g. cell hold times), and equipment or reagent lot numbers lacking traceability. Output a table: Section | Issue | Severity (critical/major/minor) | Suggested correction or question for the operator. Do not rewrite recorded data.
```

> **Caution:** Never paste identifiable donor or patient data; QA release remains a human decision.

## 3. Deviation and CAPA write-up

**Task:** Draft a deviation report with root cause analysis and CAPA

```text
You are helping me write a GMP deviation report for a bioprinting suite. Event: [WHAT HAPPENED, e.g. ISO 5 cabinet particle excursion during print, bioink lot used past expiry, incubator CO2 alarm overnight]. Date/time, lot(s) and equipment affected: [DETAILS]. Immediate actions taken: [ACTIONS]. Draft: 1) factual description, 2) impact assessment on product sterility, viability and identity, 3) root cause analysis using 5 Whys and a fishbone (people, method, machine, material, environment, measurement), 4) proposed corrective and preventive actions with owners and due dates as placeholders, 5) effectiveness check. Mark any statement that is an assumption I need to verify.
```

> **Caution:** Disposition of affected product must be decided by QA, not inferred from this draft.

## 4. Protocol to SOP

**Task:** Convert a lab research protocol into a controlled SOP

```text
Act as a technical writer for a regulated tissue-engineering facility. Turn this research protocol into an SOP suitable for document control under an ISO 13485 / cGMP quality system: [PASTE PROTOCOL]. Use sections: Purpose, Scope, Responsibilities, Definitions, Materials and Equipment (with spaces for catalog and lot numbers), Safety (BSL-[LEVEL], UV/laser hazards), Procedure (numbered, one action per step, with acceptance criteria and hold points), Data Recording, Deviations, References. Flag steps that are ambiguous, rely on operator judgment without criteria, or would need validation (e.g. sterilization, crosslinking dose) before GMP use.
```

> **Caution:** Draft only; SOPs need subject-matter review, approval and training records before use.

## 5. Construct QC plan

**Task:** Plan quality control tests for a new printed tissue construct

```text
You are a tissue engineering QC specialist. I am setting up release and in-process testing for [CONSTRUCT, e.g. vascularized liver patch, cartilage graft] printed with [CELL SOURCE, e.g. autologous chondrocytes / iPSC-derived hepatocytes] and [BIOINK]. Intended use: [RESEARCH / PRECLINICAL / PHASE 1 CLINICAL]. Propose a QC panel covering sterility, mycoplasma, endotoxin, viability, cell identity and purity, shape fidelity versus the CAD model, mechanical properties and function. For each test give method, timing, typical acceptance criterion (marked as a starting point to justify), and relevant references such as USP <71>, <63>, <85>, ISO 10993 or FDA CMC guidance for cellular therapies. Note where standards for bioprinted products are still unsettled.
```

> **Caution:** Acceptance criteria must be justified with your own data and agreed with regulators for clinical use.

## 6. Regulatory landscape brief

**Task:** Understand which rules apply to a planned bioprinted product

```text
Explain, for a technician moving from research into a clinical program, how a bioprinted [PRODUCT, e.g. autologous ear cartilage implant] is likely regulated in [US / EU / BOTH]. Cover: whether it falls under 21 CFR 1271 section 361 or as a 351 biologic/combination product (and the RMAT designation), the EU ATMP regulation 1394/2007 and hospital exemption, GMP Annex 1 for aseptic processing, ISO 14644 cleanroom classes, and FDA's 2017 guidance on technical considerations for additive manufactured medical devices. Present as: rule | what it requires of my daily work | open questions. Clearly say where you are uncertain or where rules may have changed since your training data.
```

> **Caution:** Not legal or regulatory advice; verify with your regulatory affairs team and current agency documents.

## 7. Explaining the work to patients or visitors

**Task:** Write a plain-language explanation for a non-specialist audience

```text
I am an organ bioprinting technician at [ORGANIZATION]. Write a [300-word / 5-minute talk] explanation of what we do for [AUDIENCE, e.g. clinical trial participants, hospital donors, high school students]. Cover how a printed construct is made from cells and bioink, what our current product [PRODUCT] can and cannot do, and the realistic timeline for whole printed organs. Avoid hype: do not imply that transplantable printed hearts or kidneys exist today. Use a reading level around grade 8, include one simple analogy, and end with 3 likely audience questions and honest answers.
```

> **Caution:** Trial-related materials for participants usually require IRB or ethics committee approval before use.

## 8. Upskilling plan

**Task:** Build a learning plan for moving into GMP clinical bioprinting

```text
You are a mentor in regenerative medicine manufacturing. My background: [EXPERIENCE, e.g. 2 years of academic cell culture, basic CAD, no GMP]. Target role: bioprinting technician on a [CLINICAL / PRECLINICAL] program using [TECHNOLOGIES, e.g. extrusion, FRESH printing, volumetric printing]. Build a 12-week plan covering aseptic technique and gowning qualification, cGMP and data integrity, bioink rheology, cell biology of my cell type, printer maintenance and calibration, CAD/slicing for anatomical models from imaging, and environmental monitoring. For each week give goals, specific free or common resources (e.g. ISCT, ISSCR, FDA guidance documents, ASTM F42 / ISO TC 261 work), a hands-on exercise and a self-check question.
```
