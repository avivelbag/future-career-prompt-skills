---
name: grid-battery-storage-technician
description: "Prompt playbook for a grid battery storage technician. Use when a grid battery storage technician wants help with work tasks such as: cell imbalance triage from BMS data; pCS / inverter fault troubleshooting tree; thermal event incident report; fire department pre-incident briefing; nFPA 855 / AHJ inspection readiness check; capacity fade and augmentation plan; commissioning and maintenance work package; upskilling plan and study coach."
---

# Grid battery storage technician prompts

Grid battery storage technicians commission, maintain and troubleshoot utility-scale battery energy storage systems (BESS), such as containerized lithium-ion (mostly LFP) sites owned by utilities, independent power producers and O&M contractors. The work spans battery management system (BMS) data, power conversion systems (PCS), fire safety under NFPA 855 and UL 9540/9540A, and grid-interconnection rules. AI helps most with reading BMS and SCADA trends, drafting work orders and incident reports, preparing for inspections and studying for certifications. Lockout/tagout and energized-work decisions stay with qualified people.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Cell imbalance triage from BMS data

**Task:** Analyze BMS exports to rank likely causes of a rack's voltage or temperature drift

```text
You are a senior BESS O&M engineer coaching a field technician. Here is a BMS export for [SITE / CONTAINER / RACK ID] ([CHEMISTRY, e.g. LFP], [OEM/MODEL]) covering [TIME RANGE]: [PASTE CSV OR SUMMARY: cell/module voltages, temperatures, SOC, current, balancing status, alarms]. Ambient and HVAC conditions: [DETAILS]. Identify outlier modules or cells, distinguish a sensor or harness fault from real cell degradation, balancing problems and thermal-management problems, and rank the likely causes with the evidence for each. Output: (1) a findings table (module, metric, deviation, interpretation); (2) ranked hypotheses; (3) non-invasive checks to run next, in order; (4) conditions that mean the rack should be isolated now and escalated to the OEM.
```

> **Caution:** Analysis of pasted data only; follow OEM procedures and site LOTO before opening any rack, and escalate thermal-runaway warning signs immediately.

## 2. PCS / inverter fault troubleshooting tree

**Task:** Build a step-by-step diagnostic plan for a recurring PCS trip

```text
Act as a power electronics field engineer for grid-scale storage. A PCS ([MAKE/MODEL], [RATING]) at [SITE] keeps tripping with fault code(s) [CODES], usually during [OPERATING CONDITION, e.g. high-rate discharge, grid voltage sag, cold morning start]. Recent events: [FIRMWARE CHANGES, GRID EVENTS, MAINTENANCE]. Build a diagnostic decision tree that starts with data review (event logs, SCADA, grid-side ride-through settings under IEEE 1547-2018 or [APPLICABLE GRID CODE]) and only then moves to physical checks. For each branch, state the required PPE/energy state per NFPA 70E, the tools needed, and what result points where. Flag any step that needs the OEM or the utility's protection engineer. Format as a numbered tree plus a one-page summary.
```

> **Caution:** Fault-code meanings vary by OEM; verify against the manufacturer's manual. Energized work needs a qualified person and an energized work permit.

## 3. Thermal event incident report

**Task:** Draft a factual incident report after an off-gas, smoke or thermal alarm

```text
Help me draft an incident report for a [EVENT TYPE: off-gas detection / smoke alarm / thermal runaway / suppression discharge] at [SITE], [CONTAINER/ENCLOSURE ID], on [DATE/TIME]. Here are my notes, alarm logs and timeline: [PASTE]. Responders involved: [FIRE DEPT, OEM, UTILITY]. Use these sections: summary, timeline (timestamped, sourced), system state before the event, detection and protection response (gas detection, ventilation/explosion control per NFPA 68/69, suppression), actions taken, injuries/exposure, environmental release, open questions, and preliminary contributing factors. Keep facts separate from hypotheses and mark every inference as such. Do not assign root cause. End with a list of the evidence to preserve and the records the AHJ, insurer or OEM may request.
```

> **Caution:** Have it reviewed by your safety lead and legal before submission; reporting duties and deadlines vary by jurisdiction and contract.

## 4. Fire department pre-incident briefing

**Task:** Prepare a plain-language site briefing for local first responders

```text
I'm a BESS technician preparing a pre-incident planning walk-through for [FIRE DEPARTMENT] at our [MWh / MW] site at [LOCATION], which uses [ENCLOSURE TYPE / OEM] with [SUPPRESSION AND DETECTION SYSTEMS]. Using our emergency response plan and hazard mitigation analysis summary [PASTE], write a 2-page briefing for firefighters: site layout and access, emergency shutdown locations, the hazards of lithium-ion thermal runaway (flammable/toxic off-gas, re-ignition, stranded energy), why defensive tactics and keeping enclosure doors closed are often recommended, the remote monitoring data we can share, and 24/7 contacts. Use plain language, no marketing. Add 5 questions firefighters are likely to ask, with answers grounded only in the documents I provided, and flag any gaps.
```

> **Caution:** Tactics are the fire department's decision; this must match your approved ERP and the UL 9540A test data for your system.

## 5. NFPA 855 / AHJ inspection readiness check

**Task:** Build an inspection checklist and gap list before a fire-code or insurer inspection

```text
You are a code-compliance advisor for energy storage. Our site at [JURISDICTION] has [SYSTEM DESCRIPTION: capacity, chemistry, indoor/outdoor, enclosure spacing]. The AHJ has adopted [NFPA 855 EDITION / IFC EDITION / LOCAL AMENDMENTS], and there is an upcoming [AHJ / INSURER / UTILITY] inspection on [DATE]. From the documentation list I have [PASTE: UL 9540 listing, UL 9540A report, HMA, ERP, commissioning records, maintenance logs, signage], create an inspection-readiness checklist grouped by topic (listings, separation, detection/suppression, explosion control, signage, ERP, training records, maintenance). Mark each item as have / missing / unclear. Cite clause numbers only when you are confident they're right, and otherwise say 'verify clause'. List anything where local amendments commonly differ.
```

> **Caution:** Code editions and local amendments differ; the AHJ's interpretation governs. Check every clause citation against the adopted text.

## 6. Capacity fade and augmentation plan

**Task:** Turn capacity test results into a degradation trend and augmentation recommendation

```text
Act as a storage asset performance analyst. Site [NAME] has a contracted capacity of [MW / MWh] under [CONTRACT TYPE: RA, tolling, PPA] with a guarantee of [TERMS]. Annual capacity test results and cycling history: [PASTE: dates, measured MWh, RTE, cycles, avg SOC window, temperatures]. Estimate the degradation trend (show the method and its uncertainty), project when we fall below the guarantee, and compare options: augmentation with new modules, changing the SOC window or dispatch, or doing nothing. For each option give pros, cons, key risks (mixing old and new cells, BMS compatibility, re-listing or re-permitting) and the data still needed. Output a table plus a short memo for my asset manager.
```

> **Caution:** Projections are rough without the OEM degradation model and warranty terms; confirm with the OEM and the asset owner.

## 7. Commissioning and maintenance work package

**Task:** Draft a step-by-step procedure or method statement for a planned job

```text
Draft a method statement and work procedure for [TASK: e.g. replacing a battery module, annual HVAC/thermal service, torque and IR scan of DC busbars, BMS firmware update] on [OEM / SYSTEM] at [SITE]. Inputs: OEM manual excerpts [PASTE], site rules [PASTE], crew size [N], expected outage window [HOURS]. Include scope, prerequisites and permits, hazards and controls (arc flash and shock per NFPA 70E, DC stranded energy, lifting, off-gas), isolation and LOTO points, numbered steps with hold points and acceptance values, return-to-service checks, and the SCADA/dispatch notifications needed before and after. Put [VERIFY] wherever a value is missing from the documents I gave you. Never fill in torque, voltage or setting values yourself.
```

> **Caution:** This is a draft; the procedure must be approved by the qualified person and match OEM instructions exactly.

## 8. Upskilling plan and study coach

**Task:** Build a learning plan and quiz for BESS certification or a new technology

```text
I'm a [CURRENT ROLE, e.g. solar tech / industrial electrician / lineworker] moving into grid battery storage. My background is [SKILLS] and my goal is [GOAL: e.g. NABCEP Energy Storage Installation Professional certification, OEM certification for [OEM], lead commissioning tech]. Build a 12-week study plan covering battery electrochemistry and failure modes (LFP vs NMC, plus emerging sodium-ion and flow batteries), BMS/PCS/EMS architecture, UL 9540/9540A/1973, NFPA 855 and 70E, IEEE 1547 basics, and market dispatch (frequency regulation, energy arbitrage). For each week, give objectives, recommended free or official sources by name (I will check that they exist), and a hands-on exercise. Then quiz me with 10 scenario questions on this week's topic, one at a time, explaining my mistakes.
```

> **Caution:** Check exam blueprints and source names against the official certification body; Claude may misremember edition details.
