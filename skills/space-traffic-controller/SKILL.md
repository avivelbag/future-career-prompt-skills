---
name: space-traffic-controller
description: "Prompt playbook for a space traffic controller. Use when a space traffic controller wants help with work tasks such as: conjunction alert triage; operator coordination message; post-event conjunction report; launch and reentry deconfliction plan; regulatory landscape briefing; operator fleet risk review; public explainer on a close approach; astrodynamics upskilling plan."
---

# Space traffic controller prompts

Space traffic coordinators screen conjunctions, coordinate collision-avoidance maneuvers between operators, and manage launch, reentry and spectrum deconfliction. Today they work at the US 18th/19th Space Defense Squadrons, the Office of Space Commerce's TraCSS program, ESA, and commercial SSA firms like LeoLabs and Slingshot. Binding international traffic rules don't exist yet. AI helps most with triaging conjunction alerts, drafting operator coordination messages and reports, and keeping up with fast-moving policy.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Conjunction alert triage

**Task:** Rank a shift's batch of conjunction data messages by urgency

```text
You are assisting a space traffic coordinator on shift. Below are [NUMBER] conjunction events summarized from CCSDS Conjunction Data Messages (CDMs): for each, primary/secondary object, TCA, miss distance, radial/in-track/cross-track separation, probability of collision (Pc), covariance age, and whether each object can maneuver. Data: [PASTE TABLE]. Our action thresholds: [e.g., Pc > 1e-4 red, 1e-5 to 1e-4 yellow]. Produce a ranked table with columns: event ID, tier, hours to TCA, key driver of risk, data-quality concerns (e.g., stale or unrealistic covariance, few tracks), and recommended next step (monitor, request tasking, contact operator). Flag any event where Pc is unreliable because of the covariance and explain why. Don't recommend maneuvers; that decision stays with the operator.
```

> **Caution:** Recompute Pc in your validated tools (e.g., CARA software); never act on a Pc the model calculated or restated.

## 2. Operator coordination message

**Task:** Draft a maneuver coordination note to another satellite operator

```text
Act as a space traffic coordinator writing to the operations team of [OTHER OPERATOR] about a predicted close approach between their [SATELLITE/NORAD ID] and our [SATELLITE/NORAD ID] at TCA [UTC TIME]. Current data: miss distance [X m], Pc [VALUE], our maneuver capability [DETAILS], their stated maneuver policy [IF KNOWN]. Draft a short, professional email that: states the event facts in a standard order, proposes which party maneuvers and why, asks them to share ephemeris (with covariance) in [FORMAT, e.g., OEM] by [DEADLINE], gives a 24/7 contact, and confirms neither side maneuvers without telling the other. Then list 3 points to clarify on a follow-up call. Keep it under 250 words and keep the tone neutral.
```

> **Caution:** Check that the IDs, times and contact details are right before sending; maneuver commitments need your operator's authorization.

## 3. Post-event conjunction report

**Task:** Write a close-approach incident or lessons-learned report

```text
You are helping me write a post-event report on a high-risk conjunction. Inputs: timeline of CDM updates and Pc evolution [PASTE], actions taken and by whom [PASTE], whether a maneuver occurred and its delta-v [DETAILS], and post-TCA tracking results [DETAILS]. Write a report with: executive summary (3 sentences), event timeline table, decision points with the information available at each, what went well, gaps (data latency, communication delays, ambiguous responsibilities), and numbered recommendations with owners. Keep facts separate from interpretation, and mark any timeline gap as [UNKNOWN] instead of filling it in.
```

> **Caution:** Before sharing externally, scrub any data restricted under Space-Track user agreements or export controls (ITAR/EAR).

## 4. Launch and reentry deconfliction plan

**Task:** Plan screening for an upcoming launch window or controlled reentry

```text
I coordinate space traffic for [ORGANIZATION]. We have [LAUNCH / CONTROLLED REENTRY] of [VEHICLE] with window [DATES/TIMES UTC], target orbit or reentry corridor [DETAILS], and deployed objects [LIST]. Draft a deconfliction checklist and timeline covering: collision-avoidance (COLA) screening of the launch window against crewed and active objects, screenings to request from 18th SDS/Space-Track or a commercial provider, early-orbit object identification and cataloging, notification to affected operators, NOTAM/NOTMAR coordination with FAA AST and maritime authorities for reentry or debris areas, and any FCC orbital debris or licensing commitments to check. Give it as a T-minus table with owner and deliverable. Flag steps where requirements vary by jurisdiction.
```

> **Caution:** Use this checklist as a planning aid only. Your launch license conditions and the relevant authorities' requirements take precedence.

## 5. Regulatory landscape briefing

**Task:** Get a briefing on current and emerging space traffic rules

```text
Brief me as a space traffic coordinator on the governance that applies to [OPERATOR TYPE, e.g., US-licensed LEO constellation / EU operator]. Cover: Space Policy Directive-3 and the transition of civil SSA to the Office of Space Commerce's TraCSS; the FCC 5-year post-mission disposal rule; UN COPUOS Long-Term Sustainability Guidelines; IADC debris mitigation guidelines and ISO 24113; the proposed EU Space Act; and ESA's Zero Debris approach. For each, state whether it is binding or voluntary, who it applies to, and what it means for daily operations. End with open questions where rules are still forming. Flag anything that may have changed after your training cutoff so I can check it against primary sources.
```

> **Caution:** Rules in this area change often, so check every item against the official text before relying on it.

## 6. Operator fleet risk review

**Task:** Assess a constellation operator's collision-avoidance practices

```text
You are a reviewer helping me assess how well [OPERATOR] manages space traffic for its [NUMBER]-satellite constellation at [ALTITUDE/INCLINATION]. Material: their published practices or responses [PASTE], maneuver statistics [PASTE], and ephemeris-sharing status [DETAILS]. Score each area 1-5 with a justification: ephemeris sharing and covariance quality, maneuver thresholds and response time, autonomous collision avoidance and how transparent it is to other operators, propulsion reliability and failure handling, disposal plan against the FCC 5-year rule, and 24/7 contactability. Use NASA's Spacecraft Conjunction Assessment and Collision Avoidance Best Practices Handbook as the reference. Output a scored table, the top 3 risks, and specific questions to send the operator.
```

> **Caution:** Base the assessment only on evidence the operator supplied. Don't make findings about a named company from unverified information.

## 7. Public explainer on a close approach

**Task:** Explain a newsworthy conjunction or reentry to the public or press

```text
Help me write a public statement about [EVENT, e.g., a close approach between a defunct satellite and a debris fragment / an uncontrolled reentry of OBJECT]. Facts we can release: [PASTE APPROVED FACTS]. Audience: [journalists / general public / local officials]. Write a 200-word statement in plain language that explains what happened, what 'probability of collision' or 'reentry uncertainty window' means without overstating the risk, what was done, and where updates will be posted. Then write 5 likely press questions with short answers that stay within the approved facts. Avoid speculation about cause or blame.
```

> **Caution:** Get public affairs and legal sign-off first. Reentry footprint predictions change quickly, so don't give a precise location before it's confirmed.

## 8. Astrodynamics upskilling plan

**Task:** Build a learning plan for conjunction assessment skills

```text
I'm moving into space traffic coordination from [BACKGROUND, e.g., air traffic control / software engineering / satellite operations]. My current skills: [LIST]. Create a 12-week study plan covering orbital mechanics basics, TLE versus precision ephemeris and SGP4 limitations, covariance and how Pc is computed (Foster/Alfano methods and their assumptions), CCSDS CDM and OEM formats, Space-Track.org and TraCSS workflows, and the policy basics. For each week, give learning goals, free resources (e.g., NASA CARA documentation, Vallado's textbook, the Orekit or Poliastro libraries), and a hands-on exercise. End with 10 self-test questions and answers so I can check my understanding.
```

> **Caution:** Check that recommended resources and links still exist. Practice on public data only.
