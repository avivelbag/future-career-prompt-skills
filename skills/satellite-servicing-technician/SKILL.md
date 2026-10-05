---
name: satellite-servicing-technician
description: "Prompt playbook for a satellite servicing technician. Use when a satellite servicing technician wants help with work tasks such as: docking procedure draft; telemetry anomaly triage; rPO safety compliance check; licensing and filings checklist; client service report; robotic tool task rehearsal plan; stakeholder explainer on servicing; upskilling study plan."
---

# Satellite servicing technician prompts

Satellite servicing technicians plan, rehearse and support on-orbit inspection, docking, life extension, refuelling and repair of satellites, usually from a ground operations center. Today's closest examples are Northrop Grumman SpaceLogistics' MEV missions, Astroscale's ELSA-d and ADRAS-J, and Starfish Space's Otter. AI helps most with procedure drafting, telemetry anomaly triage, RPO safety and compliance paperwork (CONFERS, ISO 24330, FCC/NOAA licensing), client reporting and upskilling in orbital mechanics and robotics.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Docking procedure draft

**Task:** Turn a servicing plan into a step-by-step operations procedure with hold points

```text
You are a senior on-orbit servicing operations engineer. Draft a ground operations procedure for the [PHASE, e.g. final approach from 80 m hold to capture] of a servicer docking with [CLIENT SATELLITE TYPE / INTERFACE, e.g. GEO comsat liquid apogee engine nozzle]. Inputs: [APPROACH CORRIDOR, KEEP-OUT SPHERE RADIUS, SENSOR SUITE, COMM WINDOWS, ABORT CRITERIA]. Output a numbered procedure table with columns: step, actor (flight director / RPO operator / robotics operator), command or action, expected telemetry, go/no-go criterion, and contingency/abort branch. Mark every hold point and required two-person verification. List any inputs you had to assume as [TBD] instead of inventing values.
```

> **Caution:** Draft only; it must go through the mission's formal procedure review, simulation and sign-off before flight use.

## 2. Telemetry anomaly triage

**Task:** Rank likely causes of an off-nominal reading during proximity operations

```text
Act as an anomaly resolution lead for a satellite servicing mission. During [MISSION PHASE], we saw: [TELEMETRY EXCERPT / DESCRIPTION, e.g. relative range rate drifting 2 cm/s above plan, lidar dropouts, thruster X temperature rise]. Vehicle context: [GNC SENSORS, PROPULSION TYPE, CURRENT RANGE TO CLIENT]. Produce: (1) a fault tree of candidate causes ranked by likelihood, (2) the specific telemetry or test that would confirm or rule out each, (3) immediate safe-state recommendations consistent with our abort rules [PASTE RULES], and (4) questions to ask the vehicle subject-matter experts. Separate what the data shows from what you are inferring.
```

> **Caution:** Abort and safing decisions stay with the flight director; never delay a rule-mandated abort to wait for analysis.

## 3. RPO safety compliance check

**Task:** Check a mission plan against CONFERS and ISO 24330 practices

```text
You are a space safety reviewer familiar with the CONFERS Recommended Design and Operational Practices, ISO 24330:2022 (rendezvous and proximity operations and on-orbit servicing), and the NASA Spacecraft Conjunction Assessment and Collision Avoidance Best Practices Handbook. Review this servicing mission concept: [SUMMARY: orbit regime, client consent status, approach strategy, passive safety of trajectories, collision-avoidance process, data sharing with 18th SDS/space-track, disposal plan]. Output a table: practice area, what the plan does, gap or risk, and suggested mitigation. Flag where you are unsure of a standard's exact wording so I can check the source text.
```

> **Caution:** Voluntary standards; confirm the current text of each standard and your licence conditions. This does not replace a formal safety review.

## 4. Licensing and filings checklist

**Task:** Map regulatory filings needed for a servicing mission

```text
Act as a regulatory affairs advisor for a [COUNTRY]-licensed satellite servicing operator. Mission: [SERVICER + CLIENT, ORBIT, ACTIVITIES, e.g. docking, imaging the client, refuelling, deorbit]. List the approvals and filings likely needed, e.g. FCC spectrum and orbital-debris showings (including the 5-year LEO disposal rule if applicable), NOAA commercial remote sensing licensing for imaging other objects, FAA payload review if relevant, ITU coordination, export controls (ITAR/EAR), client consent and liability agreements, and insurance. Output a checklist with agency, trigger, typical lead time, and documents to prepare. Mark items where rules are in flux (e.g. FCC in-space servicing proceedings, mission authorization) as open questions.
```

> **Caution:** Not legal advice; confirm with regulatory counsel and the agencies, since in-space servicing rules are still evolving.

## 5. Client service report

**Task:** Write a post-operation report for the satellite owner and insurer

```text
You are writing a customer-facing post-service report for [CLIENT OPERATOR] after [OPERATION, e.g. docking and station-keeping hand-over / refuelling transfer]. Inputs: [TIMELINE OF EVENTS, KEY TELEMETRY, DELTA-V USED, CLIENT SUBSYSTEM STATUS BEFORE/AFTER, ANOMALIES AND RESOLUTIONS, NEXT STEPS]. Produce: an executive summary (5 sentences max), a timeline table, a technical results section, an anomaly section with root cause status (confirmed / suspected / open), and the effect on the client's remaining mission life. Use plain, precise language suitable for the client's engineers and their insurer. Do not include export-controlled detail from [LIST OF RESTRICTED TOPICS].
```

> **Caution:** Have export-control and legal review the report before release; don't overstate root-cause certainty.

## 6. Robotic tool task rehearsal plan

**Task:** Plan simulation and hardware-in-the-loop rehearsals for a robotic servicing task

```text
Act as a space robotics test lead. We will perform [TASK, e.g. installing a mission extension pod / cutting a lockwire / mating a refuelling tool to an RRM-style valve] with [ARM AND END-EFFECTOR]. Constraints: [COMM LATENCY, LIGHTING/ECLIPSE TIMING, FORCE-TORQUE LIMITS, CAMERA VIEWS]. Design a rehearsal campaign: software simulation runs, hardware-in-the-loop or air-bearing/flat-floor tests, and operator training scenarios including off-nominal cases (stuck tool, lost camera, unexpected client tumble). Output a phased table with objective, test setup, pass criteria, and the off-nominal scenarios each phase covers. Note which fidelity gaps between test and orbit remain.
```

## 7. Stakeholder explainer on servicing

**Task:** Explain a servicing mission to non-specialists and address debris concerns

```text
You are a communications specialist for a satellite servicing company. Write [FORMAT: a 400-word press Q&A / a one-page briefing for a regulator or investor] explaining our upcoming mission: [MISSION SUMMARY]. Cover what will happen, why life extension or debris removal matters, how we keep the operation safe for other operators, and how the client consented. Answer likely concerns directly: risk of creating debris, dual-use and counterspace worries about RPO-capable vehicles, and transparency (e.g. sharing ephemerides). Keep it accurate and non-hype; mark any claim I should verify with [VERIFY].
```

> **Caution:** Don't release operational details (timing, vulnerabilities) beyond what the mission has approved for public disclosure.

## 8. Upskilling study plan

**Task:** Build a learning plan for the orbital mechanics and robotics a servicing tech needs

```text
Act as a mentor for someone moving into satellite servicing operations from [BACKGROUND, e.g. satellite bus operations / industrial robotics / aircraft maintenance]. Build a [12]-week study plan covering relative motion (Clohessy-Wiltshire/Hill equations), RPO trajectory safety, GNC sensors (lidar, visual navigation), space robotics and teleoperation under latency, propellant transfer basics, and relevant standards (CONFERS practices, ISO 24330). For each week give objectives, one or two well-known resources (textbooks, NASA reports such as the OSAM state-of-play report, open courses), a hands-on exercise (e.g. simulate a V-bar approach in Python or GMAT), and a self-check question. Flag resources whose titles or availability I should verify.
```
