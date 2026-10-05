---
name: vertiport-manager
description: "Prompt playbook for a vertiport manager. Use when a vertiport manager wants help with work tasks such as: daily ops briefing from logs; charger turnaround bottleneck analysis; design guidance compliance gap check; battery fire emergency plan update; community noise complaint response; slot allocation policy draft; safety Management System hazard log; upskilling plan for a heliport manager."
---

# Vertiport manager prompts

Runs a takeoff-and-landing site for electric air taxis (eVTOL) and drones: daily operations, charging, safety, slot scheduling with operators like Joby, Archer or Beta, and compliance with emerging FAA (Engineering Brief 105A, powered-lift SFAR), EASA and local fire codes. AI helps most with turning fast-changing guidance into checklists, analysing ops and charging data, drafting reports and community communications, and preparing for audits and emergencies.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily ops briefing from logs

**Task:** Turn overnight logs and today's schedule into a morning operations brief

```text
You are an operations analyst for a vertiport serving eVTOL air-taxi flights. Here are today's flight schedule, overnight maintenance and charger logs, a weather forecast (METAR/TAF), and open NOTAMs: [PASTE DATA]. The site has [NUMBER] FATOs, [NUMBER] stands and [NUMBER] chargers rated [kW]. Produce a one-page morning brief: (1) a table of capacity constraints by hour (stands, chargers, staff), (2) weather or NOTAM items that could affect operations, with the time window, (3) equipment that is out of service and its effect, (4) the top 3 decisions I need to make today. Mark anything you inferred rather than read in the data.
```

> **Caution:** Advisory only; go/no-go and airspace decisions stay with the operator, pilot in command and ATC.

## 2. Charger turnaround bottleneck analysis

**Task:** Find why aircraft turnarounds overrun and what to fix first

```text
Act as an airport turnaround and EV-charging analyst. Attached is [PERIOD] of turnaround data: arrival/departure times, stand, charger ID, state of charge in/out, charge duration, passenger boarding times and delay codes [PASTE CSV]. Target turnaround is [MINUTES]. Identify the main drivers of overruns (charging rate, charger faults, boarding, ground handling, stand conflicts), quantify each in minutes and share of delays, and flag any charger whose delivered power is consistently below its rating. Output: findings table, 2-3 charts I should build (describe axes), and a ranked list of fixes with expected minutes saved. State assumptions and where more data is needed.
```

> **Caution:** Battery thermal or charging anomalies go to the aircraft OEM and charger vendor; do not change charge limits based on this analysis.

## 3. Design guidance compliance gap check

**Task:** Compare a site layout against FAA EB 105A and related guidance

```text
You are a vertiport design reviewer. Our site [LOCATION, ROOFTOP/GROUND] is planned for the [AIRCRAFT TYPE] with a controlling dimension (D) of [VALUE] and max takeoff weight [VALUE]. Here is our layout description: FATO, TLOF, safety area, approach/departure paths, stand separation, charging and fire suppression [PASTE]. Review it against FAA Engineering Brief 105A (Vertiport Design), and where relevant AC 150/5390-2D and NFPA 418. Produce a table: requirement, source section, our design value, status (meets / gap / unclear), and question to ask the FAA or fire marshal. Flag where guidance is interim or still changing and do not quote section numbers you are unsure of.
```

> **Caution:** Verify every citation against the current published documents; final approval rests with the FAA, local authority and a licensed engineer.

## 4. Battery fire emergency plan update

**Task:** Draft or refresh the lithium-ion fire section of the emergency plan

```text
Help me update the emergency response plan for our vertiport, focused on lithium-ion battery fires and thermal runaway in eVTOL aircraft on the pad, at a stand or while charging. Context: [SITE TYPE], fire suppression available [DETAILS], local fire department response time [MINUTES], aircraft OEM emergency response guide notes [PASTE]. Draft: detection triggers, immediate actions by role (vertiport staff, pilot, fire service), isolation of chargers and power, passenger evacuation and muster points, exclusion distances, coordination with ATC/operator, and post-incident reporting. Use a checklist format. Highlight open questions that need sign-off from the fire marshal and OEM, since standards for eVTOL battery fires are still developing.
```

> **Caution:** Must be validated with the local fire authority and aircraft manufacturer and exercised in drills before use.

## 5. Community noise complaint response

**Task:** Reply to a resident complaint and summarise trends for a community meeting

```text
You are the community relations lead for a city vertiport. A resident wrote: [PASTE COMPLAINT]. Our noise monitoring data for that time shows [DATA], and the flight log shows [FLIGHTS]. Our published noise commitments are [COMMITMENTS]. (1) Draft a reply under 200 words that is factual, does not admit or deny liability, explains what we found and what we will do next. (2) Write 5 bullet points summarising complaint trends from this log [PASTE COMPLAINT LOG] for our quarterly neighbourhood meeting, with any patterns by time, route or aircraft type. Avoid jargon and do not overstate how quiet eVTOLs are.
```

> **Caution:** Remove residents' personal details before sharing summaries; legal review for anything touching liability.

## 6. Slot allocation policy draft

**Task:** Design a fair slot and stand allocation scheme across multiple operators

```text
Act as an airport capacity and slot-coordination advisor. Our vertiport will serve [NUMBER] operators ([NAMES OR TYPES]) with peak capacity of [MOVEMENTS/HOUR] limited by [FATOs, chargers, airspace corridors]. Drawing on how IATA Worldwide Airport Slot Guidelines and US slot-controlled airports work, propose a slot and stand allocation policy: allocation rules, use-it-or-lose-it thresholds, priority for medical or emergency flights, how charger time is allocated, and how disputes are resolved. Give two alternative designs with pros/cons, and list the antitrust, open-access or grant-assurance questions I should raise with counsel.
```

> **Caution:** Grant obligations and competition law vary by site and funding; get legal review before publishing.

## 7. Safety Management System hazard log

**Task:** Build and maintain SMS hazard entries using FAA Part 5 style risk assessment

```text
You are a safety management specialist familiar with FAA 14 CFR Part 5 and Part 139 SMS concepts. For our vertiport, help me add hazards for this change: [DESCRIBE CHANGE, e.g. new charger model, night operations, new approach path]. For each hazard give: description, causes, worst credible outcome, existing controls, severity and likelihood using this matrix [PASTE OR 'standard 5x5'], proposed mitigations, owner and review date. Output as a table I can paste into our hazard log. Also list hazards you think I might be missing and data I should collect to monitor each risk.
```

> **Caution:** Risk acceptance is a management decision; the AI's ratings are a starting draft, not an assessment.

## 8. Upskilling plan for a heliport manager

**Task:** Create a learning plan to move from airport or heliport operations into vertiport management

```text
I am a [CURRENT ROLE, e.g. heliport or FBO manager] with experience in [AREAS]. I will be running a vertiport for eVTOL air taxis in [COUNTRY]. Build a 12-week learning plan covering: eVTOL aircraft and powered-lift certification basics, FAA EB 105A and EASA vertiport design specifications, high-power DC charging and electrical safety, UAM airspace concepts (FAA UAM ConOps, UTM), lithium battery fire response, SMS, and community engagement. For each week give objectives, specific public sources to read, and a practical exercise. End with 15 quiz questions with answers. Note which areas are still unsettled so I track updates.
```

> **Caution:** Regulations are evolving quickly; check the latest FAA and EASA publications rather than relying on the plan's dates.
