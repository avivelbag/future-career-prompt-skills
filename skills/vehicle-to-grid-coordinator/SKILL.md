---
name: vehicle-to-grid-coordinator
description: "Prompt playbook for a vehicle-to-grid coordinator. Use when a vehicle-to-grid coordinator wants help with work tasks such as: day-ahead fleet dispatch plan; failed discharge event triage; interconnection standards explainer; battery degradation and warranty check; monthly program performance report; driver and parent communication; market participation and compliance review; personal upskilling plan."
---

# Vehicle-to-grid coordinator prompts

A V2G coordinator schedules and manages fleets of bidirectional EVs (school buses, delivery vans, utility trucks, residential cars) as a grid resource for a utility, aggregator or fleet owner, balancing driver mobility needs, battery health, interconnection rules and market revenue. AI helps most with dispatch planning, analyzing telemetry and failed events, translating standards like ISO 15118-20, IEEE 1547/UL 1741 SB, IEEE 2030.5, OpenADR and OCPP, and writing market, program and customer documents.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Day-ahead fleet dispatch plan

**Task:** Build tomorrow's charge/discharge schedule that keeps vehicles mission-ready

```text
You are helping a V2G coordinator for [FLEET TYPE, e.g. 40 electric school buses] enrolled in [PROGRAM/MARKET, e.g. a utility demand-response program or CAISO via aggregator]. Inputs: vehicle routes and departure times [PASTE], battery capacities and current SOC [PASTE], bidirectional charger ratings [PASTE], tomorrow's price or event signal [PASTE], minimum departure SOC [X%] and a daily cycling limit [X kWh/vehicle]. Produce an hour-by-hour schedule table per vehicle (charge/discharge kW, expected SOC), total export by hour, expected revenue, and a list of constraint conflicts. Show your assumptions and flag any vehicle at risk of missing its departure SOC.
```

> **Caution:** Mobility comes first; verify the schedule in your actual charge management system before dispatch, as Claude cannot see live telemetry.

## 2. Failed discharge event triage

**Task:** Diagnose why chargers or vehicles didn't respond to a grid event

```text
Act as a troubleshooting partner for a V2G coordinator. During a [EVENT TYPE] event at [TIME], [N] of [M] vehicles failed to export. Here are OCPP 2.0.1 logs / charger status messages [PASTE], ISO 15118-20 session details if available [PASTE], vehicle SOC and plug-in status [PASTE], and the dispatch signal received [PASTE, e.g. OpenADR or IEEE 2030.5]. Group the failures by likely root cause (communication, vehicle not plugged in, SOC floor, inverter trip, firmware, signal timing), cite the evidence from the logs for each, rank by likelihood, and list specific checks to confirm. Say clearly when the logs are insufficient to decide.
```

> **Caution:** Do not have anyone open or service charger power electronics based on this; that needs a qualified electrician or the OEM.

## 3. Interconnection standards explainer

**Task:** Understand which technical standards apply to a new V2G site

```text
I'm a V2G coordinator planning bidirectional charging at [SITE TYPE] in [UTILITY / STATE OR COUNTRY]. Chargers: [MODEL, AC or DC, connector e.g. CCS1/NACS]. Explain which standards and rules likely apply and what each requires of me: IEEE 1547-2018, UL 1741 SB, UL 9741, SAE J3072 (for AC V2G with onboard inverters), ISO 15118-20, IEEE 2030.5/CSIP, and my utility's interconnection tariff (e.g. California Rule 21 if relevant). Output a table: standard, what it governs, who certifies it, what documentation I need. Flag where requirements are still evolving or utility-specific so I verify with the utility.
```

> **Caution:** Standards versions and utility tariffs change; confirm with the utility interconnection team and the current published documents.

## 4. Battery degradation and warranty check

**Task:** Assess whether V2G cycling affects warranties and battery life

```text
You are an analyst supporting a V2G coordinator. Vehicles: [MAKE/MODEL], battery chemistry [NMC/LFP], warranty terms [PASTE relevant clause, especially anything on bidirectional use]. Planned V2G use: [X kWh exported per vehicle per year, typical SOC window, C-rate]. Estimate the added equivalent full cycles per year, summarize what published research suggests about degradation from shallow, moderate-rate V2G cycling (and where findings conflict), and identify any warranty language that could void or limit coverage. Output: short memo with a numbers table, a risk rating, and questions I should put to the OEM in writing.
```

> **Caution:** Degradation estimates are rough; get OEM written approval for bidirectional use before enrolling vehicles.

## 5. Monthly program performance report

**Task:** Write the monthly report for fleet owner and utility

```text
Draft a monthly V2G performance report for [AUDIENCE: fleet owner board / utility program manager]. Data: events called [N], events performed [N], energy exported [kWh], peak export [kW], revenue or incentive earned [$], missed-departure incidents [N], charger uptime [%], notable faults [PASTE]. Structure: one-paragraph executive summary, KPI table versus last month and target, what went wrong and corrective actions, upcoming changes (e.g. new tariff, firmware updates), and open risks. Plain language, no hype, under 600 words. Mark any figure I need to double-check with [VERIFY].
```

## 6. Driver and parent communication

**Task:** Explain V2G to drivers or the public and address concerns

```text
Write communications for a V2G program at [ORGANIZATION, e.g. a school district]. Audience: [bus drivers / parents / residential EV owners]. Main concerns I hear: [e.g. 'will my bus be charged in the morning', 'does it wear out the battery', 'is my data shared']. Produce (1) a one-page FAQ in plain language, (2) a 150-word notice for a newsletter, and (3) a short script for answering questions at a meeting. Be honest about trade-offs and what is still uncertain; include how participants can opt out or override a discharge, and who to contact: [CONTACT].
```

> **Caution:** Ensure privacy statements match your actual data practices and contracts; have legal review public claims about savings.

## 7. Market participation and compliance review

**Task:** Plan aggregation and check regulatory obligations

```text
You are advising a V2G coordinator at [AGGREGATOR/UTILITY] who wants to bid an aggregated EV fleet into [MARKET, e.g. CAISO, PJM, ERCOT, or a non-US market]. Fleet: [N vehicles, total kW, locations]. Explain how FERC Order 2222 (if US) and the market's current DER aggregation rules affect eligibility, minimum size, telemetry, metering and settlement; compare likely participation options (wholesale capacity, frequency regulation, retail demand response, utility program) in a table with requirements, revenue drivers and risks. Clearly flag where implementation timelines or rules are unsettled and list questions for the ISO or utility.
```

> **Caution:** Market rules and Order 2222 implementation differ by region and are still changing; confirm with the market operator and a regulatory specialist.

## 8. Personal upskilling plan

**Task:** Build a learning plan to grow into the V2G role

```text
I'm moving into a vehicle-to-grid coordinator role from [BACKGROUND, e.g. fleet management, utility operations, EV charging installation]. I have [X hours/week] for [N weeks]. Create a week-by-week learning plan covering: power system basics (frequency, voltage, distribution constraints), EV battery fundamentals, bidirectional charging and the ISO 15118-20 / OCPP 2.0.1 / IEEE 2030.5 / OpenADR protocol stack, interconnection (IEEE 1547, UL 1741 SB), electricity markets and DER aggregation, and data analysis of charging telemetry. For each week give goals, specific free or official resources by name (only real ones; say if unsure), a hands-on exercise, and 3 self-check questions.
```

> **Caution:** Double-check resource links; Claude may misremember titles or URLs.
