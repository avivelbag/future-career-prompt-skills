---
name: carbon-removal-plant-operator
description: "Prompt playbook for a carbon removal plant operator. Use when a carbon removal plant operator wants help with work tasks such as: capture rate drift diagnosis; mRV net removal report; shift handover note; community open-house Q&A; energy-aware run scheduling; cO2 hazard and PSM review; certification and incentive landscape; incident and deviation report."
---

# Carbon removal plant operator prompts

Runs direct air capture (DAC) and similar carbon removal facilities, such as Climeworks' Orca and Mammoth in Iceland, Heirloom in California and 1PointFive's Stratos in Texas, keeping capture, regeneration, compression and handoff to storage running safely while producing the measurement, reporting and verification (MRV) data that credits and 45Q tax credits depend on. AI helps most with troubleshooting performance drift, turning sensor logs into audit-ready MRV reports, writing shift handovers and procedures, and learning the fast-changing certification rules.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Capture rate drift diagnosis

**Task:** Troubleshoot a drop in tonnes captured per cycle

```text
You are a process engineer experienced with direct air capture plants using [SORBENT TYPE, e.g. amine-functionalized solid sorbent / liquid KOH-calcium loop / limestone mineralization]. Over [TIME PERIOD], our capture per cycle fell from [BASELINE t/cycle] to [CURRENT t/cycle]. Context: ambient temperature [RANGE], relative humidity [RANGE], fan power [kW], regeneration temperature [°C], steam or heat input [VALUE], product CO2 purity [%], cycles since last sorbent replacement [NUMBER]. Recent changes: [MAINTENANCE/CONTROL CHANGES]. Give a ranked list of likely causes (e.g. sorbent degradation, humidity effects, air bypass, incomplete desorption, sensor drift), the specific data or test that would confirm or rule out each, and which checks are safe to do while running versus needing a shutdown. Say clearly where you're unsure.
```

> **Caution:** Diagnostic ideas only; follow site lockout/tagout and management-of-change procedures before acting.

## 2. MRV net removal report

**Task:** Draft a monthly measurement, reporting and verification summary

```text
Act as an MRV specialist for carbon dioxide removal. Using the data below, draft a monthly net-removal report for [REGISTRY/PROTOCOL, e.g. Puro.earth, Isometric, EU CRCF methodology]. Data: gross CO2 captured [t], CO2 delivered to storage partner [t, with meter IDs], storage confirmation from [STORAGE OPERATOR, e.g. Carbfix, Class VI well operator], grid and onsite energy use [MWh by source], emission factors used [VALUES AND SOURCES], embodied/consumable emissions [t CO2e], venting or losses [t]. Output: (1) a net removal calculation table showing each deduction, (2) data gaps or assumptions an auditor would challenge, (3) a short narrative summary. Don't invent emission factors; mark any missing value as [NEEDED].
```

> **Caution:** Registry methodologies change; check the current version, and a qualified verifier must sign off before credits are issued.

## 3. Shift handover note

**Task:** Turn shift logs into a clear handover

```text
You are the control room lead at a carbon removal facility. Turn my raw shift notes and alarm log into a handover for the next shift. Notes: [PASTE NOTES]. Alarm/event log: [PASTE]. Format: (1) plant status at handover (units online/offline, capture rate, compressor and storage-delivery status), (2) open issues ranked by safety then production impact, (3) work permits and isolations still in place, (4) actions the incoming shift must take, with times, (5) anything unresolved or ambiguous that needs a phone call. Keep it to one page and use plain language. Don't drop any isolation or permit that appears in the notes.
```

> **Caution:** Check the result against the official permit-to-work and isolation registers; this is not a replacement for them.

## 4. Community open-house Q&A

**Task:** Prepare honest answers for neighbors and local officials

```text
I operate a [TYPE] carbon removal plant near [COMMUNITY], which stores CO2 via [STORAGE METHOD, e.g. Class VI saline injection well / basalt mineralization / pipeline to a partner]. We are holding a public meeting. Expected concerns: [LIST, e.g. CO2 leaks, pipeline safety, water use, noise, whether this is 'greenwashing' for oil recovery, local jobs]. For each one, write a 2-4 sentence answer in plain language that is honest about the risks and tradeoffs, cites the relevant oversight where it applies (e.g. EPA UIC Class VI permits, PHMSA pipeline rules, state agencies), and flags where I should give site-specific numbers [PLACEHOLDER]. Also list 3 questions I should be ready for that I haven't thought of.
```

> **Caution:** Communications staff and legal should review; never promise zero risk.

## 5. Energy-aware run scheduling

**Task:** Plan operation around variable power prices and carbon intensity

```text
Help me plan next week's operation of a DAC plant whose net removal depends on low-carbon power. Inputs: forecast hourly grid carbon intensity [SOURCE/DATA], power price [DATA], onsite renewable forecast [DATA], plant minimum turndown [%], startup/shutdown penalties [ENERGY, TIME, SORBENT WEAR], storage-delivery limits [t/day], and contract delivery target [t for week]. Propose an operating schedule (as a table by day and time block) that meets the target while minimizing lifecycle emissions and cost, explain the tradeoffs, and show how the net removal figure changes compared with running flat out. List the assumptions I should confirm with the grid operator or our energy desk.
```

> **Caution:** This is a planning aid; dispatch decisions stay with the operator, within grid and permit constraints.

## 6. CO2 hazard and PSM review

**Task:** Check a procedure for compression and high-concentration CO2 hazards

```text
Act as a process safety reviewer. Review this operating procedure for [TASK, e.g. compressor restart, sorbent module changeout, entry to a regeneration chamber] at a carbon removal plant: [PASTE PROCEDURE]. Check it for hazards from concentrated CO2 (asphyxiation, pooling in low areas, monitor placement), high-pressure and supercritical CO2, hot surfaces and steam, chemicals in use [LIST], and confined space entry. Map gaps to the relevant requirements in [JURISDICTION, e.g. OSHA 1910.146 confined spaces, 1910.119 PSM if applicable, site standards]. Output a table of each hazard, the existing control, the gap, and a suggested fix, then a list of questions for the site safety engineer.
```

> **Caution:** Not a substitute for a formal HAZOP or the safety engineer's sign-off.

## 7. Certification and incentive landscape

**Task:** Learn which rules and credit schemes apply to my plant

```text
I'm a new operator at a [TECHNOLOGY] carbon removal plant in [COUNTRY/STATE] selling removals to [BUYERS, e.g. Frontier members, voluntary market, compliance buyers]. Explain the current landscape that affects my daily data and operations: relevant tax credits (e.g. US 45Q and its MRV requirements, EPA GHGRP Subpart RR), certification frameworks (EU CRCF, Puro.earth, Isometric, ISO 27914 for storage), and storage permitting. For each one, give: what it requires from operators, which records I must keep, and how certain or in-flux it is as of your knowledge cutoff. End with a 4-week study plan and primary sources to read. Flag anything that may have changed recently.
```

> **Caution:** Policy changes fast; check against official agency and registry documents.

## 8. Incident and deviation report

**Task:** Write a root-cause report after an unplanned event

```text
You are helping me write an incident report for a carbon removal facility. Event: [DESCRIPTION, e.g. CO2 release at compressor seal, off-spec CO2 rejected by storage partner, extended outage]. Timeline: [PASTE]. Readings and alarms: [PASTE]. People involved by role only: [ROLES]. Produce: (1) a factual timeline, (2) a root-cause analysis using 5 Whys and a fishbone across equipment, procedure, people, environment, (3) the effect on reported tonnes and whether MRV records or registry submissions need correcting, (4) corrective actions with owners and dates [PLACEHOLDER], (5) whether this may be reportable to [REGULATOR/STORAGE PERMIT HOLDER] — list the questions to confirm, don't decide it. Don't speculate beyond the evidence.
```

> **Caution:** Regulatory reporting obligations and deadlines must be confirmed by compliance staff.
