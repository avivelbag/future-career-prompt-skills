---
name: warehouse-automation-integrator
description: "Prompt playbook for a warehouse automation integrator. Use when a warehouse automation integrator wants help with work tasks such as: throughput and sizing sanity check; fault log triage; mobile robot risk assessment draft; wMS/WES-to-fleet interface spec; site acceptance test plan; explaining the change to floor staff; brownfield retrofit plan; upskilling on safety and controls standards."
---

# Warehouse automation integrator prompts

Warehouse automation integrators design, install and commission mixed systems of AMRs, AS/RS, conveyors, sorters and robotic picking for distribution centers, tying them together through WMS/WES software and safety standards such as ANSI/A3 R15.08, ISO 3691-4 and ISO 10218. AI helps most with throughput analysis, fault triage from logs, interface specs, risk assessment drafts, commissioning documentation and explaining changes to operations staff.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Throughput and sizing sanity check

**Task:** Check whether a proposed automation design meets peak order volume before quoting

```text
You are a senior warehouse automation integrator reviewing a concept design. Site profile: [ORDER LINES PER HOUR AT PEAK], [SKU COUNT AND VELOCITY SPLIT], [ORDER PROFILE: e-com eaches / store replenishment / cases], [BUILDING FOOTPRINT AND CLEAR HEIGHT]. Proposed system: [E.G. 40 GOODS-TO-PERSON AMRs, 8 PICK STATIONS, CUBE STORAGE GRID, SORTER RATE]. Do a back-of-envelope capacity check: estimate cycle times, robot and station utilization, and the likely bottleneck at peak. Show your arithmetic in a table, list every assumption I must verify with the vendor, and flag where a discrete-event simulation (e.g. FlexSim, AnyLogic, Emulate3D) is needed before committing. End with three design changes that would add the most headroom.
```

> **Caution:** Rough estimates only; vendor-validated rates and simulation must back any committed throughput guarantee.

## 2. Fault log triage

**Task:** Find root-cause candidates in robot fleet or conveyor fault logs after a downtime event

```text
Act as a controls and fleet-management troubleshooting lead. Below are fault/alarm logs from [SYSTEM: E.G. AMR FLEET MANAGER, PLC ALARM HISTORY, WES EVENT LOG] covering [TIME WINDOW] around a stoppage that cost [DOWNTIME MINUTES]. Context: [LAYOUT NOTES, RECENT CHANGES, FIRMWARE/SOFTWARE VERSIONS]. [PASTE LOGS]. Group the events into a timeline, separate initiating faults from cascade symptoms, and rank the 3-5 most likely root causes (e.g. Wi-Fi roaming dropouts, localization loss, traffic deadlock, photo-eye misalignment, WMS message timeout) with the evidence for each. For each, give the next diagnostic check and what data would confirm or rule it out. Mark anything you are inferring rather than reading directly from the logs.
```

> **Caution:** Never bypass safety devices or interlocks to test a hypothesis; follow lockout/tagout (OSHA 1910.147) for any physical inspection.

## 3. Mobile robot risk assessment draft

**Task:** Draft a hazard list and risk assessment structure for an AMR deployment in a mixed human-robot area

```text
You are helping a safety-trained integrator prepare a risk assessment for industrial mobile robots in [AREA DESCRIPTION: aisles, pick zones, dock, pedestrian crossings]. Robots: [MAKE/MODEL, PAYLOAD, MAX SPEED, SAFETY SCANNER CONFIG]. Work alongside: [NUMBER OF STAFF, FORKLIFTS, VISITORS]. Using the structure of ANSI/A3 R15.08-1/-2 and ISO 3691-4 (and ISO 12100 for method), draft a hazard identification table: hazard, scenario, affected persons, initial severity/likelihood, proposed risk reduction (design, safeguarding, information), and residual risk. Note which clauses I should check in the actual standard text, and list questions for the robot manufacturer about stopping distances and field-set switching.
```

> **Caution:** A draft only; the final assessment must be done and signed by qualified people against the purchased standard texts and the manufacturer's data.

## 4. WMS/WES-to-fleet interface spec

**Task:** Write an integration interface specification between warehouse software and a robot fleet

```text
Act as an integration architect. I need an interface specification between [WMS/WES PRODUCT] and [ROBOT FLEET MANAGER OR VENDOR], connected via [REST / MQTT / VDA 5050 / VENDOR API]. Business flows: [E.G. TASK CREATION, PICK CONFIRMATION, EXCEPTION HANDLING, REPLENISHMENT]. Produce: (1) a message catalog table (message, direction, trigger, key fields, acknowledgment, timeout), (2) sequence diagrams in Mermaid for the happy path and two failure cases, (3) idempotency and retry rules, (4) a list of open questions for each vendor. Where I name a standard like VDA 5050, use only its real concepts and tell me which version details I must confirm against the published spec.
```

> **Caution:** Verify field names and versions against the vendors' actual API documentation; do not assume fields exist.

## 5. Site acceptance test plan

**Task:** Build a commissioning and SAT test plan with pass/fail criteria

```text
You are a commissioning manager preparing the Site Acceptance Test for [SYSTEM SCOPE] at [CUSTOMER SITE]. Contracted performance: [THROUGHPUT, ACCURACY, AVAILABILITY TARGETS AND MEASUREMENT RULES]. Write an SAT plan with sections for: prerequisites (FAT closed, safety validation done, network survey), functional tests per subsystem, integration tests with [WMS], degraded-mode and recovery tests (power loss, network outage, e-stop and restart), a timed rate test with sampling method, and a punch-list process. Format as a table with test ID, procedure, expected result, pass/fail criterion and sign-off role. Flag any target in the contract that is ambiguous to measure.
```

> **Caution:** Acceptance criteria must match the contract; have the project manager and customer agree the measurement method before testing.

## 6. Explaining the change to floor staff

**Task:** Write a plain-language briefing for warehouse associates and supervisors before go-live

```text
Act as a change-management communicator for a distribution center introducing [AUTOMATION: E.G. AMRs IN PICK AISLES, A NEW SORTER]. Audience: [SHIFTS, LANGUAGES, UNION OR NOT]. Write (1) a one-page briefing in plain language covering what changes, how robots behave around people, right-of-way rules, how to stop a robot and who to call, and how jobs and training are affected per [WHAT MANAGEMENT HAS CONFIRMED], and (2) a 10-question FAQ answering likely worries honestly. Don't promise anything not in my notes; insert [CONFIRM WITH HR] where job or pay questions arise. Keep reading level around grade 6.
```

> **Caution:** Job-impact statements must come from management/HR, not the integrator; translate with a qualified translator for safety content.

## 7. Brownfield retrofit plan

**Task:** Plan a phased automation retrofit in a live, operating warehouse

```text
You are an integration project planner. The customer's DC at [LOCATION] must stay open while we install [SCOPE] over [TIMELINE]. Constraints: [PEAK SEASON DATES, FLOOR FLATNESS/SLAB DATA, POWER AND NETWORK CAPACITY, FIRE SPRINKLER LAYOUT, RACKING CONDITION]. Produce a phased plan: phases with scope, temporary operations workarounds, cutover approach (parallel run vs. big bang), rollback criteria, and dependencies such as permits, fire marshal review, Wi-Fi survey and racking inspection (ANSI MH16.1). Present it as a phase table plus a top-10 risk register with owner and mitigation. Note where local code or AHJ approval could change the schedule.
```

> **Caution:** Local codes and the authority having jurisdiction govern permits, fire protection and electrical work; confirm with licensed engineers.

## 8. Upskilling on safety and controls standards

**Task:** Build a study plan to learn the standards and skills that govern robot integration

```text
Act as a mentor for someone moving into warehouse automation integration from [BACKGROUND: e.g. software, mechanical, operations]. Build a 12-week study plan covering: machine safety basics (ISO 12100 risk assessment, ISO 13849-1 performance levels), mobile robot standards (ANSI/A3 R15.08, ISO 3691-4), collaborative and industrial arms (ISO 10218:2025), electrical (NFPA 79), industrial network security (IEC 62443), the EU Machinery Regulation 2023/1230 if I work in Europe, and PLC/fleet-manager fundamentals. For each week give goals, specific resources to find, a hands-on exercise, and a self-test question. Flag areas where standards are being revised or where practice is still unsettled, such as humanoid robots in warehouses.
```

> **Caution:** Confirm current editions and dates of each standard; formal safety certification courses are needed before signing off safety work.
