---
name: propellant-depot-operator
description: "Prompt playbook for a propellant depot operator. Use when a propellant depot operator wants help with work tasks such as: shift telemetry triage; transfer procedure review; anomaly report draft; boil-off and inventory planning; regulatory and licensing map; client readiness briefing; proximity operations hazard analysis; cryogenic fluid management study plan."
---

# Propellant depot operator prompts

Runs orbital refueling depots and tanker missions: monitoring cryogenic or storable propellant inventory and boil-off, planning and executing transfers to client spacecraft, and handling safety, debris and licensing compliance. Closest today: SpaceX's Starship ship-to-ship transfer for Artemis HLS, Orbit Fab's RAFTI-equipped tankers, and NASA's Cryogenic Fluid Management Tipping Point demos (e.g. Eta Space LOXSAT). AI helps most with telemetry triage, transfer-procedure drafting, anomaly write-ups, client and regulator documentation, and getting up to speed on cryogenic fluid management.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Shift telemetry triage

**Task:** Summarize depot health telemetry into a shift handover with flagged trends

```text
You are supporting an operator on a [DEPOT/TANKER NAME] carrying [PROPELLANT, e.g. LOX/LCH4, hydrazine, xenon]. Below is a telemetry export for the last [TIME WINDOW]: tank pressures, ullage and wall temperatures, fill levels, heater and cryocooler status, attitude, and any fault flags. [PASTE DATA OR SUMMARY]. Nominal ranges: [LIMITS TABLE]. Produce a shift handover with: (1) a one-paragraph status, (2) a table of parameters outside limits or trending toward them, with rate of change and projected time to limit, (3) estimated boil-off or leak rate compared to the [BASELINE], and (4) items needing a decision from the next shift. Do not invent values; mark gaps in the data explicitly.
```

> **Caution:** Advisory only: limit violations must be confirmed against the flight software and handled per approved flight rules, not AI output.

## 2. Transfer procedure review

**Task:** Check a propellant transfer procedure for gaps before a client refueling

```text
Act as a second reviewer on an on-orbit propellant transfer procedure. Context: depot [NAME], client vehicle [NAME], interface [e.g. Orbit Fab RAFTI, custom coupler], propellant [TYPE], planned quantity [KG], transfer method [pressure-fed, pump, settling burn]. Procedure text: [PASTE]. Review it step by step and return a table: step number, issue (missing hold point, unclear go/no-go criterion, missing abort path, unverified valve state, settling or ullage-gas ingestion risk, interface leak check), why it matters, and suggested wording. Then list the abort and safing paths you'd expect to see that are absent. Flag anything that depends on unknown hardware behavior as an open question for engineering.
```

> **Caution:** The procedure needs formal review and approval by the operator's engineering and safety boards; this review only adds to that process.

## 3. Anomaly report draft

**Task:** Turn raw notes on an off-nominal event into a structured anomaly report

```text
Help me draft an anomaly report for a [depot/tanker] event. Notes, timeline and telemetry excerpts: [PASTE]. Structure it as: title; event summary; timeline (UTC); observed vs expected behavior; immediate actions taken; current vehicle state and propellant inventory impact; candidate root causes ranked by likelihood with the evidence for and against each; data still needed to discriminate; recommended corrective actions; and effect on upcoming client transfers [LIST]. Use a fault-tree style for the root causes. Keep my words where they are factual and label your inferences as hypotheses.
```

> **Caution:** Root-cause conclusions must come from the investigation team; treat AI-ranked causes as hypotheses to test.

## 4. Boil-off and inventory planning

**Task:** Plan a propellant inventory and resupply schedule around losses and client demand

```text
You are a mission planner for a cryogenic propellant depot in [ORBIT, e.g. LEO 400 km 51.6 deg / NRHO]. Inputs: current inventory [KG per propellant], measured or estimated boil-off rate [%/day or kg/day], whether there is active cooling [ZBO/RBO cryocooler capacity], tanker arrival options [DATES, quantities], and client demand [LIST of vehicle, date, quantity, margin required]. Build a 90-day inventory table, identify dates where reserves fall below [RESERVE POLICY], and propose two alternative schedules with tradeoffs. Show your arithmetic and state each assumption. Note where boil-off estimates for this tank size are poorly characterized in flight data.
```

> **Caution:** Check all numbers against the team's thermal and flight dynamics models before committing to customers.

## 5. Regulatory and licensing map

**Task:** Map the licenses, filings and standards a refueling mission touches

```text
I work for [COMPANY], a [US/other]-licensed operator planning a refueling mission: [BRIEF MISSION DESCRIPTION, orbit, client, propellant, RPO and docking]. Map the regulatory and standards landscape as a table: authority or standard (e.g. FCC Part 25 including its 5-year post-mission disposal rule and its 2024 in-space servicing (ISAM) proceedings, FAA/AST Part 450 for launch/reentry, NOAA remote sensing if cameras are used, ITAR/EAR export controls on the client interface, CONFERS principles, ISO 24330 for rendezvous and proximity operations, the Artemis Accords for cislunar work), what it requires of us, filing or timing, and open questions. Flag clearly where rules for on-orbit servicing are still being written or untested, and where I need counsel.
```

> **Caution:** Not legal advice; regulations change, so verify current text and have licensing counsel confirm before filing.

## 6. Client readiness briefing

**Task:** Explain a refueling service and its requirements to a prospective client team

```text
Write a briefing for the engineering team at [CLIENT COMPANY], whose spacecraft [NAME/BUS] is considering refueling from our depot. Our service: [INTERFACE, propellant, delivery quantity, pressure and temperature at interface, RPO approach and capture method]. Their vehicle: [WHAT WE KNOW]. Cover: what the refueling sequence looks like from their side, interface and design-in requirements, data we need from them (ICD inputs, keep-out zones, attitude control during mated ops, contamination limits), liability and insurance points to resolve, and a realistic timeline to first transfer. 2 pages, plain technical language, and list questions they should ask us.
```

> **Caution:** Export-controlled technical data (ITAR/EAR) must not be shared with foreign persons without authorization; run the final version through export review.

## 7. Proximity operations hazard analysis

**Task:** Draft a hazard analysis for rendezvous, mating and transfer

```text
Help me build a first-draft hazard analysis for rendezvous, docking and propellant transfer between [DEPOT] and [CLIENT]. Phases: approach, capture, leak check, transfer, demate, departure. For each phase, list hazards (collision, plume impingement, propellant leak or freeze-up at the coupler, overpressurization, loss of comms, unintended separation, debris generation, toxic propellant contamination for hydrazine/NTO), causes, effects, existing controls, recommended additional controls, and severity/likelihood using [RISK MATRIX]. Format as a table compatible with a NASA-style hazard report (e.g. NASA-STD-8719 safety practices). Mark items needing test data.
```

> **Caution:** Starting draft only; hazard closure requires the safety review board and real test and analysis evidence.

## 8. Cryogenic fluid management study plan

**Task:** Get up to speed on the physics and history of in-space propellant transfer

```text
I'm a [BACKGROUND, e.g. satellite ops engineer] moving into propellant depot operations and need to learn cryogenic fluid management. Build an 8-week study plan covering: microgravity fluid behavior and propellant settling, thermal stratification and boil-off, MLI and active cooling, chilldown and no-vent fill, mass gauging in zero-g, and storable vs cryogenic tradeoffs. For each week give core concepts, 2-3 sources to look up (NASA CFM program reports, the Centaur and ISS experiments, NASA's Tipping Point demos, SpaceX HLS ship-to-ship transfer), a self-test question, and a practical exercise like estimating boil-off for [TANK SIZE]. Tell me where you are unsure a source exists so I can verify it.
```

> **Caution:** Verify cited reports exist before relying on them; AI can misremember document titles and numbers.
