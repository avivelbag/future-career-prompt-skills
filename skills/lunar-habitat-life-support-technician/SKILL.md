---
name: lunar-habitat-life-support-technician
description: "Prompt playbook for a lunar habitat life support technician. Use when a lunar habitat life support technician wants help with work tasks such as: daily ECLSS telemetry trend review; fault tree for a degraded subsystem; anomaly report draft; consumables and redundancy margin plan; crew-facing explanation of a life support change; lunar dust contamination risk review; maintenance procedure rewrite for usability; eCLSS upskilling study plan."
---

# Lunar habitat life support technician prompts

Maintains and troubleshoots the environmental control and life support systems (ECLSS) of future lunar surface habitats and today's analogues: ISS-heritage CO2 removal, oxygen generation, water recovery, thermal and trace-contaminant control, plus lunar-specific threats like regolith dust. Claude helps most with trend analysis of telemetry, fault-tree reasoning, procedure and anomaly-report drafting, consumables planning and fast upskilling, while ground engineering and the flight surgeon keep authority over crew-safety decisions.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily ECLSS telemetry trend review

**Task:** Spot drifting life support parameters before they become alarms

```text
You are assisting a life support technician on a [HABITAT / ANALOGUE NAME] crewed habitat with [CREW SIZE] crew. Below is [TIME WINDOW] of telemetry: cabin ppCO2, ppO2, total pressure, humidity, temperature, trace contaminant readings, and status for [SYSTEMS, e.g. CO2 removal bed, oxygen generator, water processor]. [PASTE DATA OR SUMMARY STATS]. Our limits are [LIMITS, e.g. from NASA-STD-3001 and our flight rules]. Output: (1) a table of each parameter with current value, trend direction, and margin to limit; (2) anomalies or slow drifts worth watching, with likely causes ranked; (3) recommended checks for the next shift. Distinguish sensor drift from real changes and say what extra data would resolve it.
```

> **Caution:** Advisory only; any parameter near a crew-health limit goes to the flight controller and flight surgeon, not to Claude's judgment.

## 2. Fault tree for a degraded subsystem

**Task:** Structure troubleshooting of a failing ECLSS component

```text
Act as an experienced ECLSS systems engineer. Our [SUBSYSTEM, e.g. electrolysis oxygen generator / urine processor / Sabatier reactor] shows [SYMPTOMS AND ERROR CODES] since [TIME]. Recent events: [MAINTENANCE, POWER EVENTS, DUST INCURSION, THERMAL CHANGES]. Known ISS-heritage failure modes may apply. Build a fault tree from the top-level symptom to candidate root causes, then give a troubleshooting sequence ordered by (a) crew safety, (b) consumable cost, (c) diagnostic value, noting which steps need ground approval or EVA/IVA time. Flag any step that risks contaminating water or atmosphere and any assumption you are making about our hardware.
```

> **Caution:** Never execute steps outside the approved procedure set; use this to prepare questions for ground engineering.

## 3. Anomaly report draft

**Task:** Turn shift notes into a structured nonconformance/anomaly report

```text
Draft an anomaly report for [ORGANIZATION]'s problem reporting system from my raw notes: [PASTE NOTES, LOGS, TIMESTAMPS]. Use sections: summary, system and part/serial numbers, timeline (UTC and mission elapsed time), observed behavior vs expected, immediate actions taken, crew impact, consumables impact, suspected cause (clearly labeled as hypothesis), open questions, and recommended disposition. Keep facts and interpretation separate, use neutral language, and list every gap in my notes that an investigator would ask about.
```

> **Caution:** Verify every timestamp and part number against the source logs before submitting.

## 4. Consumables and redundancy margin plan

**Task:** Plan oxygen, water and spares margins for a surface stay

```text
Help me build a consumables plan for a [DURATION]-day lunar surface stay with [CREW SIZE] crew. Inputs: oxygen generation rate [X], CO2 removal capacity [X], water recovery ratio [X%], stored reserves [LIST], spares manifest [LIST], resupply cadence [X], EVA plan [NUMBER/DURATION]. Use NASA-STD-3001 / published crew metabolic assumptions where I have not given values and state them. Output: a daily mass balance table, days of margin under nominal and under [FAILURE CASE, e.g. loss of oxygen generator], the limiting consumable, and spares most worth adding. Flag which numbers are uncertain for lunar conditions (1/6 g, dust, thermal cycling).
```

> **Caution:** Planning aid; official margins must come from the program's validated models.

## 5. Crew-facing explanation of a life support change

**Task:** Explain a system change or restriction to crew calmly and clearly

```text
Write a short crew briefing (under 200 words, plain language) explaining [CHANGE, e.g. reduced water allocation, switching to backup CO2 scrubbing, a new dust-cleaning protocol] because of [REASON]. Include: what is changing, why, how long we expect it to last, what crew need to do differently, what symptoms (e.g. headache from elevated CO2) they should report, and who to contact. Tone: factual, reassuring without minimizing. Then give a one-line version for the daily planning conference.
```

> **Caution:** Health guidance must match what the flight surgeon has approved.

## 6. Lunar dust contamination risk review

**Task:** Assess regolith dust risks to ECLSS hardware and crew air

```text
Act as a reviewer of lunar dust mitigation for a habitat with [AIRLOCK / SUITPORT CONFIGURATION], filters [TYPE/RATING], and EVA cadence [X]. Summarize what Apollo experience and current NASA dust research say about regolith effects on seals, fans, filters, sensors and crew respiratory health. Then produce a risk table for our ECLSS components: hazard, mechanism, likelihood, consequence, existing controls, proposed added controls, and monitoring method. Clearly mark where evidence is thin or still being researched, and list open questions to raise with our program's safety team.
```

> **Caution:** Exposure limits for lunar dust are still being established; cite sources and confirm current values.

## 7. Maintenance procedure rewrite for usability

**Task:** Make a maintenance procedure clearer and safer to execute in suit gloves or under fatigue

```text
Here is a maintenance procedure for [TASK, e.g. CO2 removal bed swap / filter change / water processor R&R]: [PASTE PROCEDURE]. Rewrite it following human factors practice used in spaceflight procedures: one action per step, warnings and cautions placed before the step they apply to, explicit verification steps, tools and parts list up front, and stopping points where the crew should call ground. Do not change technical content; instead list separately anything ambiguous, missing, or possibly incorrect for me to take to the procedure owner.
```

> **Caution:** Rewritten procedures must go through the program's formal review and verification before use.

## 8. ECLSS upskilling study plan

**Task:** Learn regenerative life support from a terrestrial background

```text
I am a [CURRENT BACKGROUND, e.g. HVAC technician / submarine atmosphere tech / chemical process operator] preparing for a lunar habitat life support role in [TIMEFRAME]. Build a [WEEKS]-week study plan covering: ISS ECLSS architecture (CDRA, OGA, WPA, UPA, Sabatier, TCCS), spacecraft atmosphere standards (NASA-STD-3001, SMACs), water quality monitoring, closed-loop and bioregenerative concepts (e.g. ESA MELiSSA), lunar-specific challenges, and fault diagnosis. For each week give learning goals, real public sources (NASA technical reports, conference papers like ICES), a hands-on exercise, and 5 self-test questions. Note which of my existing skills transfer directly.
```

> **Caution:** Verify that cited documents exist and are current versions.
