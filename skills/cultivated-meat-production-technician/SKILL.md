---
name: cultivated-meat-production-technician
description: "Prompt playbook for a cultivated meat production technician. Use when a cultivated meat production technician wants help with work tasks such as: bioreactor run trend review; contamination investigation; sOP from tribal knowledge; deviation report draft; hazard analysis walkthrough; shift handover and production plan; explaining the process to visitors; upskilling study plan."
---

# Cultivated meat production technician prompts

Runs and monitors the bioreactors, cell banks, media prep and harvest steps that grow animal cells into food at companies like UPSIDE Foods, GOOD Meat, Wildtype, Mission Barns and Vow, under a food-safety regime (FDA pre-market consultation, USDA-FSIS inspection, HACCP, Singapore SFA, FSANZ) still taking shape. AI helps most with reading batch trends, troubleshooting contamination and growth issues, drafting SOPs and deviation reports, and keeping up with changing rules.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Bioreactor run trend review

**Task:** Spot early warning signs in a running batch's process data

```text
You are an experienced cell-culture process engineer reviewing a cultivated meat bioreactor run. Here is the data for batch [BATCH ID], [CELL TYPE/SPECIES], [REACTOR TYPE AND VOLUME], day [X] of [Y]: [PASTE TABLE: time, viable cell density, viability, glucose, lactate, ammonia, pH, DO, temperature, agitation, gas flow]. Our normal ranges are [RANGES OR 'use typical mammalian/avian culture ranges and say so']. Give me: 1) a table of parameters trending out of range or drifting, with how far off they are; 2) the two or three most likely causes of each; 3) checks I can do this shift, ranked by speed and cost; 4) what I should escalate to my supervisor now. Mark where you are guessing because of missing data.
```

> **Caution:** Decision support only; follow your site's alarm limits and escalation SOP, and don't change setpoints without authorization.

## 2. Contamination investigation

**Task:** Structure a root-cause investigation after a contaminated batch

```text
Act as a QA investigator for a cultivated meat facility running under HACCP and cGMP-style controls. Batch [BATCH ID] was found contaminated with [ORGANISM OR 'unidentified; observation: e.g. turbidity, pH crash, mycoplasma PCR positive'] on day [X]. Context: [MEDIA PREP, STERILIZATION METHOD (SIP/autoclave/filtration), SAMPLING EVENTS, OPERATOR CHANGES, ENVIRONMENTAL MONITORING RESULTS, RECENT MAINTENANCE]. Build a fishbone (people, methods, materials, machines, environment, measurement) of plausible entry points, rank them by likelihood given the organism and timing, and list the evidence that would confirm or rule each out. Then draft a CAPA outline with effectiveness checks. Don't settle on one root cause without evidence.
```

> **Caution:** Final root cause and product disposition belong to QA; contaminated material goes through your site's biohazard and disposal procedures.

## 3. SOP from tribal knowledge

**Task:** Turn informal notes into a controlled standard operating procedure

```text
You are a technical writer at a food biotech plant. Turn my rough notes on [PROCEDURE, e.g. cell bank thaw and seed train expansion / media batching / harvest and dewatering] into a draft SOP in our format: purpose, scope, responsibilities, safety/PPE, materials and equipment, step-by-step instructions with acceptance criteria, critical control points flagged, recording requirements (ALCOA+ data integrity), deviation handling and references. Notes: [PASTE NOTES]. Equipment: [MODELS]. Put any step that is ambiguous, missing a parameter, or might conflict with aseptic technique into a numbered 'questions for the process owner' list. Don't make up specific values.
```

> **Caution:** Draft only; it must go through your document control review and approval before use.

## 4. Deviation report draft

**Task:** Write a clear, factual deviation record after a process excursion

```text
Help me draft a deviation report for our quality system. What happened: [DESCRIPTION, e.g. DO probe failed for 3 h, pH controller overshoot, wrong media lot used]. Batch/equipment: [IDs]. Timeline: [TIMESTAMPED EVENTS]. Immediate actions taken: [ACTIONS]. Write it as: summary, chronology, affected product/materials, initial impact assessment on food safety and product quality, immediate containment, proposed investigation scope, and open questions. Keep it factual and neutral, separate what was observed from what is assumed, and don't use language that pre-judges whether product is releasable.
```

> **Caution:** Check every fact against batch records; impact and release decisions belong to QA.

## 5. Hazard analysis walkthrough

**Task:** Check a process step against HACCP hazard categories

```text
You are a food safety specialist who knows HACCP, the FDA Preventive Controls for Human Food rule (21 CFR 117), and the 2019 FDA/USDA-FSIS joint framework for cell-cultured food. For our process step [STEP, e.g. harvest, scaffold seeding, media sterilization, post-harvest handoff to FSIS-inspected processing], with inputs [INPUTS] and conditions [CONDITIONS], list potential biological, chemical (e.g. growth factors, antibiotics, residual media components, scaffold materials) and physical hazards. For each, say if it is likely a CCP, a prerequisite program, or neither, and suggest monitoring methods. Note where guidance for cultivated meat is still unsettled or differs by jurisdiction (US, Singapore SFA, FSANZ, UK FSA sandbox).
```

> **Caution:** Your HACCP team and a qualified PCQI make the final determinations; check the current guidance, which is still changing.

## 6. Shift handover and production plan

**Task:** Plan a multi-reactor week and write a clean handover

```text
I'm a production technician coordinating [NUMBER] bioreactors and a seed train this week. Status: [EACH REACTOR: batch, day, VCD, planned harvest/passage dates, issues]. Constraints: [STAFFING BY SHIFT, CLEANROOM/BSC AVAILABILITY, CIP/SIP TIMES, MEDIA PREP CAPACITY, QC LAB TURNAROUND]. Make 1) a day-by-day schedule table showing passages, feeds, sampling, harvests, cleaning and media batches; 2) conflicts or bottlenecks and options to resolve them; 3) a one-page handover template for the next shift with open items, alarms to watch, and pending QC results. Mark anything that relies on assumptions I need to confirm.
```

## 7. Explaining the process to visitors

**Task:** Answer public and press questions accurately without hype

```text
Our facility is hosting [AUDIENCE, e.g. local residents, a school group, journalists, a state legislator's staff]. Help me prepare plain-language answers (100 words max each) to likely questions: Is it safe? Is it 'real meat'? Are animals harmed (cell sourcing, fetal bovine serum)? Are antibiotics or GMOs used? What's the environmental footprint? Why is it banned in some US states? Base answers on these facts about our process: [FACTS APPROVED BY COMMS/REGULATORY]. Where evidence is limited or disputed (e.g. life-cycle emissions depend on energy source), say so honestly. Flag any question I should send to our communications or regulatory team.
```

> **Caution:** Use only company-approved facts and stay within confidential info and claims-substantiation rules.

## 8. Upskilling study plan

**Task:** Build a learning path from bioprocess tech to cultivated meat specialist

```text
I'm a [CURRENT BACKGROUND, e.g. biopharma upstream technician / food plant operator / lab biologist] moving into cultivated meat production. I have [HOURS/WEEK] for [MONTHS]. Build a study plan covering: animal cell culture and aseptic technique, bioreactor scale-up (kLa, shear, mixing time), serum-free media and growth factors, scaffolds and cell differentiation for muscle and fat, food safety (HACCP, PCQI training, FSIS labeling), and the regulatory landscape. For each module give learning goals, credible free or low-cost resources (e.g. The Good Food Institute materials, open courses, textbooks), a practical exercise, and self-test questions. Tell me which resource details I should verify are current.
```

> **Caution:** Check that the resources and certifications still exist; regulations for this field change often.
