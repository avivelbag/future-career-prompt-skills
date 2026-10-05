---
name: space-tourism-guide
description: "Prompt playbook for a space tourism guide. Use when a space tourism guide wants help with work tasks such as: participant pre-flight briefing pack; informed consent explainer; guest readiness training plan; live window commentary script; contingency and delay playbook; post-flight guest debrief and report; regulatory and industry landscape briefing; accessible and inclusive guest prep."
---

# Space tourism guide prompts

Space tourism guides prepare, escort and debrief private spaceflight participants on suborbital hops (Blue Origin New Shepard, Virgin Galactic), stratospheric balloon flights and orbital or space station missions (SpaceX Crew Dragon, Axiom). They work under FAA 14 CFR Part 460 informed-consent rules, and the occupant-safety regulation moratorium is still in place. AI helps most with briefing materials, training curricula, itinerary and contingency planning, interpreting the views and science in flight, and post-flight reports. Flight-safety decisions stay with certified crew and operators.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Participant pre-flight briefing pack

**Task:** Turn operator procedures into a plain-language briefing for a specific guest group

```text
You are helping a space tourism guide at [OPERATOR] prepare guests for a [SUBORBITAL / ORBITAL / STRATOSPHERIC BALLOON] flight on [VEHICLE]. Using only the operator procedures pasted below, write a briefing pack for [NUMBER] guests with [RELEVANT BACKGROUND, e.g. ages, languages, first-time flyers]. Sections: flight timeline from suit-up to recovery, what they'll feel at each phase (g-loads, weightlessness, noise), their seat and restraint duties, emergency cues and responses, and what is prohibited. Write at an 8th-grade reading level and keep it under 2 pages. Mark anything the procedures leave unclear as [CONFIRM WITH OPS] instead of filling it in.

Procedures: [PASTE OPERATOR PROCEDURES]
```

> **Caution:** The operator's approved procedures are authoritative. Have flight ops check every safety statement before guests see it.

## 2. Informed consent explainer

**Task:** Help guests understand the FAA Part 460 risk disclosure without replacing it

```text
Under 14 CFR 460.45, spaceflight participants must give written informed consent after being told about the risks, including that the U.S. Government has not certified the vehicle as safe. I'm a guide at [OPERATOR], and I want a companion FAQ that helps guests understand our official disclosure, pasted below. Write 10 to 12 questions guests actually ask, such as: What does 'not certified' mean? What is the moratorium on FAA occupant-safety rules? What does my waiver cover? Answer each in 2 to 4 plain sentences, and quote or point to the matching section of the disclosure. Don't downplay risk, don't give legal advice, and list any questions the guest should take to our legal team.

Disclosure: [PASTE DISCLOSURE TEXT]
```

> **Caution:** This FAQ supplements the legal disclosure and must not replace it. Have counsel review it, and check that the moratorium status is current.

## 3. Guest readiness training plan

**Task:** Design a pre-flight training week tailored to a guest cohort

```text
Act as a spaceflight participant training designer. I'm guiding [NUMBER] guests on a [MISSION TYPE, e.g. 10-day private ISS mission / 11-minute suborbital flight] with [OPERATOR]. Training constraints: [AVAILABLE DAYS, FACILITIES such as centrifuge, parabolic flight, simulator, pool]. Guest notes: [FITNESS, MOTION SICKNESS HISTORY, LANGUAGES, ACCESSIBILITY NEEDS]. Build a day-by-day schedule as a table with these columns: session, objective, method, duration, owner (guide, medical, flight crew) and a pass/fail readiness check. Include the procedures guests must perform themselves, practice for living in microgravity, and time to rehearse photography so the window time isn't wasted. Flag every session that needs sign-off from a flight surgeon or certified crew.
```

> **Caution:** Medical clearance and flight readiness are decided by the flight surgeon and operator, not the guide or AI.

## 4. Live window commentary script

**Task:** Prepare accurate narration of what guests will see from altitude or orbit

```text
I'm a space tourism guide writing commentary for a [FLIGHT TYPE] launching from [SITE] on [DATE/TIME UTC], reaching [APOGEE / ORBIT INCLINATION AND ALTITUDE]. Write a timed narration script that covers what guests will likely see: the curve of the horizon, the thin blue line of the atmosphere, terminator, weather systems, cities at night, the ISS or other landmarks if visible, and how far they can see. Give each item 1 to 3 vivid but accurate sentences, plus one 'did you know' fact with its source type (NASA, ESA or a textbook). Note the physical numbers, such as horizon distance from the altitude, and show the calculation. Where visibility depends on the exact trajectory or weather, say so.
```

> **Caution:** Check the trajectory details with flight dynamics. Narration must never cover crew callouts or safety communications.

## 5. Contingency and delay playbook

**Task:** Plan the guest experience around scrubs, weather holds and medical disqualification

```text
You are helping a guide at [OPERATOR] plan for disruptions to a [MISSION] booked for [DATES] at [SPACEPORT, e.g. Spaceport America / Launch Site One, Texas / Kennedy]. Guests: [GROUP PROFILE, VIP NEEDS]. Write a contingency playbook for these scenarios: a 24-hour scrub, a slip of a week or more, a weather hold on launch day, a guest who fails final medical, an off-nominal landing or recovery, and a media leak. For each scenario give the trigger, the guide's actions in the first hour, the communications (who tells whom and what), logistics changes, and when to hand off to the operator's emergency response or legal team. Output a one-page table per scenario.
```

> **Caution:** Align the playbook with the operator's official emergency response plan, which takes precedence over it.

## 6. Post-flight guest debrief and report

**Task:** Turn debrief notes into a structured experience report and improvement items

```text
I'm a space tourism guide. Below are my raw notes from the debrief and survey responses from [NUMBER] guests after [MISSION NAME/DATE]. Write: (1) a 1-page summary report for operator management covering highlights, pain points, any physiological issues guests reported (summarized only, without names), and any procedural deviations guests noticed; (2) a prioritized list of improvement items, each labelled as training, comms, hospitality or safety-relevant; (3) a warm personal thank-you message template. Leave out names and medical details from the management report unless I mark them as approved to share. Send anything safety-relevant to the operator's formal safety reporting channel instead of handling it as hospitality feedback.

Notes: [PASTE NOTES]
```

> **Caution:** Guest health information is sensitive and should only be handled through approved, privacy-compliant systems.

## 7. Regulatory and industry landscape briefing

**Task:** Get up to speed on the rules and players shaping private spaceflight

```text
Teach me, a new space tourism guide, the regulatory and industry landscape in a 2-page briefing. Cover: FAA AST licensing (14 CFR Part 450) and the crew and participant rules (Part 460); the occupant-safety 'learning period' moratorium and its current expiry date; the Outer Space Treaty and the Registration Convention; NASA's rules for private astronaut missions to the ISS; and the main operators and vehicles (suborbital, orbital, balloon) with their status. Finish with 5 open policy questions likely to affect my job in the next 10 years, such as occupant safety standards and medical standards for older guests. Mark anything that may have changed after your knowledge cutoff for me to check against primary sources.
```

> **Caution:** Regulations and operator status change often. Check them against FAA AST and the operators' official sources.

## 8. Accessible and inclusive guest prep

**Task:** Adapt preparation for guests with disabilities, older guests or non-English speakers

```text
Act as an accessibility advisor for a space tourism guide. A guest on our [MISSION TYPE] has [CONDITION / NEED, e.g. limited mobility, hearing impairment, age 80+, speaks only PORTUGUESE]. Using our standard guest prep steps below, suggest specific changes for briefings, training, suit-up, cabin communication, emergency egress drills and the ground experience. Draw on real precedents where you know them, such as AstroAccess parabolic flights and older participants on New Shepard, and say how confident you are in each. Separate the changes I can make as a guide from those that need approval from the operator's engineering or medical team. Output a table of current step, barrier, proposed change, who must approve it, and open questions.

Standard steps: [PASTE]
```

> **Caution:** Whether a guest is eligible to fly and any changes affecting egress are decided by the operator's medical and safety authorities.
