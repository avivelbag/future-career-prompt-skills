---
name: urban-air-mobility-pilot
description: "Prompt playbook for an urban air mobility pilot. Use when an urban air mobility pilot wants help with work tasks such as: pre-flight route and energy briefing; powered-lift regulation study guide; abnormal procedure drill builder; post-flight debrief and safety report; battery and performance trend analysis; passenger briefing and delay messaging; community noise and route explainer; future autonomy and multi-aircraft supervision prep."
---

# Urban air mobility pilot prompts

Flies piloted eVTOL and powered-lift air taxis (Joby, Archer, Beta, EHang-style operations) on short urban routes between vertiports under emerging rules such as the FAA powered-lift SFAR (14 CFR Part 194), EASA's VTOL framework and FAA Engineering Brief 105A for vertiports, and later may supervise multiple autonomous aircraft. AI helps most with route and energy-reserve planning, briefing prep, studying fast-changing regulations and type-specific systems, debriefs and safety reports, and passenger communication, while the pilot keeps full command authority.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Pre-flight route and energy briefing

**Task:** Build a structured pre-departure brief for an urban eVTOL sector.

```text
You are a briefing assistant for a commercial eVTOL pilot flying [AIRCRAFT TYPE] from [DEPARTURE VERTIPORT] to [ARRIVAL VERTIPORT]. Using the data I paste below (METAR/TAF, winds aloft, NOTAMs/TFRs, planned route, payload, battery state of charge and the operator's energy reserve policy), produce a one-page brief with: 1) weather and wind hazards relevant to low-altitude urban flight (gusts, building-induced turbulence, density altitude); 2) relevant NOTAMs and TFRs; 3) an energy plan comparing expected consumption plus required reserve against available charge, with diversion options; 4) go/no-go flags. Mark any number you estimated rather than read from my data. Data: [PASTE DATA]
```

> **Caution:** Advisory only; verify against the operator's approved flight planning tools, the AFM and official weather/NOTAM sources. The PIC makes the go/no-go decision.

## 2. Powered-lift regulation study guide

**Task:** Learn the current certification and operating rules for powered-lift pilots.

```text
Act as a ground-school instructor. I am a [CURRENT CERTIFICATES, e.g. commercial helicopter / ATP airplane] pilot moving to powered-lift operations in [COUNTRY/REGULATOR]. Explain the current path to a powered-lift rating and type rating, citing the actual rules (e.g. FAA SFAR Part 194 and related Parts 61/91/135 provisions, or EASA's VTOL operations rules), including training, experience, simulator credit and instructor requirements. Present it as: a summary table, a step-by-step plan for my background, and 10 self-quiz questions with answers. Clearly flag anything that is proposed, recently changed, or that you are uncertain about, and list which official documents I should read to confirm.
```

> **Caution:** Rules for powered-lift are new and changing; confirm every requirement against the current regulation text and your operator's training program.

## 3. Abnormal procedure drill builder

**Task:** Turn operator checklists into scenario drills for recurrent practice.

```text
You are a training captain for [AIRCRAFT TYPE] eVTOL operations. Based only on the operator procedures I paste below, create [NUMBER] scenario-based drills for abnormal and emergency situations such as [e.g. loss of one or more lift motors, battery thermal warning, flight control degradation, lost C2/datalink, vertiport pad blocked on short final]. For each drill give: the setup and phase of flight, cues the pilot would see, the expected actions in order (quoting my procedures), key decision points, and debrief questions. Do not invent procedures; if my text does not cover a situation, say so and list it as a gap to raise with the training department. Procedures: [PASTE PROCEDURES]
```

> **Caution:** For study and simulator prep only; the approved AFM/QRH always takes precedence.

## 4. Post-flight debrief and safety report

**Task:** Draft a factual safety report after an event or anomaly.

```text
Help me write a safety report for my operator's SMS (and, if applicable, a draft for NASA ASRS or [OTHER REPORTING SYSTEM]). Event notes: [DATE, ROUTE, AIRCRAFT, PHASE OF FLIGHT, WHAT HAPPENED, ATC/VERTIPORT COMMS, WEATHER, CREW ACTIONS, OUTCOME]. Produce: a neutral chronological narrative, contributing factors grouped as human / aircraft / environment / organizational (e.g. using a HFACS-style lens), immediate actions taken, and suggested corrective actions. Keep the language factual and non-speculative, mark assumptions, and list questions I should answer before submitting. Remove passenger personal data.
```

> **Caution:** Check your operator's reporting deadlines and NTSB/authority immediate-notification rules (e.g. 49 CFR 830) separately; do not paste data your company policy forbids sharing.

## 5. Battery and performance trend analysis

**Task:** Spot patterns in energy use and battery data across many sectors.

```text
You are a data analyst supporting an eVTOL pilot. Below is a CSV export of my recent sectors with columns [e.g. date, route, payload, OAT, wind, takeoff SOC, landing SOC, cruise time, hover time, max cell temp]. Analyze: energy consumed per sector vs. payload, wind and temperature; outliers where landing state of charge was closer to the reserve minimum than usual; any upward trend in hover time or cell temperature that could matter for planning. Output a short findings list, a table of flagged sectors, and questions to raise with maintenance or flight ops. Explain your method and do not overstate conclusions from small samples. Data: [PASTE CSV]
```

> **Caution:** Pilot-side observations only; battery health and airworthiness determinations belong to maintenance and the manufacturer.

## 6. Passenger briefing and delay messaging

**Task:** Write clear passenger safety briefings and disruption announcements.

```text
Write passenger communications for a [NUMBER]-seat air taxi on the [ROUTE] service. Produce: 1) a 60-second spoken safety briefing covering seatbelts, headsets, doors, emergency exits and what to expect during vertical takeoff and transition, consistent with these required items from our operations manual: [PASTE REQUIRED ITEMS]; 2) three short announcements for a weather hold, a diversion to [ALTERNATE VERTIPORT], and a battery-charging delay. Tone: calm, plain English, reading level about grade 8, no promises about times we cannot keep. Also give a [SECOND LANGUAGE] version of the safety briefing.
```

> **Caution:** The approved operations manual's required briefing content governs; have translations checked by a fluent speaker.

## 7. Community noise and route explainer

**Task:** Prepare a pilot's talking points for a community meeting about air taxi routes.

```text
I am a line pilot asked to speak at a [CITY] community meeting about a proposed air taxi route over [NEIGHBORHOODS] to a vertiport at [LOCATION]. Using the facts I provide (route altitudes, flight frequency, published noise data from the manufacturer, curfew hours, safety record so far): [PASTE FACTS], draft 5-minute talking points and an FAQ of 10 likely resident questions with honest answers on noise, privacy, safety, emergency landing options and who regulates what (FAA/local authorities). Distinguish clearly between facts I supplied, general industry information, and open questions still being decided. Avoid marketing language.
```

> **Caution:** Get public statements approved by your operator's communications and legal teams before speaking.

## 8. Future autonomy and multi-aircraft supervision prep

**Task:** Learn what supervising remotely piloted or autonomous air taxis would involve.

```text
Act as a career mentor for an urban air mobility pilot preparing for a possible shift from onboard piloting to supervising [NUMBER] autonomous or remotely piloted aircraft from a ground station (as companies such as Wisk and EHang are pursuing). Explain: how today's analogues work (e.g. FAA BVLOS rulemaking under proposed Part 108, UTM/UAM concepts of operations, EHang's operations in China), which human-factors risks matter most (automation complacency, mode confusion, alert overload, handoffs), and what skills and certifications I should build over the next [TIMEFRAME]. Output a 12-month learning plan with resources. Clearly separate what exists today from what is proposed or speculative.
```

> **Caution:** This area is largely unregulated or in rulemaking; treat forecasts as uncertain and verify the current status of any proposal.
