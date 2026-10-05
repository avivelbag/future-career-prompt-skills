---
name: precision-fermentation-operator
description: "Prompt playbook for a precision fermentation operator. Use when a precision fermentation operator wants help with work tasks such as: fed-batch run trend review; contamination deviation investigation; sOP writing for CIP/SIP; hACCP / food safety plan hazard review; regulatory landscape briefing; scale-up risk plan; shift handover and batch summary; explaining the process to non-specialists; upskilling path for operators."
---

# Precision fermentation operator prompts

Runs the bioreactors that make animal-free food proteins and ingredients (whey and casein, egg white, collagen, fats, enzymes) using engineered yeast, fungi or bacteria, at companies like Perfect Day, The EVERY Company, Onego Bio and contract makers like Liberation Labs. They work under FSMA, HACCP and GMP rules. AI helps most with reading batch trends, investigating deviations, writing SOPs and batch records, preparing for audits, and learning the bioprocess and regulatory background.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Fed-batch run trend review

**Task:** Spot early warning signs in a live or just-finished fermentation run

```text
You are a senior bioprocess engineer reviewing a fed-batch precision fermentation run. Host: [ORGANISM, e.g. Pichia pastoris / Trichoderma reesei]. Product: [PROTEIN]. Vessel: [SCALE, L]. I am pasting timestamped data for dissolved oxygen, pH, temperature, agitation, airflow, off-gas O2/CO2 (OUR/CER/RQ), feed rate, base addition and offline OD/titer: [DATA]. Compare it with our golden-batch ranges: [RANGES]. Output: (1) a table of parameters that drifted, when the drift started, and how big it was; (2) likely causes ranked by evidence, such as oxygen limitation, overfeeding, contamination, foaming or probe drift; (3) checks I can do now without breaking sterility. Say where the data is too thin to tell. Do not recommend setpoint changes outside our validated ranges.
```

> **Caution:** Setpoint changes and batch disposition stay with the operator and QA under your approved procedures.

## 2. Contamination deviation investigation

**Task:** Structure a root-cause investigation after a contaminated or failed batch

```text
Act as a QA investigator at a food-grade precision fermentation plant running under FSMA Preventive Controls (21 CFR 117) and GMP. Batch [ID] was [CONTAMINATED / LOW TITER / OFF-SPEC] at [STAGE]. Evidence: [MICRO RESULTS, GRAM STAIN, TIMELINE, CIP/SIP RECORDS, RECENT MAINTENANCE, RAW MATERIAL LOTS]. Write a deviation report draft with these sections: event description, immediate containment, a 5-Whys and fishbone covering people, method, machine, materials, measurement and environment, the root cause hypotheses and the evidence for and against each, more data to collect, CAPA proposals with owners and due dates, and an impact assessment for other lots that used shared equipment. Mark clearly which statements are confirmed and which are hypotheses.
```

> **Caution:** Hypotheses are not root causes. QA must verify findings and sign off before the batch is released or closed.

## 3. SOP writing for CIP/SIP

**Task:** Turn engineering notes into a clear, auditable SOP

```text
You are a technical writer for a GMP food fermentation facility. Using my notes [PASTE NOTES] and equipment details [VESSEL, VALVES, CHEMICALS, CONCENTRATIONS, TEMPERATURES, HOLD TIMES], draft a standard operating procedure for [CIP / SIP / MEDIA STERILIZATION / INOCULUM TRANSFER]. Use these sections: purpose, scope, responsibilities, safety and PPE (including caustic, acid and steam hazards and lockout/tagout), materials, step-by-step procedure with verification checkpoints and record entries, acceptance criteria, deviations, and references. Steps should be numbered and short, with one action each. Mark with [VERIFY] any value I did not provide. Do not fill those in with typical numbers.
```

> **Caution:** Every parameter must come from your validated cycle studies, not from Claude's defaults.

## 4. HACCP / food safety plan hazard review

**Task:** Check a food safety plan for gaps specific to fermentation-derived ingredients

```text
Act as a PCQI (Preventive Controls Qualified Individual) reviewing the food safety plan for a precision-fermentation protein ingredient. Process flow: [STEPS from media prep through fermentation, harvest, cell removal, filtration, purification, drying, packaging]. Current hazard analysis: [PASTE]. Find hazards that are missing or underrated. Cover biological hazards (contaminants, viable production strain carryover), chemical hazards (residual media components, antifoam, cleaning chemicals, process allergens such as the target protein itself, e.g. milk-identical beta-lactoglobulin) and physical hazards. For each one, propose whether it should be a preventive control and how to verify it. Present the result as a table. List the questions I should take to regulatory or QA.
```

> **Caution:** Allergen labeling and strain-absence claims need regulatory review; animal-free proteins can still be allergenic.

## 5. Regulatory landscape briefing

**Task:** Understand approval pathways in markets the company is targeting

```text
I run fermentation operations and need a working understanding of how precision-fermentation food ingredients get to market in [MARKETS, e.g. US, EU, Singapore, Israel, Canada]. For each market, explain the relevant pathway (e.g. FDA GRAS notice vs self-affirmed GRAS, EU Novel Food via EFSA, SFA novel food), what that pathway means for manufacturing: specifications, strain documentation, absence of production organism and DNA, batch-to-batch consistency data, and how labeling is handled. Separate settled requirements from areas that are under debate or changing. Note where your information may be out of date and give the official sources I should check. Finish with a one-page table.
```

> **Caution:** This is background only. Check current rules with regulatory affairs and the official agency sources.

## 6. Scale-up risk plan

**Task:** Plan a tech transfer from pilot to production or CMO scale

```text
You are a scale-up advisor. We are transferring [PRODUCT] from a [PILOT VOLUME] vessel to [PRODUCTION VOLUME] at [OWN PLANT / CMO NAME]. Pilot performance: [TITER, YIELD, PRODUCTIVITY, kLa, P/V, TIP SPEED, MIXING TIME, FEED STRATEGY]. Production vessel specs: [SPECS]. Produce: (1) the scale-dependent risks we should expect, such as oxygen transfer, CO2 accumulation, mixing and substrate gradients, heat removal, foaming, shear and longer seed trains; (2) which scaling criterion to keep constant and what we give up by choosing it; (3) a staged engineering-run plan with go/no-go criteria; (4) the documents the tech-transfer package needs. Show your calculations and their assumptions.
```

> **Caution:** Check scale-up calculations against vendor data and engineering runs before you commit any production batches.

## 7. Shift handover and batch summary

**Task:** Turn messy shift logs into a clear handover and batch record summary

```text
Act as a fermentation shift lead. Below are my raw shift notes, alarm log and manual entries for [BATCH IDs]: [PASTE]. Write (1) a handover for the incoming shift, at most 200 words: the status of each vessel, open actions with times, alarms to watch, and pending samples; (2) a batch record summary in GMP-friendly wording (factual, past tense, no speculation) with any gaps or missing signatures listed as [MISSING]. Do not invent values, times or initials. If an entry is ambiguous, quote it and ask what was meant.
```

> **Caution:** Claude's summary does not replace the official batch record. Entries and signatures must come from the people who did the work.

## 8. Explaining the process to non-specialists

**Task:** Communicate clearly with visitors, community members, buyers or new staff

```text
I am a precision fermentation operator at [COMPANY/FACILITY]. I need to explain what we do to [AUDIENCE: local residents at a permit hearing / a food brand buyer / new hires from dairy plants]. Their likely concerns: [CONCERNS, e.g. GMOs, odor and wastewater, safety, "is it real dairy?", jobs]. Draft a [5-minute talk / one-page FAQ] in plain language. It should explain how the microbes make the protein and how the protein is separated from them, our safety and containment practices, and what the regulators did and did not review. Be honest about trade-offs and unknowns, such as energy use, LCA uncertainty and the fact that long-term market evidence is still limited. Do not make marketing claims we cannot support with [OUR DATA].
```

> **Caution:** Have environmental and health claims checked by legal or comms against your actual LCA and regulatory filings.

## 9. Upskilling path for operators

**Task:** Build a learning plan to move from brewing, dairy or pharma into precision fermentation

```text
Act as a bioprocess training mentor. My background: [e.g. craft brewery cellar operator / dairy plant technician / biopharma upstream associate]. My target role: precision fermentation operator, then [GOAL, e.g. process engineer]. Make a 12-week study plan covering microbial physiology of common hosts, fed-batch control and oxygen transfer, aseptic technique and sterility assurance, downstream basics (centrifugation, filtration, chromatography, spray drying), food GMP/FSMA/HACCP, and data literacy (trending, SPC). For each week list concepts, one hands-on or calculation exercise, free or low-cost resources such as BioWork, NIIMBL, GFI and university MOOCs, and a self-check question. Point out which of my existing skills transfer directly.
```

> **Caution:** Check that the resources named still exist and are current.
