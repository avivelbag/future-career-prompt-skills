---
name: modular-housing-assembler
description: "Prompt playbook for a modular housing assembler. Use when a modular housing assembler wants help with work tasks such as: station work instruction from shop drawings; mate-line fit-up troubleshooting; crane pick and set-day plan review; nonconformance report write-up; explaining modular to a homeowner or neighbor; weather and transport damage inspection checklist; site connection and inspection sign-off log; upskilling plan for a new assembler."
---

# Modular housing assembler prompts

Modular housing assemblers build volumetric modules or panels on factory lines (Factory_OS-style plants, HUD Code manufactured-home plants, state-approved modular builders) and then set, connect and finish them on site, working under ICC/MBI 1200/1205, state modular programs and third-party inspection. AI helps most with reading shop drawings and work instructions, planning set day and crane picks, troubleshooting fit-up and mate-line problems, writing QC and nonconformance records, and learning codes and new joining methods.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Station work instruction from shop drawings

**Task:** Turn a module's shop drawings and spec notes into a clear step-by-step station instruction

```text
You are a lead assembler in a volumetric modular housing factory. Below are the notes and dimensions from the shop drawings for module [MODULE ID] at station [STATION, e.g. wall framing / MEP rough-in / drywall]: [PASTE DRAWING NOTES, FASTENING SCHEDULE, DIMENSIONS]. Write a one-page station work instruction: required materials and tools, numbered steps in build order, fastening and tolerance callouts, hold points where QC or the third-party inspector must sign off before covering work, and common mistakes to watch for. Flag anything in the notes that is ambiguous or conflicts, as a question for engineering, instead of guessing.
```

> **Caution:** Engineering drawings and the approved plan set govern; confirm any change with the design engineer before building.

## 2. Mate-line fit-up troubleshooting

**Task:** Diagnose why modules are not lining up on site and pick a fix

```text
Act as an experienced modular set foreman. On set day we stacked/joined modules [MODULE IDS] and found: [DESCRIBE PROBLEM, e.g. 12 mm gap at marriage wall, floor height mismatch of X mm, out-of-square opening]. Foundation/podium survey data: [PASTE OR SUMMARIZE]. Factory as-built dimensions: [PASTE]. List the likely causes ranked by probability (foundation tolerance, module racking in transport, factory dimensional error, lifting distortion, etc.), what to measure to confirm each, and acceptable correction options. Clearly separate fixes a crew can do from ones that need engineer of record approval, and note which would affect fire-rated or structural connections.
```

> **Caution:** Never shim, cut or modify structural or fire-rated connections without written approval from the engineer of record.

## 3. Crane pick and set-day plan review

**Task:** Check a set-day sequence and rigging plan for gaps before the crane arrives

```text
You are helping a modular installation crew prepare for set day. Project: [NUMBER OF MODULES, STORIES, SITE CONDITIONS]. Crane: [CRANE TYPE, CAPACITY, RADIUS]. Module weights and pick points: [LIST]. Draft set sequence: [PASTE]. Review the plan and produce: a checklist of pre-lift items (lift plan sign-off, qualified rigger and signal person per OSHA 1926 Subpart CC, wind limits, exclusion zones, tag lines, ground bearing), questions about the sequence order or weather protection of open modules, and a short toolbox-talk script for the crew. Do not calculate final rigging loads; list what the lift planner must verify.
```

> **Caution:** Lift plans and rigging calculations must be prepared and approved by a qualified person; this is a review aid only.

## 4. Nonconformance report write-up

**Task:** Write a clear NCR from rough notes and photos taken on the line

```text
You are a quality technician in a modular home factory operating under a third-party inspection program (state modular program or HUD Code, 24 CFR 3280, as applicable: [WHICH]). From these rough notes: [PASTE NOTES, MODULE ID, STATION, PHOTO DESCRIPTIONS], write a nonconformance report with: description of the defect, requirement it violates (cite drawing or spec section I give you; if I gave none, say 'requirement to be confirmed'), extent (which other modules may be affected), containment action, proposed disposition options (rework, use-as-is pending engineering, scrap), and root-cause questions. Keep it factual and neutral; no blame.
```

> **Caution:** Do not let AI invent code citations; verify every referenced requirement against the approved documents.

## 5. Explaining modular to a homeowner or neighbor

**Task:** Answer common public questions about a modular project in plain language

```text
I am a site lead installing a modular [SINGLE-FAMILY HOME / MULTIFAMILY BUILDING] in [CITY/REGION]. Neighbors and the buyer asked: [PASTE QUESTIONS, e.g. Is it a trailer? Will it be as strong? How loud is crane day? How long will the road be closed?]. Draft a short, friendly handout (under 300 words) answering these honestly in plain language, explaining the difference between modular built to local building code and HUD Code manufactured homes where relevant, plus a set-day schedule section with [DATES, ROAD CLOSURE DETAILS, CONTACT]. Avoid promises about cost, resale value or warranty I haven't stated.
```

> **Caution:** Have the project manager approve anything that mentions schedules, warranties or code compliance before it goes out.

## 6. Weather and transport damage inspection checklist

**Task:** Build a receiving inspection checklist for modules arriving on site

```text
You are a modular installation QC lead. Modules for [PROJECT] travel [DISTANCE] by truck and may sit on site [DAYS] before set; expected weather: [CONDITIONS]. Create a receiving inspection checklist organized by area (exterior wrap and weather protection, structure and racking, openings, MEP stubs and mate-line connections, interior finishes, moisture), with what to look for, how to measure or photograph it, and a pass/hold/reject column. Add a section on moisture risk to wood framing and drywall and when to call for moisture readings before closing in.
```

> **Caution:** Hidden damage may need engineer or manufacturer assessment; document and escalate rather than conceal.

## 7. Site connection and inspection sign-off log

**Task:** Organize the site-completed work list and inspection sign-offs for the local building official

```text
You are assisting a modular set crew on a project inspected under [STATE MODULAR PROGRAM / LOCAL JURISDICTION] with site work governed by ICC/MBI 1205-style inspection splits between factory and site. Here is the list of site-completed scope: [PASTE, e.g. inter-module structural ties, fire-stopping at mate lines, plumbing and electrical crossovers, roof closure]. Build a table: item, which party performs it, applicable inspection (factory third-party vs local building inspector), required evidence (photos, test reports, labels), status, and open questions. Flag items where responsibility between factory and site is commonly unclear.
```

> **Caution:** Inspection jurisdiction splits vary by state and project; confirm with the authority having jurisdiction.

## 8. Upskilling plan for a new assembler

**Task:** Create a learning plan to move from general carpentry into modular assembly and set work

```text
I am a [CURRENT ROLE, e.g. framer, factory line worker] who wants to become a lead modular housing assembler within [TIMEFRAME]. My current skills: [LIST]. Create a learning plan covering: reading shop drawings and BIM/module viewers, off-site construction standards (ICC/MBI 1200 and 1205, HUD Code basics if relevant), lean manufacturing and takt-time line work, rigging and signal-person qualification, fire-stopping and mate-line details, and QC documentation. For each, suggest concrete ways to learn (certifications, trade association courses such as from the Modular Building Institute, on-the-job tasks) and a self-test question. Note which credentials are required versus nice to have in [REGION].
```

> **Caution:** Certification and licensing requirements differ by state and country; check with your employer and local authorities.
