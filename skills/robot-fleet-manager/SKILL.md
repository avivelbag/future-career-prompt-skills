---
name: robot-fleet-manager
description: "Prompt playbook for a robot fleet manager. Use when a robot fleet manager wants help with work tasks such as: shift fault-log triage; throughput drop root cause; safety incident report draft; floor staff change announcement; fleet expansion capacity plan; mixed-fleet vendor evaluation; change and risk assessment; upskilling plan for fleet ops."
---

# Robot fleet manager prompts

Robot fleet managers run mixed fleets of AMRs, AGVs, cleaning, delivery or humanoid robots for warehouses, hospitals, factories and campuses, owning uptime, safety, interoperability (VDA 5050, Open-RMF, MassRobotics) and the people who work alongside the robots. AI helps most with triaging fault and telemetry logs, writing incident and KPI reports, drafting safety and change documentation against ISO 3691-4 / ANSI R15.08, and planning fleet expansions and vendor evaluations.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Shift fault-log triage

**Task:** Turn a shift's raw fleet alerts into a prioritized action list

```text
You are an experienced robot fleet operations lead. Below is an export of alerts and error codes from our [FLEET MANAGER / PLATFORM, e.g. Formant, InOrbit, vendor console] for a [SHIFT LENGTH] shift covering [NUMBER] [ROBOT TYPES] at [SITE TYPE]. Group the alerts by likely root cause (localization, navigation/blocking, battery/charging, network, payload/hardware, software), not by error code. For each group give: count, robots affected, probable cause, whether it is safety-relevant, and a recommended next action with owner (ops, maintenance, IT, vendor). Output a table, then a 5-line summary for the shift handover. Flag any pattern you are unsure about rather than guessing.

Alerts:
[PASTE LOG EXPORT]
```

> **Caution:** Treat cause guesses as hypotheses; any alert touching safety fields, e-stops or collisions goes to a qualified person before the robot returns to service.

## 2. Throughput drop root cause

**Task:** Analyze why fleet KPIs fell and test candidate explanations

```text
Act as a data-minded fleet performance analyst. Our fleet of [NUMBER] [ROBOT MODEL] at [SITE] dropped from [BASELINE KPI, e.g. 420 picks/hr or 92% mission success] to [CURRENT KPI] over [TIME PERIOD]. Changes in that window: [LIST: software updates, layout changes, new SKUs, staffing, Wi-Fi work, seasonal volume]. Data attached: [PASTE CSV OR SUMMARY: missions, durations, wait times, charge time, interventions per robot-hour]. Rank the candidate explanations by how well the data supports each, say what extra data would confirm or rule each out, and propose one controlled test (e.g. A/B zones, rollback on a subset). Output: ranked hypotheses table, data gaps, test plan.
```

## 3. Safety incident report draft

**Task:** Draft a factual near-miss or collision report for internal and regulator use

```text
You are helping a fleet manager write an internal incident report. Incident facts: [DATE/TIME, LOCATION, ROBOT ID AND MODEL, SPEED/MODE, PEOPLE OR ASSETS INVOLVED, INJURIES IF ANY, WHAT WAS OBSERVED, VIDEO/LOG EVIDENCE AVAILABLE]. Write a report with sections: summary, timeline, immediate actions taken, contributing factors (robot, environment, human, procedure, software), relevant requirements to check (e.g. ISO 3691-4 or ANSI/A3 R15.08 provisions, site risk assessment, OSHA recordkeeping in [JURISDICTION]), corrective and preventive actions with owners and dates, and open questions. Use neutral, non-blaming language and mark anything not supported by the facts as [UNVERIFIED].
```

> **Caution:** Do not let the draft assign fault or determine reportability; the EHS lead and legal decide what is recordable or reportable.

## 4. Floor staff change announcement

**Task:** Explain a new robot rollout or route change to frontline workers

```text
You are a communications partner for an operations team. We are [CHANGE: adding 12 AMRs to aisles 4-9 / changing robot speed zones / introducing a humanoid pilot] at [SITE] starting [DATE]. Workers' likely concerns: [e.g. job security, getting hit, slower work, being monitored]. Write (1) a one-page notice in plain language at about an 8th-grade reading level covering what changes, what stays the same, right-of-way and how to stop a robot, and who to ask; (2) 6 FAQ answers that are honest and don't overpromise; (3) a 3-minute toolbox-talk script for supervisors. Output in [LANGUAGES]. Don't claim headcount guarantees we haven't given: [WHAT MANAGEMENT HAS ACTUALLY COMMITTED TO].
```

> **Caution:** Have HR and, where applicable, the union or works council review before release; some jurisdictions require consultation on workplace technology changes.

## 5. Fleet expansion capacity plan

**Task:** Size robots, chargers and network for a volume increase

```text
Act as a fleet capacity planner. Current state: [NUMBER] robots of [MODEL], average mission time [X min], utilization [Y%], charging [CHARGER COUNT, CHARGE/RUN RATIO], peak demand [MISSIONS/HR], Wi-Fi/5G coverage notes [DETAILS]. Target: [NEW PEAK DEMAND] by [DATE], with [CONSTRAINTS: floor space, budget, aisle congestion, union shift rules]. Build a sizing estimate showing your formulas: robots needed with a congestion/blocking allowance, chargers, spare-robot ratio for maintenance, and network load. Give low/expected/high scenarios, the assumptions that most move the answer, and what to simulate (e.g. in the vendor's simulator or Open-RMF) before purchasing. Output as tables plus a short recommendation.
```

> **Caution:** First-order estimates only; validate with vendor simulation and a pilot before committing capital.

## 6. Mixed-fleet vendor evaluation

**Task:** Compare robot vendors and interoperability approaches

```text
You are an independent advisor helping choose robots for a mixed fleet at [SITE TYPE]. Existing systems: [WMS/MES, CURRENT ROBOTS, FLEET SOFTWARE]. Candidates: [VENDOR A, VENDOR B, VENDOR C] with these spec sheets/quotes: [PASTE]. Build a weighted scoring matrix covering safety certification claims (ISO 3691-4, ANSI/A3 R15.08, ISO 10218 where arms are involved), interoperability (VDA 5050, MassRobotics Interoperability Standard, Open-RMF, APIs), total cost of ownership over [N] years, service/SLA, cybersecurity (e.g. IEC 62443 posture), data ownership, and lock-in risk. Then list the 10 questions I must ask each vendor, and mark claims that need documentary proof rather than marketing assurance.
```

> **Caution:** Verify certifications against actual certificates and test reports; standards adoption and versions change, so confirm the current edition.

## 7. Change and risk assessment

**Task:** Prepare a pre-deployment risk assessment for a fleet or layout change

```text
Act as a robotics safety engineer assisting (not replacing) our site's qualified safety professional. Proposed change: [e.g. new route through pedestrian corridor, software update v3.2, raising speed limit to 1.5 m/s, adding a mobile manipulator]. Environment: [LAYOUT, TRAFFIC, PEOPLE PRESENT, FLOOR CONDITIONS]. Draft a hazard analysis table (hazard, cause, who is exposed, severity, likelihood, existing controls, added controls, residual risk) following the structure of ISO 12100 and the operating-zone concepts in ISO 3691-4 / ANSI R15.08. Then list required verification tests, signage/training updates, and a rollback plan. Flag where the EU Machinery Regulation (EU) 2023/1230 or AI Act may apply if we operate in [JURISDICTION], noting what is still unsettled.
```

> **Caution:** A draft for review; sign-off and conformity decisions stay with qualified safety staff and, where required, notified bodies.

## 8. Upskilling plan for fleet ops

**Task:** Build a learning plan for the fleet manager or new team members

```text
You are a mentor for robot fleet operations. My background: [e.g. warehouse supervisor / mechanical tech / software engineer]. My fleet: [ROBOT TYPES, SCALE, SOFTWARE]. In 12 weeks I want to be competent at [GOALS: reading ROS 2 logs, understanding SLAM/localization failures, battery health, safety standards, KPI analytics, vendor contract management]. Make a week-by-week plan with 3-5 hours/week: concepts, free or widely available resources (e.g. ROS 2 docs, Open-RMF tutorials, standards summaries), a hands-on exercise using my own fleet's data each week, and a self-check question. End with the 5 skills you expect to matter most as fleets add humanoids and AI-driven tasking over the next decade, labeled as forecasts.
```

> **Caution:** Check resource links exist and are current; buy official standards texts rather than relying on summaries.
