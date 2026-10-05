---
name: orbital-debris-removal-operator
description: "Prompt playbook for an orbital debris removal operator. Use when an orbital debris removal operator wants help with work tasks such as: conjunction message triage; rPO approach anomaly review; target tumble characterization plan; licensing and consent checklist; controlled reentry risk summary; client mission proposal; public explainer for a capture mission; operator upskilling plan."
---

# Orbital debris removal operator prompts

Plans and flies servicer spacecraft that inspect, rendezvous with, capture and deorbit defunct satellites and rocket bodies, the work pioneered by Astroscale's ELSA-d and ADRAS-J and ESA's ClearSpace-1. AI helps most with conjunction and RPO data triage, anomaly reports, licensing and consent paperwork under the Outer Space Treaty and national regimes, and explaining missions to clients, regulators and the public.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Conjunction message triage

**Task:** Summarize and prioritize incoming CDMs during a debris-removal campaign

```text
You are supporting a flight dynamics operator on an active debris removal (ADR) mission. Below are conjunction data messages (CCSDS CDM format, from Space-Track/18th SDS and [COMMERCIAL SSA PROVIDER]) for our servicer [SERVICER NAME] and client object [TARGET NORAD ID]. Our maneuver threshold is Pc > [THRESHOLD, e.g. 1e-4]. For each event, produce a table: TCA, secondary object, miss distance (radial/in-track/cross-track), Pc, covariance age and quality notes, trend across successive CDMs, and recommended action (monitor / screen maneuver / coordinate with other operator). Flag inconsistent covariances or stale data explicitly. Do not recommend a maneuver yourself; list what the flight dynamics lead must verify. CDMs: [PASTE CDMs]
```

> **Caution:** Pc values depend heavily on covariance realism; all maneuver decisions stay with the certified flight dynamics team.

## 2. RPO approach anomaly review

**Task:** Draft a structured anomaly report after an aborted rendezvous approach

```text
Act as a spacecraft operations engineer writing an anomaly report for an aborted rendezvous and proximity operations (RPO) approach to an uncooperative target [TARGET DESCRIPTION, e.g. tumbling upper stage]. Inputs: timeline of commands and events [PASTE], telemetry excerpts (relative navigation, LIDAR/camera state, thruster firings, GNC mode changes) [PASTE], and the abort trigger [TRIGGER]. Produce: 1) executive summary, 2) chronological timeline, 3) candidate root causes ranked with supporting/contradicting evidence, 4) data gaps needed to close each hypothesis, 5) proposed corrective actions and safe-hold criteria before the next attempt. Clearly label anything that is inference rather than shown in the data.
```

> **Caution:** Treat hypotheses as leads for the engineering review board, not conclusions.

## 3. Target tumble characterization plan

**Task:** Plan an inspection phase to estimate a derelict object's attitude and capture feasibility

```text
I'm planning the inspection phase of an ADR mission, similar in concept to Astroscale's ADRAS-J inspection of an H-IIA upper stage. Target: [OBJECT, mass, dimensions, orbit]. Prior data: [GROUND-BASED LIGHT CURVES / RADAR / NONE]. Servicer sensors: [SENSORS]. Propose an inspection plan: standoff distances and hold points, relative trajectory types (e.g. passive safety ellipse, V-bar/R-bar holds), observations needed to estimate tumble rate and axis, and go/no-go criteria for proceeding to capture. Present as a phased table with rationale and passive-safety considerations for each phase. Note assumptions and where published guidance (e.g. CONFERS RPO practices) applies or is silent.
```

> **Caution:** Trajectory safety must be validated with your own flight dynamics tools and Monte Carlo analysis.

## 4. Licensing and consent checklist

**Task:** Map the regulatory and legal approvals needed before removing a specific object

```text
You are a space regulatory analyst. Our company, licensed in [COUNTRY], plans to inspect and deorbit [OBJECT, NORAD ID], registered by [STATE OF REGISTRY / OWNER]. Build a checklist of approvals and obligations, grouped as: international (Outer Space Treaty Art. VI, VIII and IX, Liability Convention, Registration Convention, UN COPUOS Long-Term Sustainability Guidelines), national licensing (e.g. FCC, FAA, NOAA commercial remote sensing, UK CAA under the Space Industry Act 2018, as relevant), owner consent and data-sharing agreements, export control (ITAR/EAR), and reentry casualty-risk requirements. For each item: who grants it, typical evidence needed, and open questions. Flag where law is unsettled and where I need a qualified space lawyer.
```

> **Caution:** Not legal advice; removing another party's object without its owner's and registry state's consent is not permitted.

## 5. Controlled reentry risk summary

**Task:** Turn reentry analysis outputs into a compliance summary

```text
Act as a mission safety engineer. Below are outputs from our reentry survivability analysis ([TOOL, e.g. ESA DRAMA or NASA DAS]) for the stacked servicer + captured [OBJECT]: surviving fragments, casualty area, casualty risk for controlled and uncontrolled cases, and the planned deorbit burn sequence and target zone [PASTE]. Write a 1-2 page summary comparing results against the applicable thresholds ([e.g. 1:10,000 casualty risk per NASA-STD-8719.14 / ISO 24113 / national licence condition]), the burn-failure contingencies, and notification steps (NOTAM/NAVAREA warnings for the impact zone). End with a list of assumptions and sensitivities a reviewer should challenge.
```

> **Caution:** Numbers must come from your validated analysis; Claude should only summarize, not generate risk figures.

## 6. Client mission proposal

**Task:** Draft a proposal to a satellite operator for end-of-life removal service

```text
Write a proposal from [COMPANY] to [SATELLITE OPERATOR] offering end-of-life removal for [SATELLITE / CONSTELLATION], which [has / lacks] a docking plate or grapple fixture. Audience: their operations director and legal counsel. Include: problem statement (e.g. FCC 5-year post-mission disposal rule, ESA Zero Debris approach, insurer expectations), mission concept and phases, what we need from them (ephemeris, attitude history, design data, passivation status, consent), responsibilities and liability allocation to be negotiated, schedule [DATES], and indicative pricing structure [PRICING]. Keep it under 1,200 words, plain language, with a one-paragraph executive summary. Do not overstate capture success rates; use [OUR FLIGHT HERITAGE] only.
```

> **Caution:** Have legal review any liability or indemnity language before sending.

## 7. Public explainer for a capture mission

**Task:** Explain a debris removal mission to journalists and the public

```text
Write a public-facing explainer and 6-question FAQ for our upcoming mission [MISSION NAME] to capture and deorbit [OBJECT] in [ORBIT]. Audience: general readers and science journalists. Cover: why this object matters (Kessler syndrome context, without hype), how rendezvous with an uncooperative target works, what could go wrong and how we protect other satellites, where and when reentry will happen, and why this isn't a space weapon (address dual-use concerns honestly, referencing transparency measures [OUR MEASURES]). Include a 280-character social post. Use only facts I provide here: [MISSION FACTS]; mark anything you'd need me to confirm.
```

> **Caution:** Coordinate with your comms and export-control teams before releasing imagery or technical detail.

## 8. Operator upskilling plan

**Task:** Build a study plan for a new ADR operator coming from conventional satellite ops

```text
I'm a satellite operator with [BACKGROUND, e.g. 3 years GEO station-keeping] moving to an active debris removal team. Create a 10-week study plan covering: relative motion (Clohessy-Wiltshire/Hill equations), RPO passive safety, conjunction assessment and Pc methods, relative navigation sensors, capture mechanisms (magnetic plates, robotic arms, nets, harpoons) and their failure modes, reentry risk, and the legal/regulatory framework (IADC guidelines, ISO 24113, UN LTS Guidelines). For each week: learning goals, 2-3 recommended sources (textbooks, NASA/ESA/IADC documents; mark any you're unsure exists), a hands-on exercise (e.g. in GMAT, Orekit or Python), and a self-check question.
```

> **Caution:** Verify every cited source exists before buying or relying on it.
