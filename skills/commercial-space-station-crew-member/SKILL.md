---
name: commercial-space-station-crew-member
description: "Prompt playbook for a commercial space station crew member. Use when a commercial space station crew member wants help with work tasks such as: daily timeline digest; procedure walkthrough rehearsal; payload operations log entry; anomaly note for ground; pre-flight systems study plan; outreach and media prep; informed consent and rules digest; crew health and routine log."
---

# Commercial space station crew member prompts

Professional or private astronauts working aboard commercial LEO stations (today via Axiom Space missions to the ISS; soon Vast Haven-1, Axiom Station, Starlab and Orbital Reef under NASA's Commercial LEO Destinations program) who run payloads for paying customers, maintain station systems and host visitors. AI helps most with pre-flight study, turning procedures and timelines into usable checklists, drafting payload and anomaly reports, and preparing outreach, while ground control and flight rules keep authority over every real operational decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily timeline digest

**Task:** Turn the day's crew timeline into a prioritized personal plan

```text
You are helping a crew member on a commercial space station plan their workday. Here is today's timeline export: [PASTE TIMELINE ROWS: time GMT, activity, crew assigned, constraints]. Here are known carry-overs from yesterday: [LIST]. Produce: (1) a one-page table of my activities in order with prep items, tools/stowage locations to pull ahead, and any hard time constraints (comm passes, vehicle ops, payload windows) marked; (2) conflicts or tight transitions I should raise with ground at the daily planning conference; (3) a short 'if I fall behind' list ranking which tasks are flexible. Do not move or drop anything yourself; flag, don't decide.
```

> **Caution:** The approved timeline and ground controllers are authoritative; use this only as a personal study aid, never to reschedule.

## 2. Procedure walkthrough rehearsal

**Task:** Rehearse an upcoming maintenance or payload procedure before executing it

```text
Act as an experienced station instructor. I will execute this procedure tomorrow: [PASTE PROCEDURE TEXT OR STEPS]. Hardware involved: [ITEMS]. My training on it was [WHEN/HOW]. Walk me through it as a tabletop rehearsal: for each block of steps, ask me one question about what I expect to see, list the likely error traps (wrong connector, valve state, cable routing, cleanliness), and note where the procedure says to stop and call ground. End with a 10-item quiz. Quote the procedure's own wording for cautions and warnings; do not add or reinterpret steps, and tell me where the text is ambiguous so I can ask ground.
```

> **Caution:** Never deviate from the approved procedure; ambiguities go to the flight control team, not the AI.

## 3. Payload operations log entry

**Task:** Draft a clean payload ops report for the customer and payload developer

```text
I ran a commercial research payload aboard [STATION] for [CUSTOMER/INSTITUTION]. Payload: [NAME, PURPOSE]. My raw notes: [PASTE NOTES: times, steps done, readings, photos taken, deviations, anything odd]. Write a structured payload operations report with: summary, activities completed vs planned, timestamps (GMT), observations, deviations and their cause if known, sample/stowage status (location, temperature), data/photo file names downlinked, and open questions for the principal investigator. Keep my observations factual and separate from interpretation. Flag any missing info I should add before sending.
```

> **Caution:** Check customer data-sharing agreements and export-control (ITAR/EAR) markings before sharing payload details outside approved channels.

## 4. Anomaly note for ground

**Task:** Structure an observed system anomaly into a clear report for the flight control team

```text
Something unexpected happened aboard: [DESCRIBE: system/hardware, what I saw/heard/smelled, time GMT, what I was doing, any caution & warning tones, actions I already took per procedure]. Help me write a concise anomaly report for the ground team in this format: observation (facts only), timeline, current configuration and crew status, actions taken and by whose direction, photos/data available, and questions for ground. Then list what additional observations would help troubleshooting that I can safely make without touching hardware. Do not suggest diagnoses as conclusions or any corrective action.
```

> **Caution:** For any emergency (fire, rapid depress, toxic atmosphere) follow onboard emergency procedures and ground direction immediately; this is for after-the-fact documentation only.

## 5. Pre-flight systems study plan

**Task:** Build a study plan to learn the station's systems before launch

```text
I am a [PROFESSIONAL ASTRONAUT / PRIVATE ASTRONAUT / PAYLOAD SPECIALIST] training for a [DURATION] mission to [STATION, e.g. ISS on an Axiom mission, Vast Haven-1]. Launch is in [WEEKS]. My background: [ENGINEERING/SCIENCE/NONE]. Create a week-by-week study plan covering ECLSS (air revitalization, water recovery, CO2 removal), power and thermal, comms, emergency response (fire, depress, toxic atmosphere), vehicle docking/undocking roles, and payload ops. For each topic give the core concepts, public sources to read (NASA technical reports, ISS reference guides), and self-test questions. Mark which content I must learn from my provider's controlled training materials instead.
```

> **Caution:** Public materials are background only; certification comes from the operator's official training program.

## 6. Outreach and media prep

**Task:** Prepare for a live downlink event or social post from orbit

```text
I have a [LIVE SCHOOL DOWNLINK / MEDIA INTERVIEW / SOCIAL POST] from [STATION] on [DATE] for [AUDIENCE, AGE, COUNTRY]. My mission sponsor is [ORGANIZATION] and topics I can talk about: [RESEARCH, DAILY LIFE, VIEWS]. Draft: (1) a 60-second opening in plain language, (2) 12 likely questions with short, accurate answers, (3) three simple on-camera demonstrations of microgravity that are safe and use only approved items, and (4) a list of topics to avoid or route to the press office (anomalies, crew medical info, partner proprietary payload details). Keep facts checkable and flag any I should verify.
```

> **Caution:** Follow your operator's and sponsor's public affairs rules; never disclose crewmates' medical or private information.

## 7. Informed consent and rules digest

**Task:** Understand the regulatory and contractual framework governing my flight

```text
I am flying as a [SPACEFLIGHT PARTICIPANT / CREW] on a [U.S.-LICENSED VEHICLE] to [STATION]. Explain in plain language the frameworks that apply: FAA 14 CFR Part 460 (crew and spaceflight participant requirements, informed consent, the 'learning period' limits on FAA occupant-safety rules), NASA's requirements for private astronaut missions to the ISS where relevant, the ISS Intergovernmental Agreement/crew code of conduct, and the Outer Space Treaty's jurisdiction principles. Output a table: rule, what it means for me, questions to ask my provider or lawyer. Flag where rules for free-flying commercial stations are still unsettled.
```

> **Caution:** Not legal advice; verify current regulations and your contract with qualified counsel, as the FAA learning period and station rules are evolving.

## 8. Crew health and routine log

**Task:** Track sleep, exercise and symptoms to discuss with the flight surgeon

```text
Help me keep a structured daily self-report for my flight surgeon during a [DURATION] mission. Today's inputs: sleep [HOURS, QUALITY], exercise [DEVICE, MINUTES], fluid/food notes, symptoms [e.g. headache, congestion, vision changes, back pain, motion sickness], mood/workload [1-5], medications taken per the onboard kit. Produce a compact entry, a 7-day trend summary from my previous entries [PASTE], and a short list of items worth raising at my next private medical conference, noting known spaceflight issues they may relate to (e.g. SANS, fluid shift, CO2 headaches). Do not diagnose or recommend medication changes.
```

> **Caution:** Private medical data: keep it in approved channels, and all medical decisions belong to the flight surgeon.
