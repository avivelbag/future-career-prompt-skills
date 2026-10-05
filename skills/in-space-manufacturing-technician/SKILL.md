---
name: in-space-manufacturing-technician
description: "Prompt playbook for an in-space manufacturing technician. Use when an in-space manufacturing technician wants help with work tasks such as: run telemetry triage; microgravity defect root cause; procedure and checklist drafting; batch traceability record; payload safety and licensing checklist; customer run report; next-flight run planning; upskilling study plan."
---

# In-space manufacturing technician prompts

Runs and maintains production hardware in orbit or controls it from the ground: free-flyer capsules growing pharmaceutical crystals or semiconductor material (Varda, Space Forge), ISS printers and furnaces (Redwire, the ESA/Airbus metal printer), and later fiber and alloy lines on commercial stations. AI helps most with reading telemetry, finding root causes when a microgravity run goes wrong, writing traceable process and quality records, and turning payload safety and reentry licensing requirements into checklists. Humans still own every safety and release decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Run telemetry triage

**Task:** Review telemetry from one production run and flag deviations before the next pass

```text
You are helping an in-space manufacturing technician review a production run on [PLATFORM, e.g. free-flyer capsule / ISS payload rack]. The process is [PROCESS, e.g. protein crystallization / metal wire-fed printing / semiconductor crystal growth]. Below are the planned setpoints and tolerance bands, followed by the downlinked telemetry summary: [SETPOINTS AND TOLERANCES] [TELEMETRY: temperatures, pressures, accelerometer/g-jitter, power, timestamps]. Produce: (1) a table of every parameter that left its band, with duration and magnitude; (2) correlations with spacecraft events such as thruster firings, attitude changes or eclipse transitions; (3) a ranked list of the deviations most likely to affect product quality, with your reasoning; (4) questions I should ask the operations team before the next contact window. Label anything that relies on assumed data as an assumption.
```

> **Caution:** Telemetry may be decimated or delayed. Confirm anomalies against the raw data before you command any change.

## 2. Microgravity defect root cause

**Task:** Structure a root-cause investigation for a defective part or batch made in orbit

```text
Act as a materials and process engineer with microgravity experience. A [PART/BATCH] produced on [PLATFORM] failed inspection: [DEFECT DESCRIPTION, e.g. porosity, delamination, polymorph mismatch, crystal size out of spec]. Context: [PROCESS PARAMETERS], [FEEDSTOCK LOT], [ENVIRONMENT DATA], [GROUND CONTROL SAMPLE RESULTS]. Organize the investigation as a fishbone covering machine, material, method, environment, measurement and the effects of microgravity itself (no buoyant convection, Marangoni flow, wetting and contact behavior, sedimentation). For each candidate cause, give the evidence for and against it, the cheapest test that would tell the causes apart (on the ground or in orbit), and a likelihood rating. End with what ground analogues such as drop towers, parabolic flights or clinostats can and cannot reproduce for this defect.
```

> **Caution:** Microgravity process physics is still poorly characterized. Treat these hypotheses as starting points and do not attribute a root cause without test evidence.

## 3. Procedure and checklist drafting

**Task:** Turn an engineering process into a crew- or operator-executable procedure

```text
Draft an operations procedure for [TASK, e.g. feedstock cartridge swap / build-plate removal / furnace sample exchange] on [PLATFORM]. It will be executed by [ISS CREW / commercial station crew / ground operators via commanding]. Inputs: [ENGINEERING STEPS], [HAZARDS AND CONTROLS from the safety data package], [TOOLS AND CONSUMABLES], [TIME AVAILABLE]. Follow the NASA ISS procedure style: numbered steps, a single action per step, WARNING/CAUTION/NOTE blocks placed before the step they apply to, verification steps, and go/no-go points. Add a contingency branch for [LIKELY OFF-NOMINAL, e.g. stuck latch, particulate release, power drop]. After the procedure, list every step whose hazard control you could not trace to my inputs.
```

> **Caution:** Your safety review team and the platform operator must validate procedures. Never execute a draft.

## 4. Batch traceability record

**Task:** Assemble the as-built record for a space-made product destined for regulated use

```text
I am compiling the as-built and traceability record for [PRODUCT, e.g. pharmaceutical crystal batch / AM flight part] made on [MISSION/PLATFORM]. The record must support [STANDARD, e.g. FDA cGMP under 21 CFR 210/211 / NASA-STD-6030 for additively manufactured spaceflight hardware / customer quality requirements]. Inputs: [FEEDSTOCK LOT CERTS], [PROCESS LOG], [DEVIATIONS], [REENTRY/RECOVERY CHAIN OF CUSTODY], [POST-FLIGHT TEST RESULTS]. Produce a structured record template filled with my data, a gap list showing which elements the standard expects that I have not supplied, and a short deviation summary written for a quality reviewer. Point out any place where producing in orbit leaves the existing standard ambiguous, such as environmental monitoring during reentry.
```

> **Caution:** Regulators have not settled how cGMP applies to space-made drugs. Your QA and regulatory leads make the release decision.

## 5. Payload safety and licensing checklist

**Task:** Map a new production payload against safety and launch/reentry approvals

```text
Help me prepare a compliance checklist for a new in-space manufacturing payload: [PAYLOAD DESCRIPTION, hazardous materials, energies, temperatures, pressures]. It will fly on [ISS / free-flyer with reentry capsule / commercial station] and launch on [VEHICLE]. Where they apply, cover: ISS payload safety requirements (SSP 51700 and the phased safety review process), FAA commercial space licensing under 14 CFR Part 450 for reentry, the NOAA remote sensing license if cameras are aboard, toxicity and offgassing limits, and the host platform's interface requirements. Output a table with columns requirement source | what it demands | evidence I need | owner | lead time. Mark clearly which items you are unsure of or where commercial station rules are not yet published.
```

> **Caution:** Regulations and platform requirements change. Check every item against current official documents and confirm with your licensing counsel.

## 6. Customer run report

**Task:** Explain run results to a paying customer or research partner

```text
Write a results report for [CUSTOMER, e.g. pharma partner / university PI / defense customer] covering the run of [EXPERIMENT/PRODUCT] on [MISSION]. The reader is [TECHNICAL LEVEL]. Inputs: [OBJECTIVES], [WHAT RAN AS PLANNED], [DEVIATIONS], [PRELIMINARY RESULTS vs GROUND CONTROLS], [NEXT STEPS AND TIMELINE]. Structure: one-paragraph executive summary, results against each objective, anomalies with candid impact assessment, what we learned about the process, and recommendations for the next flight. Keep the tone factual: do not overstate the microgravity benefit when ground controls are inconclusive, and keep confirmed findings separate from preliminary ones.
```

> **Caution:** Do not include export-controlled (ITAR/EAR) data or other customers' proprietary information. Have the report reviewed before release.

## 7. Next-flight run planning

**Task:** Plan process parameters and sample matrix for a limited-capacity future flight

```text
I have [NUMBER] sample slots or [HOURS] of process time on [UPCOMING MISSION], with these constraints: [POWER, THERMAL, CREW TIME, RETURN MASS, MAX DURATION BEFORE REENTRY]. Earlier flights gave these results: [SUMMARY]. Open questions: [LIST]. Propose a design-of-experiments plan that gets the most information from each slot. Include a parameter matrix, matched ground controls, which runs are essential and which are nice to have if capacity is cut, and the decision each result would unlock. Briefly explain the trade-off between exploring new parameters and repeating runs for statistical confidence when flights are scarce.
```

## 8. Upskilling study plan

**Task:** Build a learning plan for moving into in-space manufacturing from a ground role

```text
I am a [CURRENT ROLE, e.g. AM technician / pharma process tech / semiconductor fab tech] and I want to become an in-space manufacturing technician working on [PROCESS FOCUS]. I can study [HOURS/WEEK] for [MONTHS]. Build a study plan covering: microgravity fluid and thermal physics, spacecraft subsystems and telemetry, ISS and commercial payload integration, space quality standards (NASA-STD-6030, ECSS quality standards), FAA Part 450 basics, and contamination control. For each module, name real resources (textbooks, NASA technical reports, ISS research results, open courses) and a hands-on exercise I could do on the ground. Include the companies and programs currently hiring for this kind of work, and say plainly which skills are speculative and which are already in demand.
```

> **Caution:** Check that course and program listings are still current. This field changes quickly.
