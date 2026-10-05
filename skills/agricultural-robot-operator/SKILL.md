---
name: agricultural-robot-operator
description: "Prompt playbook for an agricultural robot operator. Use when an agricultural robot operator wants help with work tasks such as: daily fleet mission plan; fault log triage; perception miss review; pre-season safety risk assessment; spray drone mission compliance check; incident and near-miss report; explaining autonomy to workers and neighbors; upskilling plan for operators."
---

# Agricultural robot operator prompts

Runs and supervises fleets of autonomous tractors, laser/mechanical weeders, harvest-assist carts and spray drones (today's analogues: John Deere autonomous 8R, Carbon Robotics LaserWeeder, Monarch, Burro, Naio, ag drones under FAA Part 137), handling mission planning, remote monitoring, field interventions and safety compliance. AI helps most with log and fault triage, mission and season planning, safety documentation against ISO 18497 / ISO 25119, crew training and clear communication with growers, workers and neighbors.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily fleet mission plan

**Task:** Plan the day's autonomous field operations across machines and blocks

```text
You are an experienced autonomous farm-fleet operations planner. Build today's mission plan for my fleet. Machines: [LIST: model, task capability, battery/fuel state, implement]. Fields/blocks: [BLOCK NAMES, acreage, crop, growth stage, row spacing]. Constraints: [WEATHER FORECAST, soil moisture/trafficability, spray re-entry intervals, hand-crew locations and hours, charging/refuel points, RTK base coverage gaps]. Priorities from the grower: [PRIORITIES]. Output: (1) a time-blocked table per machine with block, task, estimated hours and handoff points; (2) exclusion zones and times where people will be present; (3) the top 3 things that could break the plan and a fallback for each. State any assumptions about work rates explicitly so I can correct them.
```

> **Caution:** Verify work rates and exclusion zones on site; the operator remains responsible for keeping people out of active autonomous zones.

## 2. Fault log triage

**Task:** Diagnose a robot stoppage or recurring fault from logs and symptoms

```text
Act as a field-robotics troubleshooting engineer. My [MACHINE MAKE/MODEL, software version] stopped or behaved abnormally during [TASK] in [FIELD CONDITIONS: dust, slope, canopy, time of day]. Here are the fault codes, log excerpt and what I observed: [PASTE LOGS/CODES/OBSERVATIONS]. Recent changes: [FIRMWARE UPDATE, IMPLEMENT SWAP, CALIBRATION, NEW FIELD BOUNDARY]. Give me: a ranked list of likely causes (perception, GNSS/RTK, connectivity, hydraulics/drive, implement, map/boundary error) with the evidence for each; a safe step-by-step check sequence starting with lockout/power-down where needed; what data to capture before resetting; and when this should be escalated to the OEM instead of fixed in the field. Say plainly where the logs are ambiguous.
```

> **Caution:** Follow the OEM service manual and lockout/tagout procedures; never bypass safety-rated stops or obstacle detection to clear a fault.

## 3. Perception miss review

**Task:** Analyze weeding or harvest-assist errors such as crop strikes or missed weeds

```text
You are a precision-ag data analyst reviewing autonomous weeder/harvest-assist performance. Block [BLOCK ID], crop [CROP, stage], machine [MODEL/MODE]. Data: [PASTE SUMMARY: crop-damage counts, weed-kill rate by pass, scouting sample results, speed, lighting/time, soil and residue conditions, any per-row stats]. Grower tolerance: [ACCEPTABLE CROP LOSS %]. Analyze where and why performance degraded, separating likely causes (lighting, dust, weed size vs. crop size, speed, bed shape, model version). Output a short findings table, 3-5 concrete operating adjustments to try next pass, a ground-truth sampling plan to confirm the fix, and what feedback/images I should send the vendor for retraining.
```

> **Caution:** Ground-truth with manual scouting before changing settings fleet-wide; small samples can mislead.

## 4. Pre-season safety risk assessment

**Task:** Draft a site risk assessment and operating procedure for autonomous machines

```text
Act as an agricultural machinery safety specialist familiar with ISO 18497 (safety of highly automated agricultural machines), ISO 25119 (functional safety of ag control systems), ISO 12100 risk assessment, and [OSHA / Cal-OSHA / EU Machinery Regulation 2023/1230 / OTHER JURISDICTION] requirements. Draft a site-specific risk assessment and standard operating procedure for deploying [MACHINES] on [FARM: layout, public roads, neighbors, worker crews, livestock, water features]. Include hazard list with severity/likelihood, controls (geofences, signage, exclusion zones, e-stops, supervision ratio, communications), a pre-operation checklist, and an incident/near-miss reporting step. Mark every point where local rules on supervision of driverless machines are unsettled or need confirmation with a regulator or insurer.
```

> **Caution:** This is a draft; rules on unattended tractors vary by state and country and are changing, so have it reviewed by a qualified safety professional and your insurer.

## 5. Spray drone mission compliance check

**Task:** Prepare and check an aerial application job with an ag drone

```text
You are a compliance-minded ag drone operations lead in [COUNTRY/STATE]. I plan an aerial application with [DRONE MODEL, tank size] on [FIELD, acreage, crop] using [PRODUCT NAME, EPA reg. no. or local equivalent]. Nearby: [HOUSES, SCHOOLS, WATER, SENSITIVE CROPS, BEEHIVES]. My certifications/waivers: [e.g., FAA Part 107, Part 137 operator certificate, exemptions, state applicator license]. Produce a pre-job checklist covering airspace, certificates, label requirements (droplet size, buffer zones, wind limits, REI), drift management, notifications, and records to keep. Flag anything I appear to be missing and anything where the label is silent on drone application and I should ask the registrant or state lead agency.
```

> **Caution:** The pesticide label is the law; confirm drone-specific application rights and certificates with the FAA and state agency before flying.

## 6. Incident and near-miss report

**Task:** Write a clear, factual report after a robot incident or near miss

```text
You are helping me write a factual incident report for [AUDIENCE: farm owner, insurer, OEM, safety committee]. Event: [WHAT HAPPENED, date/time, location, machine and mode, people/animals/property involved, injuries/damage]. Evidence: [LOG EXCERPTS, CAMERA NOTES, WITNESS STATEMENTS]. Write a report with: timeline, immediate actions taken, contributing factors (technical, procedural, human, environmental), what is still unknown, corrective actions with owner and due date, and whether this should be reported to the OEM or a regulator in [JURISDICTION]. Keep fact separate from interpretation and do not assign blame beyond what the evidence supports.
```

> **Caution:** Check legal reporting duties (e.g., OSHA serious-injury reporting) and preserve logs before any software update or reset.

## 7. Explaining autonomy to workers and neighbors

**Task:** Communicate safely and clearly about robots operating on the farm

```text
Act as a farm communications coordinator. We are deploying [MACHINES] on [FARM] starting [DATE]. Audiences: [FARMWORKERS (languages: e.g., Spanish, Mixtec), NEIGHBORS, LOCAL ROAD USERS]. Concerns we have heard: [CONCERNS: safety, jobs, noise, night work, drift, cameras/privacy]. Draft: (1) a one-page plain-language safety briefing for workers with what the machines do, how to recognize an active zone, what to do if one approaches, and who to call; (2) a short neighbor letter; (3) 5 honest FAQ answers, including what cameras record and how long data is kept. Keep reading level around grade 6 and avoid overpromising.
```

> **Caution:** Have translations checked by native speakers and confirm data-retention facts with the vendor before stating them.

## 8. Upskilling plan for operators

**Task:** Build a learning plan to move from tractor operator to autonomous fleet operator

```text
You are a training designer for precision agriculture. I am [BACKGROUND: e.g., 10 years running conventional equipment, basic computer skills] and will supervise [MACHINES/PLATFORM] at [FARM TYPE]. Build a 12-week learning plan covering: GNSS/RTK and field boundaries, ISOBUS (ISO 11783) and implement setup, basics of perception and why it fails, remote monitoring and connectivity, battery/charging management, fault triage, safety standards (ISO 18497, ISO 25119 basics) and data handling. For each week give goals, a hands-on exercise I can do on the farm, free or low-cost resources (extension services, OEM training, certifications such as state applicator or FAA Part 107 if relevant), and a self-check question. Flag areas where vendor-specific training is essential.
```
