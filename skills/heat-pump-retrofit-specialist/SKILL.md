---
name: heat-pump-retrofit-specialist
description: "Prompt playbook for a heat pump retrofit specialist. Use when a heat pump retrofit specialist wants help with work tasks such as: sanity-check a heat loss calculation; select equipment for cold-climate performance; troubleshoot a poor-performing install; explain the retrofit to a homeowner; map incentives and paperwork; plan the electrical side; commissioning and handover report; get current on A2L refrigerants and codes."
---

# Heat pump retrofit specialist prompts

Assesses existing homes and small buildings, designs and commissions heat pump systems that replace gas, oil or propane heating, and guides owners through rebates, electrical upgrades and the refrigerant transition. AI helps most with load-calculation sanity checks, troubleshooting, homeowner explanations, incentive paperwork and keeping up with changing codes and refrigerants.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Sanity-check a heat loss calculation

**Task:** Review a Manual J / EN 12831 heat loss result before sizing equipment

```text
You are a senior HVAC designer reviewing a heat pump retrofit load calculation. Home: [YEAR BUILT, FLOOR AREA, STORIES, FOUNDATION TYPE], climate: [LOCATION, 99% DESIGN TEMP], envelope: [INSULATION LEVELS, WINDOWS, BLOWER DOOR RESULT OR 'UNTESTED']. My calc method: [ACCA MANUAL J / EN 12831 / MCS HEAT LOSS TOOL]. Results: heating [BTU/H OR kW], cooling [BTU/H OR kW]. Also attached: [PAST WINTER FUEL USE, e.g. THERMS PER MONTH]. Cross-check the calc against a fuel-use (degree-day) estimate, flag inputs that look implausible, and list the 5 most likely sources of oversizing or undersizing. Output: a short table of checks (pass/concern/why), then a recommended capacity range at design temperature. Show your arithmetic and state your assumptions.
```

> **Caution:** This is a screening check only; the stamped or certified load calculation required by your code, utility or MCS remains your responsibility.

## 2. Select equipment for cold-climate performance

**Task:** Compare candidate heat pumps against the design load at low temperatures

```text
Act as a cold-climate heat pump application engineer. Design heating load: [LOAD] at [DESIGN TEMP]. Distribution: [DUCTED / DUCTLESS / HYDRONIC RADIATORS AT FLOW TEMP X]. Candidates, with data I copied from manufacturer extended-performance tables or the NEEP Cold Climate ASHP list: [MODEL, CAPACITY AND COP AT 47F/17F/5F OR A7/A2/A-7, MIN TURNDOWN]. For each, estimate capacity and COP at design temperature, the balance point, how much backup heat is needed, and whether minimum output is low enough to avoid short cycling at shoulder-season loads. Output a comparison table and a 3-sentence recommendation. Only use the numbers I supplied; mark anything you extrapolate.
```

> **Caution:** Do not trust remembered spec numbers; confirm with current manufacturer submittals and the NEEP listing.

## 3. Troubleshoot a poor-performing install

**Task:** Diagnose a callback for high bills, cold rooms or frequent defrost

```text
You are a heat pump service lead helping me diagnose a callback. System: [BRAND/MODEL, REFRIGERANT, AGE, DUCTED OR DUCTLESS]. Complaint: [e.g. HIGH BILLS, COLD BEDROOMS, BACKUP STRIP HEAT RUNNING, ICING]. Field readings: [OUTDOOR TEMP, SUPPLY/RETURN TEMPS, STATIC PRESSURE, SUPERHEAT/SUBCOOLING, AMP DRAW, FAULT CODES, THERMOSTAT SETTINGS, AUX HEAT LOCKOUT SETTINGS]. Give a ranked list of likely causes, each with the reading that supports or rules it out and the next measurement to take. Separate controls/setup issues from refrigerant or airflow issues from design (sizing/duct) problems. Finish with what to tell the homeowner today.
```

> **Caution:** Refrigerant work requires EPA Section 608 (US) or F-gas (UK/EU) certification; follow manufacturer service procedures, especially for A2L refrigerants.

## 4. Explain the retrofit to a homeowner

**Task:** Write a plain-language proposal summary for a household switching from gas or oil

```text
You are a trusted home-energy advisor writing to a homeowner. Their situation: [CURRENT SYSTEM AND FUEL, ANNUAL FUEL COST, CONCERNS e.g. 'WILL IT KEEP UP AT -10F?', 'NOISE', 'ELECTRIC PANEL']. My proposal: [EQUIPMENT, SCOPE, BACKUP HEAT PLAN, PANEL/ELECTRICAL WORK, PRICE, ESTIMATED OPERATING COST WITH ASSUMED ELECTRICITY AND FUEL PRICES]. Write a one-page explanation at an 8th-grade reading level: what changes in their home, how it performs on the coldest days, honest operating-cost range with assumptions stated, what maintenance looks like, and 5 FAQ answers addressing their concerns. Don't overpromise savings; say where results depend on rates and weather.
```

> **Caution:** Verify every price, savings figure and incentive amount before sending; savings claims can create consumer-protection liability.

## 5. Map incentives and paperwork

**Task:** Build a checklist of rebates, credits and documentation for a specific job

```text
Act as an incentives coordinator for a heat pump contractor. Job: [LOCATION (STATE/PROVINCE/COUNTRY), UTILITY, HOUSEHOLD INCOME BAND IF KNOWN, EQUIPMENT, INSTALL DATE]. Programs I believe apply: [e.g. STATE HEEHRA/HOMES REBATE, UTILITY REBATE, UK BOILER UPGRADE SCHEME, LOCAL PROGRAM]. For each, list eligibility requirements, required documents (AHRI certificate, load calc, MCS certificate, invoices, photos, income verification), who submits, timing (pre-approval vs post-install), and stacking rules. Output a checklist table. Explicitly flag anything you are unsure is still active or funded as of [TODAY'S DATE], since programs and federal credits such as 25C have changed recently.
```

> **Caution:** Incentive rules change often; confirm on the program administrator's current guidelines before quoting amounts to customers.

## 6. Plan the electrical side

**Task:** Assess panel capacity and avoid an unnecessary service upgrade

```text
You are an electrical-aware retrofit planner. Home: [SERVICE SIZE e.g. 100A, PANEL MAKE, EXISTING LOADS: RANGE, DRYER, WATER HEATER, EV CHARGER, ETC.], 12 months of peak demand data if available: [DATA]. Proposed heat pump: [MCA/MOCP FROM NAMEPLATE], backup heat: [STRIP kW OR NONE], heat pump water heater: [YES/NO]. Walk through an NEC 220.83 (or local equivalent) existing-dwelling load calculation, then outline alternatives to a service upgrade: smaller backup strips, load management/circuit sharing devices, 120V heat pump water heaters, staging. Output: the calc in a table, then options ranked by cost and disruption, with questions I need the electrician to answer.
```

> **Caution:** Final load calculation and panel work belong to a licensed electrician and the local AHJ; code editions vary by jurisdiction.

## 7. Commissioning and handover report

**Task:** Turn field notes into a commissioning record and owner handover document

```text
You are a quality manager for a heat pump installer. From my commissioning notes below, produce two documents. (1) A commissioning record: system details, refrigerant type and charge (factory plus added), pressure/vacuum test results, airflow or water flow, measured temperatures, static pressure, controls settings (aux heat lockout temp, defrost, setpoints), photos taken, and any deviations from design. Mark missing items as GAP. (2) A one-page homeowner guide: thermostat do's and don'ts for heat pumps, filter and outdoor-unit care, what normal defrost looks like, and when to call. Notes: [PASTE FIELD NOTES]. Requirements to align with: [e.g. MCS MIS 3005-D, UTILITY QA CHECKLIST, MANUFACTURER STARTUP SHEET].
```

> **Caution:** Never fill gaps with assumed values; a commissioning record must reflect actual measurements.

## 8. Get current on A2L refrigerants and codes

**Task:** Build a study plan for the refrigerant transition and new safety rules

```text
You are a technical trainer for HVAC technicians moving into heat pump retrofits. My background: [YEARS EXPERIENCE, CERTIFICATIONS, REGION]. Create a 4-week study plan covering: the AIM Act / EPA Technology Transitions rules phasing down R-410A (or EU F-gas Regulation 2024/573 / UK F-gas if I'm in Europe), A2L refrigerants like R-454B and R-32, UL 60335-2-40 and ASHRAE 15/34 requirements (charge limits, leak detection, mitigation), tool and recovery-equipment changes, and propane (R-290) monoblocks. For each week: key concepts, 5 self-test questions, and which official sources or manufacturer trainings to read. Flag rules that are still being phased in or adopted locally.
```

> **Caution:** Hands-on A2L and R-290 handling must be learned through accredited or manufacturer training, not from AI summaries.
