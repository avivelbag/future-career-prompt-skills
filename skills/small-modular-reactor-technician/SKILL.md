---
name: small-modular-reactor-technician
description: "Prompt playbook for a small modular reactor technician. Use when a small modular reactor technician wants help with work tasks such as: condition report draft; surveillance data trending; work package pre-job brief; learn a new SMR design; regulatory change explainer; troubleshooting plan; community Q&A prep; shift turnover summary."
---

# Small modular reactor technician prompts

SMR technicians maintain, test and monitor the instrumentation, mechanical and radiation-protection systems of factory-built reactors such as NuScale, GE-Hitachi BWRX-300 (OPG Darlington, TVA Clinch River), X-energy Xe-100 and Kairos Hermes, working under NRC or CNSC licences and plant procedures. AI helps most with drafting condition reports and work packages, studying new designs and procedures, trending surveillance data, and preparing clear communication, while licensed staff and approved procedures keep every safety decision.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Condition report draft

**Task:** Turn rough field notes into a clear corrective action program entry

```text
You are a corrective action program (CAP) coordinator at a nuclear plant. Turn my field notes into a draft condition report. Notes: [WHAT I OBSERVED, WHEN, WHERE, EQUIPMENT ID, WHO WAS NOTIFIED]. Plant/design: [SMR DESIGN AND SITE]. Output: (1) a factual problem statement with no speculation about cause, (2) immediate actions taken, (3) the questions an operability or reportability reviewer will ask, so I can answer them, (4) any facts that are missing. Mark anything that might touch 10 CFR 50.72/50.73 reportability or Technical Specifications for the Shift Manager to decide; don't decide it yourself. Use plain, neutral language.
```

> **Caution:** Operability and reportability calls belong to licensed operators and Licensing; never paste safeguards or export-controlled information into a public AI tool.

## 2. Surveillance data trending

**Task:** Spot drift in instrument calibration or pump test results

```text
Act as an I&C reliability engineer. Below are as-found/as-left calibration results (or ASME OM inservice test data) for [COMPONENT/INSTRUMENT TAG, e.g. module level transmitter] over [TIME PERIOD]: [PASTE TABLE]. Acceptance criteria from the procedure: [LIMITS]. Analyze: trend direction and rate, any points near or past the alert/required action range, whether the drift suggests sensor aging, setpoint methodology issues or test error, and what to recommend raising under the 10 CFR 50.65 Maintenance Rule program. Give a short summary table, then reasoning. Show your calculations and say where the data is too sparse to conclude.
```

> **Caution:** This only screens the data for trends; the system engineer must formally evaluate results against Tech Spec and procedure limits.

## 3. Work package pre-job brief

**Task:** Prepare a pre-job brief and human-performance risk review

```text
You are a nuclear maintenance supervisor running a pre-job brief. The task is: [WORK ORDER SUMMARY] on [SYSTEM/COMPONENT] at [SMR SITE], under procedure [PROCEDURE NUMBER/TITLE, key steps pasted]. Plant conditions: [MODE, PROTECTED EQUIPMENT, RADIOLOGICAL CONDITIONS]. Produce a pre-job brief checklist: critical steps, error-likely situations, human performance tools for each (peer check, independent verification, three-way communication, STAR), stop/hold points, ALARA considerations, and what to do if conditions differ from the procedure. Keep it to one page. Do not change or add procedure steps; flag any step that looks unclear for a procedure change request instead.
```

> **Caution:** The approved procedure always governs; a brief from AI supports the supervisor's brief but does not replace it.

## 4. Learn a new SMR design

**Task:** Upskill from a large LWR background to a specific SMR design

```text
I am a [CURRENT ROLE, e.g. mechanical technician at a large PWR] transferring to a [SMR DESIGN, e.g. GE-Hitachi BWRX-300 / NuScale US460 / X-energy Xe-100] plant. Build a 6-week self-study plan comparing my current plant to the new design: passive safety systems and natural circulation, reactor coolant and decay-heat removal, instrumentation and control architecture, refueling approach, multi-module or remote-operation differences, and the maintenance tasks likely to change. For each week give learning goals, public sources to read (NRC/CNSC licensing documents, vendor public materials, IAEA SMR publications) and 5 self-check questions. Mark where public information is limited or the design is still under licensing review.
```

> **Caution:** Plant-specific training (INPO ACAD-accredited programs, systems lessons) is the authority; check AI-generated technical details against official documents.

## 5. Regulatory change explainer

**Task:** Understand how new or changing rules affect technician work

```text
Explain to a nuclear plant technician how [REGULATORY ITEM, e.g. NRC 10 CFR Part 53 risk-informed licensing framework / ADVANCE Act implementation / CNSC licence-to-construct conditions for Darlington BWRX-300] could affect day-to-day maintenance, surveillance testing, staffing and training at an SMR. Structure: what the rule is and its current status, what changes compared to 10 CFR Part 50/52, practical effects on my job, and open questions. State your knowledge cutoff, say which points may be outdated, and list the primary sources (Federal Register, NRC ADAMS, CNSC REGDOCs) I should check. Don't guess at the status of the rule.
```

> **Caution:** Rule status changes quickly; confirm against the Federal Register, NRC or CNSC sites and your plant's Licensing group.

## 6. Troubleshooting plan

**Task:** Structure a fault investigation without skipping steps

```text
Act as a senior I&C/electrical troubleshooter at a nuclear plant. Symptom: [SYMPTOM, alarms, indications, when it started]. Equipment: [COMPONENT, MODEL, SYSTEM, SAFETY CLASSIFICATION]. Recent work or changes: [RECENT MAINTENANCE, MODIFICATIONS]. Build a troubleshooting plan in the style of a structured troubleshooting worksheet: possible failure modes ranked by likelihood, evidence for and against each, the least invasive check that tells them apart, what I can check passively (data, logs, walkdown) versus what needs an approved work order, and when to stop and escalate. Flag any step that could affect redundancy, trip logic or Technical Specification equipment.
```

> **Caution:** Only do troubleshooting on plant equipment under an approved work order or troubleshooting plan, with operations' authorization.

## 7. Community Q&A prep

**Task:** Answer public questions about a new SMR plainly and honestly

```text
I'm a technician at [SMR SITE/PROJECT] and will be volunteering at a community open house in [TOWN]. Common questions: [LIST, e.g. radiation exposure, spent fuel storage, what happens in an emergency, local jobs]. Draft short, plain-language answers (under 80 words each) that are accurate, don't oversell safety, compare radiation doses to everyday sources using real figures from NRC or UNSCEAR, and say 'I don't know, here's who to ask' where it's outside my role. Mark any answer that should be checked by the communications or emergency preparedness team before I use it.
```

> **Caution:** Follow your employer's public communication policy; don't speak about security, incidents under review, or anything not already public.

## 8. Shift turnover summary

**Task:** Write a concise, complete turnover for the incoming technician

```text
Help me write a shift turnover for maintenance/I&C technicians at an SMR plant. Raw notes: [WORK COMPLETED, WORK IN PROGRESS WITH STATUS, EQUIPMENT OUT OF SERVICE, CLEARANCES/TAGOUTS HUNG, PARTS ON ORDER, ISSUES FOUND, RADIOLOGICAL AREAS ACCESSED]. Format it as: priorities for the next shift, open work with exact stopping point and next step, active clearances and LCO-related items to verify with operations, open questions. Keep it scannable in two minutes. Don't add information that isn't in my notes; list anything ambiguous separately so I can fix it before I leave.
```

> **Caution:** The incoming crew must still verify clearances and plant status in the official systems; the summary is not a substitute.
