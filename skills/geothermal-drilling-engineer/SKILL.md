---
name: geothermal-drilling-engineer
description: "Prompt playbook for a geothermal drilling engineer. Use when a geothermal drilling engineer wants help with work tasks such as: daily drilling report review; bit run performance analysis; lost circulation troubleshooting; well program and casing design draft; permit and regulator narrative; induced seismicity plan and briefing; post-well lessons learned report; oil-and-gas to geothermal upskilling plan."
---

# Geothermal drilling engineer prompts

Plans and supervises deep, hot wells for conventional and enhanced geothermal systems (EGS), as at Fervo, Eavor, Sage Geosystems and DOE's Utah FORGE site, adapting oil-and-gas methods to hard, hot granite and fractured reservoirs. AI helps most with reviewing daily drilling reports, comparing bit and penetration-rate data, drafting well programs and permit narratives, preparing seismicity and community communications, and helping oil-and-gas engineers learn high-temperature geothermal practice.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily drilling report review

**Task:** Find trends and issues in a day's drilling data before the morning call

```text
You are a senior geothermal drilling engineer reviewing a daily drilling report for well [WELL NAME], an [EGS / hydrothermal] well in [FORMATION, e.g. granite]. Below are the last [N] hours of data: depth, ROP, WOB, RPM, torque, standpipe pressure, flow in/out, mud temperature in/out, and the driller's comments. [PASTE DATA]. Identify: (1) trends that point to bit wear, stick-slip, losses or gains, or rising return temperature; (2) any readings that look wrong and need checking; (3) three questions for the rig team. Output a short table of findings with evidence and confidence, then a 5-line summary for the morning call. Do not make well-control calls; mark anything urgent for immediate human review.
```

> **Caution:** Advisory only; well control and real-time decisions stay with the rig team and approved procedures.

## 2. Bit run performance analysis

**Task:** Compare PDC bit runs in hard, hot rock to choose the next bit

```text
Act as a drilling optimization engineer for hard-rock geothermal wells. I am comparing bit runs in [FORMATION] at [TEMPERATURE RANGE]. For each run I have bit type, cutter, interval drilled, hours, average ROP, WOB, RPM, mechanical specific energy (if computed), dull grade (IADC), and notes: [PASTE RUN DATA]. Compute or check MSE where the inputs allow, rank the runs by cost per foot using [RIG DAY RATE] and [BIT COST], explain the likely causes of the dull grades, and recommend parameters and bit features for the next run. Show your formulas. Say where the data is too thin to support a conclusion.
```

> **Caution:** Check calculations and recommendations with the bit vendor's engineers and offset well data.

## 3. Lost circulation troubleshooting

**Task:** Work through options when severe losses happen in fractured hot rock

```text
You are advising a geothermal drilling engineer facing [PARTIAL / SEVERE / TOTAL] lost circulation at [DEPTH] in [FORMATION] at about [TEMPERATURE]. Current setup: [MUD SYSTEM, HOLE SIZE, CASING POINT, LOSS RATE, ACTIONS TRIED]. The fractured zone [IS / IS NOT] the production target. Lay out the options: LCM pills, cement plugs, drilling blind or with aerated fluid, setting casing early. For each, give the temperature limits of the materials, the risk to the reservoir's permeability, the well-control and stuck-pipe risks, and rough time and cost. Finish with the decision criteria I should agree with the company man before choosing. Flag anything that depends on vendor data you do not have.
```

> **Caution:** Follow the approved well program and well-control procedures; confirm material temperature ratings with suppliers.

## 4. Well program and casing design draft

**Task:** Draft the outline and design checks for a high-temperature well program

```text
Act as a geothermal well design engineer. Draft an outline for the drilling program for [WELL NAME], target depth [TD], bottomhole temperature [BHT], in [LOCATION]. Inputs: [HOLE SECTIONS, PLANNED CASING SIZES AND GRADES, EXPECTED PRESSURES, H2S/CO2 EXPECTATIONS]. Organize it with headings for each hole section, casing and cementing, BOP and wellhead, mud and cooling, and contingencies. For casing, list the design checks to run: burst, collapse, axial load, and thermal stress from heating and cooling cycles. Reference API 5CT grades and NZS 2403 (deep geothermal wells) where relevant. Mark every number as a placeholder for the engineer to calculate and approve.
```

> **Caution:** A draft only; final design must be calculated, checked and signed by a qualified engineer under the relevant regulator.

## 5. Permit and regulator narrative

**Task:** Draft the technical narrative for a geothermal drilling permit application

```text
You are helping a geothermal drilling engineer write the technical narrative for a drilling permit to [REGULATOR, e.g. BLM under 43 CFR 3260, Nevada Division of Minerals, CalGEM] for [PROJECT] on [FEDERAL / STATE / PRIVATE] land. Project facts: [WELL COUNT, DEPTHS, CASING PLAN, BOP CLASS, WATER SOURCE AND VOLUMES, WASTE HANDLING, NEARBY AQUIFERS]. Write a clear narrative for each section the regulator usually asks for, in plain technical language. Then list the documents and data I still need, and any rules you are unsure apply to this jurisdiction so I can check them with the regulator or counsel. Do not invent rule numbers.
```

> **Caution:** Confirm current requirements with the regulator; rules differ by state and land status.

## 6. Induced seismicity plan and briefing

**Task:** Prepare a seismicity monitoring outline and community briefing for stimulation

```text
Act as a geothermal engineer preparing hydraulic stimulation for an EGS project at [SITE]. Using the DOE Induced Seismicity Protocol for EGS and lessons from Basel, Pohang and Utah FORGE as background, draft: (1) an outline of a traffic light system with the magnitude and ground-motion thresholds as placeholders [THRESHOLDS] and the actions at each level; (2) the monitoring network and data-sharing plan; (3) a one-page briefing for nearby residents and local officials in plain language that explains the risks honestly and says how they can raise concerns. Flag where thresholds need site-specific hazard analysis by a seismologist.
```

> **Caution:** Thresholds and hazard analysis must come from qualified seismologists; do not understate risks to the public.

## 7. Post-well lessons learned report

**Task:** Turn well data and notes into a structured lessons-learned report

```text
You are writing an end-of-well report for [WELL NAME] for the engineering team and investors. Here are the planned vs actual depth-time curve, NPT log, cost summary, and crew notes: [PASTE]. Produce: (1) a one-paragraph executive summary; (2) a table of non-productive time events with cause, hours, cost, and root cause category; (3) the five most important lessons, each with a specific change for the next well; (4) metrics to track across the program, such as days per 1,000 ft and cost per well. Keep blame out of it; focus on systems and procedures. Mark any figure you calculated so I can check it.
```

> **Caution:** Check figures against the official cost and time records before sharing.

## 8. Oil-and-gas to geothermal upskilling plan

**Task:** Build a study plan to move from oil and gas drilling to geothermal

```text
I am a drilling engineer with [YEARS] years in [OIL AND GAS SPECIALTY] moving into geothermal and EGS. Create a 12-week study plan that covers what is different: high-temperature tools and electronics, thermal stress on casing and cement, hard-rock drilling and PDC bits, lost circulation in fractured reservoirs, geothermal fluid chemistry (scale, corrosion, H2S), stimulation and induced seismicity, and how geothermal permitting works in [COUNTRY/STATE]. For each week give the main concepts, two reliable sources (e.g. Stanford Geothermal Workshop papers, DOE FORGE reports, GRC publications, NZS 2403), and one practice exercise using my own data. Say which areas are still changing quickly.
```

> **Caution:** Check that suggested sources exist and are current before relying on them.
