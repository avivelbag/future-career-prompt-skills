---
name: spaceport-operations-manager
description: "Prompt playbook for a spaceport operations manager. Use when a spaceport operations manager wants help with work tasks such as: multi-tenant launch campaign deconfliction; part 420/450 compliance cross-walk; anomaly and mishap initial report; propellant operations hazard review; airspace and maritime coordination brief; community and public launch notice; site master plan and capacity forecast; upskilling plan for the role."
---

# Spaceport operations manager prompts

Runs day-to-day operations at a licensed launch and reentry site (e.g. Spaceport America, Cecil Spaceport, Space Florida, SaxaVord, Andøya): scheduling tenant campaigns, propellant and explosive safety, airspace and maritime coordination, emergency response, and regulatory compliance under FAA 14 CFR Part 420/450 or the UK Space Industry Act 2018. AI helps most with campaign deconfliction, drafting procedures and compliance cross-walks, incident reporting, and turning dense regulatory and safety material into clear briefings for tenants, agencies and the public.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Multi-tenant launch campaign deconfliction

**Task:** Build a conflict-free site schedule across several tenant launch campaigns

```text
You are assisting the operations manager of a licensed spaceport with [NUMBER] tenant operators. Here are the planned campaigns: [LIST: operator, vehicle, pad/hangar, propellant loads, static fires, launch windows, hazard-area radii]. Shared constraints: [FUEL FARM CAPACITY, RANGE/TRACKING ASSETS, CREW SHIFTS, ROAD CLOSURES, AIRSPACE/NOTAM LEAD TIMES]. Build a week-by-week schedule as a table (date, activity, location, resources, hazard area, conflicts). Flag every overlap where hazard areas, explosive-siting quantity-distance limits or shared resources collide, propose two alternative resolutions for each, and list assumptions I must confirm with tenants. Do not treat any hazard radius as verified; mark values I supplied versus ones you inferred.
```

> **Caution:** Hazard areas and explosive siting distances must come from licensed analyses (e.g. Part 420 explosive siting plan), not from the AI's estimates.

## 2. Part 420/450 compliance cross-walk

**Task:** Map site procedures against licence requirements to find gaps

```text
Act as a regulatory compliance analyst for a spaceport operating under [FAA 14 CFR Part 420 launch site operator licence / UK CAA spaceport licence under the Space Industry Act 2018 / OTHER]. Below are excerpts of our current procedures: [PASTE: e.g. access control, explosive siting, lightning protection, accident investigation plan, agreements with local emergency services]. Produce a cross-walk table: requirement (cite the section number only if you are confident), our procedure that addresses it, evidence we hold, and gap/weakness rating. Then list the top five gaps to fix before our [AUDIT/LICENCE RENEWAL DATE]. Clearly flag where you are unsure of the current regulatory text so I can check the eCFR or CAA guidance directly.
```

> **Caution:** Verify every citation against the current eCFR or CAA text; regulations and advisory circulars change, and licence conditions are site-specific.

## 3. Anomaly and mishap initial report

**Task:** Draft the first internal and regulator-facing report after an on-site anomaly

```text
You are helping a spaceport operations manager document an on-site event. Facts so far: [TIMELINE, LOCATION, VEHICLE/GSE INVOLVED, PROPELLANTS, INJURIES, DAMAGE, ACTIONS TAKEN, WEATHER]. Our accident investigation plan requires [NOTIFICATION REQUIREMENTS, e.g. FAA Washington Operations Center, local fire, tenant]. Draft (1) a factual initial report in neutral language separating confirmed facts, unverified reports, and unknowns; (2) a notification checklist with deadlines from our plan; (3) a list of evidence to preserve and data to impound. Do not speculate on root cause, assign blame, or classify the event as a mishap; leave that determination marked for me and our legal/safety team.
```

> **Caution:** Mishap classification and regulator notification are legal obligations; the human manager and safety officer decide and sign.

## 4. Propellant operations hazard review

**Task:** Run a structured hazard review before a new propellant or GSE configuration

```text
Act as a facilitator for a pre-task hazard analysis at a spaceport. The operation: [DESCRIBE: e.g. first LOX/methane loading at Pad B, new cryogenic transfer line, hypergolic servicing]. Equipment and quantities: [DETAILS]. Existing controls: [PROCEDURES, PPE, EXCLUSION ZONES, DETECTION]. Using a HAZOP-style approach with guidewords, produce a table of deviations, causes, consequences, existing safeguards and recommended actions. Note where OSHA Process Safety Management (29 CFR 1910.119), NFPA codes, or our explosive siting plan likely apply and should be checked by a qualified engineer. Finish with questions the review team must answer before approving the operation.
```

> **Caution:** This structures a review; it does not replace a qualified safety engineer, the tenant's own hazard analyses, or required approvals.

## 5. Airspace and maritime coordination brief

**Task:** Prepare the coordination package for a launch window

```text
You are helping prepare airspace and maritime coordination for a launch from [SITE] on [DATE/WINDOW]. Inputs: hazard areas from the operator's flight safety analysis [COORDINATES/DESCRIPTION], affected airspace [SPECIAL USE AIRSPACE, ROUTES], waterways [SHIPPING LANES, PORTS], and our letters of agreement with [FAA ATC FACILITY / NATIONAL ANSP, COAST GUARD/COASTGUARD AGENCY]. Draft: a timeline of required submissions (NOTAM, notice to mariners, LOA notifications) with lead times as stated in our agreements, a one-page brief for ATC/maritime partners, and a scrub/recycle communication plan. Mark any lead time you could not confirm from my inputs.
```

> **Caution:** Hazard areas must come from the operator's approved flight safety analysis; the AI must not generate or alter them.

## 6. Community and public launch notice

**Task:** Write clear public communications about launches, closures and noise

```text
You are the communications aide for [SPACEPORT NAME], near [COMMUNITIES]. Upcoming activity: [LAUNCH/STATIC FIRE/REENTRY, DATE, WINDOW]. Impacts: [ROAD/BEACH/WATER CLOSURES, EXPECTED SONIC BOOMS OR NOISE, VIEWING AREAS, WILDLIFE OR HABITAT RESTRICTIONS]. Write (1) a 150-word plain-language public notice, (2) a 280-character social post, (3) an FAQ of 6 questions residents commonly ask about safety, noise, scrubs and debris, and (4) a short scrub update template. Use only the facts I provided, avoid hype, and don't promise outcomes like zero noise or exact launch times.
```

> **Caution:** Check closures and safety messaging with the operator, local authorities and emergency services before release.

## 7. Site master plan and capacity forecast

**Task:** Assess infrastructure capacity against projected launch cadence

```text
Act as a strategic planning analyst for a spaceport. Current infrastructure: [PADS, HANGARS, PROPELLANT STORAGE, POWER, WATER/DELUGE, ROADS, RANGE ASSETS]. Projected demand: [TENANTS, VEHICLE CLASSES, LAUNCHES PER YEAR FOR NEXT 5-10 YEARS, POINT-TO-POINT OR REENTRY PLANS]. Identify the binding constraints year by year, propose phased investments with rough sequencing, and list regulatory and environmental steps each would likely trigger (e.g. licence modification, NEPA or equivalent environmental review, explosive siting updates). Present as a table plus a one-page summary for our board, and separate solid assumptions from speculative ones such as future reentry or point-to-point demand.
```

> **Caution:** Cost figures and environmental timelines are rough; validate with engineers, regulators and environmental consultants.

## 8. Upskilling plan for the role

**Task:** Build a learning path for a new or aspiring spaceport operations manager

```text
I am [BACKGROUND, e.g. airport operations manager / military range officer / launch engineer] moving into spaceport operations management at a [US FAA-licensed / UK / OTHER] site. Create a 12-week learning plan covering launch site licensing (14 CFR Part 420 and Part 450 basics or local equivalent), explosive and propellant safety, range safety and flight safety analysis concepts, airspace integration, emergency management (incident command), environmental review, and commercial tenant agreements. For each week give objectives, primary sources to read (official regulations, FAA/CAA guidance, agency reports), a practical exercise, and three self-check questions. Flag areas where rules are actively changing so I track updates.
```

> **Caution:** Confirm reading lists against current official sources; some guidance documents are revised or superseded.
