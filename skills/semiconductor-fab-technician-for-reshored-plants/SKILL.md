---
name: semiconductor-fab-technician-for-reshored-plants
description: "Prompt playbook for a semiconductor fab technician for reshored plants. Use when a semiconductor fab technician for reshored plants wants help with work tasks such as: tool alarm troubleshooting tree; sPC chart out-of-control review; shift passdown report; 8D / root cause write-up; chemical and gas safety briefing; equipment metrics for management; cross-cultural tech transfer questions; 90-day upskilling plan."
---

# Semiconductor fab technician for reshored plants prompts

Equipment and process technicians who keep etch, deposition, lithography and metrology tools running in the new CHIPS Act-funded fabs (TSMC Arizona, Intel Ohio, Samsung Taylor, Micron Idaho/New York), often trained fast through community-college and apprenticeship pipelines. AI helps most with troubleshooting from alarm logs and SPC data, writing clean shift handoffs and 8D reports, decoding SEMI/OSHA safety requirements, and closing the experience gap for new hires working alongside veteran overseas engineers.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Tool alarm troubleshooting tree

**Task:** Work through a recurring equipment alarm methodically before escalating

```text
You are a senior equipment engineer mentoring a fab technician. Tool: [TOOL TYPE AND MODEL, e.g. PECVD chamber]. Alarm/symptom: [ALARM CODE AND TEXT]. Recent history: [PM DATE, PARTS REPLACED, RECIPE, FREQUENCY OF ALARM]. Sensor/trace data I can see: [VALUES OR PASTED LOG EXCERPT]. Build a troubleshooting tree ordered from most likely and least invasive to least likely and most invasive. For each branch give: what to check, expected normal reading, what result points where, and whether it requires LOTO, chamber vent, or vendor (FSE) support. End with the data I should collect before escalating. Flag where you are guessing because OEM-specific details are not public.
```

> **Caution:** Follow the OEM manual, site LOTO (OSHA 1910.147) and hazardous-energy procedures; never open chambers or gas lines without authorization.

## 2. SPC chart out-of-control review

**Task:** Interpret an SPC excursion and decide whether to hold lots

```text
Act as a fab process control engineer. Here is SPC data for [PARAMETER, e.g. film thickness / CD / particle adders] on [TOOL/CHAMBER]: [PASTE DATA POINTS WITH TIMESTAMPS], control limits [UCL/LCL], spec limits [USL/LSL]. Identify which Western Electric/Nelson rules are violated, whether this looks like shift, drift, or noise, and plausible physical causes on this tool type. Then draft the OCAP (out-of-control action plan) steps I should follow: inhibit tool or not, which lots to put on hold, what monitor wafers to run. Output as a short table plus a recommended action, clearly marked as a recommendation for the process engineer to approve.
```

> **Caution:** Lot disposition and tool release decisions belong to the responsible engineer per site OCAP; Claude's analysis is advisory.

## 3. Shift passdown report

**Task:** Turn messy shift notes into a clear handoff

```text
You are helping a fab technician write an end-of-shift passdown for [AREA/BAY, e.g. Diffusion Bay 3]. My raw notes: [PASTE NOTES: tools down, PMs done, open work orders, quals pending, alarms, safety items]. Rewrite as a structured passdown with sections: Safety/EHS items first, Tools down (with tool ID, symptom, actions taken, next step, owner, ETA), PMs and quals completed/pending, WIP holds, Parts on order, Notes for engineering. Keep each line terse and specific; flag anything ambiguous in my notes as a question for me rather than inventing details.
```

> **Caution:** Do not paste proprietary recipe parameters or export-controlled data into tools not approved by your employer.

## 4. 8D / root cause write-up

**Task:** Draft an 8D report after a scrap or excursion event

```text
Act as a quality engineer experienced with 8D and 5-Why in semiconductor manufacturing. Event: [WHAT HAPPENED, e.g. 25 wafers scrapped after wrong recipe on implanter]. Timeline: [EVENTS WITH TIMES]. Containment done: [ACTIONS]. Suspected causes: [LIST]. Draft an 8D report (D1 team through D8 recognition) with a 5-Why chain and a fishbone (man, machine, method, material, measurement, environment) as a text list. Distinguish verified facts from hypotheses, propose corrective actions that are systemic (interlocks, MES checks, training) rather than 'retrain operator' alone, and list the evidence still needed to confirm root cause.
```

> **Caution:** Keep blame-free framing; final root cause must be confirmed with data by the owning engineer.

## 5. Chemical and gas safety briefing

**Task:** Understand hazards before working near a hazardous production material

```text
You are an EHS trainer for a semiconductor fab. I am about to support work on [TASK, e.g. gas cabinet cylinder change / wet bench maintenance] involving [CHEMICAL OR GAS, e.g. silane, HF, NF3, arsine]. Explain in plain language: the main hazards (toxicity, pyrophoricity, exposure limits), symptoms of exposure, which controls are typical (gas cabinets, exhausted enclosures, toxic gas monitoring, SEMI S2-compliant interlocks, PPE), and first-aid concepts such as calcium gluconate for HF. Format as a one-page pre-task briefing with a checklist of questions to ask my supervisor. State that site SDS and procedures override your summary.
```

> **Caution:** Educational only; follow the SDS, site EHS procedures and buddy/permit requirements. Never improvise on toxic or pyrophoric gas systems.

## 6. Equipment metrics for management

**Task:** Explain tool availability and downtime to managers

```text
Act as an equipment reliability analyst familiar with SEMI E10 (equipment states) and E79 (OEE). Data for [TOOL GROUP] over [PERIOD]: [PASTE HOURS IN PRODUCTIVE, STANDBY, ENGINEERING, SCHEDULED DOWN, UNSCHEDULED DOWN, NON-SCHEDULED; MTBF/MTTR; TOP DOWNTIME CAUSES]. Calculate availability, MTBF, MTTR and an approximate OEE, showing formulas. Then write a 150-word summary for a production manager who is not an equipment specialist: what is driving downtime, the top three improvement actions (e.g. spare parts stocking, PM interval change, FSE response), and what data is missing. Note any assumptions in the calculation.
```

> **Caution:** Verify numbers against your MES/automation system; E10 state definitions can be customized per site.

## 7. Cross-cultural tech transfer questions

**Task:** Get the most out of training from overseas engineers at a new US fab

```text
I am a new technician at a reshored fab [COMPANY TYPE/LOCATION, e.g. US site of an Asian foundry], learning [TOOL OR MODULE] from visiting engineers whose first language is [LANGUAGE]. Their written procedures are [DESCRIBE: translated, partial, diagrams only]. Help me: (1) prepare a list of precise, yes/no or numeric questions to capture tacit knowledge (tolerances, sounds/smells that signal trouble, typical failure parts); (2) a template for turning what I learn into a clear English work instruction with photos and checkpoints; (3) tips for respectful communication across work-culture differences. Keep it practical, not stereotyped.
```

> **Caution:** Procedures you write must go through your site's document control before use.

## 8. 90-day upskilling plan

**Task:** Build a learning plan from technician to advanced equipment tech

```text
Act as a semiconductor workforce training advisor. My background: [e.g. military avionics tech / 2-year electronics degree / no fab experience]. Current role: [ROLE AND AREA]. Goal in [TIMEFRAME]: [e.g. qualify on lithography track tools, become Level 2 equipment tech]. Create a 90-day plan with weekly themes covering: vacuum and RF fundamentals, plasma basics, cleanroom/contamination control (ISO 14644), SPC, SECS/GEM automation basics, and the specific module I named. For each week give concepts, a hands-on practice idea, a self-check question, and free or low-cost resources (e.g. community college fab programs, SEMI training, vendor courses). Mark anything that requires employer-provided access.
```

> **Caution:** Check that resources are current; employer qualification requirements take precedence.
