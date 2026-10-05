---
name: lunar-construction-engineer
description: "Prompt playbook for a lunar construction engineer. Use when a lunar construction engineer wants help with work tasks such as: landing pad trade study; design basis environment memo; regolith simulant test plan; robotic construction sequence; hazard analysis for surface works; explain design to non-engineers; requirements and verification review; upskilling plan."
---

# Lunar construction engineer prompts

Lunar construction engineers design and plan surface infrastructure such as landing pads, berms, roads, habitat foundations and regolith-based structures, today mostly in NASA and contractor R&D (Artemis, LSIC, ICON's Project Olympus, MMPACT) and later on site for Artemis-era bases. AI helps most with trade studies, design-basis and requirements documents, test planning with regolith simulants, risk analysis for plume, dust, thermal and radiation loads, and explaining a field with few settled standards.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Landing pad trade study

**Task:** Compare options for a lunar landing pad that resists plume-surface interaction

```text
You are a lunar surface infrastructure engineer supporting an Artemis-era base study. Compare these landing pad concepts: [OPTIONS, e.g. sintered regolith, polymer-stabilized regolith, interlocking pavers, unprepared site with berm]. Context: lander class [LANDER MASS / THRUST / ENGINE TYPE], site [SOUTH POLE SITE, SLOPE, REGOLITH DATA], available equipment and power [ASSETS]. Assess each concept on plume-surface interaction and ejecta risk, required mass delivered from Earth, energy per square meter, construction time, robotic feasibility, and technology readiness. Return a weighted trade matrix with your weights stated, a short paragraph per option, and a list of data gaps where published test results (e.g. NASA PSI studies, LSIC reports) are thin or missing. Mark estimates clearly as estimates.
```

> **Caution:** Numbers from the model are first-order; check them against NASA PSI test data and run CFD and ejecta models before using them in design.

## 2. Design basis environment memo

**Task:** Draft the environmental design-basis section for a surface structure

```text
Draft the environment section of a design-basis document for [STRUCTURE, e.g. a regolith-shielded habitat foundation] at [SITE / LATITUDE]. Cover thermal cycling and permanently shadowed region temperatures, vacuum, lunar dust abrasion and electrostatic behaviour, micrometeoroid flux, radiation (GCR and SPE), seismic activity (shallow moonquakes), and 1/6 g effects on bearing capacity and compaction. For each item, give a design parameter or range, the source to cite (e.g. NASA SLS-SPEC-159 Cross-Program Design Specification for Natural Environments, Apollo data, LRO measurements), and the confidence level. Format as a table followed by open questions for the project's environments lead. Do not invent document numbers; write [VERIFY SOURCE] where unsure.
```

> **Caution:** Confirm every parameter against the current revision of the governing NASA environments specification before baselining.

## 3. Regolith simulant test plan

**Task:** Plan a terrestrial test campaign for a regolith construction material

```text
Act as a geotechnical and materials test engineer. I am qualifying [PROCESS, e.g. microwave sintering, laser melting, geopolymer binder] for [APPLICATION]. Simulant(s) available: [e.g. LHS-1, LMS-1, JSC-1A]. Budget and facilities: [TVAC CHAMBER, FURNACE, LOAD FRAMES, BUDGET]. Write a test plan with objectives, test matrix (variables, levels, replicates), specimen geometry, applicable ASTM test methods for compression, flexure and thermal cycling adapted to vacuum, and pass/fail criteria tied to [REQUIREMENT]. Include a section on how simulant differs from real regolith (agglutinates, glass content, particle shape, polar volatiles) and what that means for interpreting results. Output as a numbered plan with a table.
```

> **Caution:** Simulant results do not transfer directly to real regolith; state that limitation in any report built from this plan.

## 4. Robotic construction sequence

**Task:** Plan the sequence and power budget for an autonomous construction task

```text
You are planning a robotic construction campaign at [SITE] using [ROBOTS / TOOLS, e.g. excavator rover, 3D printing gantry]. The task is to build [STRUCTURE, e.g. a 2 m berm around a fission power unit or a 50 m road]. Constraints: available power [kW] and how it changes with the illumination schedule [DATA], comms latency and windows [DATA], tool wear limits, thermal limits in shadow, and how much the crew is involved [NONE / EVA SUPPORT]. Produce a phased construction sequence with durations, a power and duty-cycle table, hold points for inspection, fault-recovery steps for a stuck or failed robot, and the three assumptions with most effect on the schedule. Call out which steps need human-in-the-loop approval.
```

> **Caution:** Hold points and go/no-go calls stay with the mission's responsible engineer, not an automated plan.

## 5. Hazard analysis for surface works

**Task:** Draft a hazard analysis for a construction operation near crew and assets

```text
Help me draft a preliminary hazard analysis for [OPERATION, e.g. regolith excavation and berm placement 200 m from a habitat]. List hazards including dust transport onto seals, optics and radiators, ejecta from nearby landings, collapse of excavated slopes in low gravity, robot-crew collisions, thermal and electrical faults, and damage to neighbouring operators' assets. For each, give cause, effect, severity and likelihood category in the style of NASA hazard reports (aligned with NPR 8705 and NASA-STD-3001 where crew are involved), proposed controls, and how each control would be verified. Add a note on coordination and notification obligations under the Artemis Accords (Section 11, deconfliction/safety zones). Output as a table, then a list of items needing a safety panel decision.
```

> **Caution:** This is a draft for review; the formal hazard analysis must go through the program's safety and mission assurance process.

## 6. Explain design to non-engineers

**Task:** Brief program managers, policymakers or the public on a construction approach

```text
Rewrite the following technical summary for [AUDIENCE, e.g. program managers, congressional staff, a general public blog]. Technical summary: [PASTE]. Explain what is being built, why building with lunar materials (ISRU) instead of shipping everything from Earth matters, what has actually been demonstrated on Earth versus what is still unproven on the Moon, and the main risks in plain language. Keep it under [WORD COUNT] words, use one concrete analogy, avoid hype, and end with three questions this audience is likely to ask, with honest short answers. Flag any claims in my summary that seem stronger than the evidence supports.
```

> **Caution:** Check export-control (ITAR/EAR) limits before sharing technical details publicly.

## 7. Requirements and verification review

**Task:** Review structural requirements for gaps and verifiability

```text
Act as a systems engineer reviewing lunar surface structure requirements. Here are the requirements: [PASTE REQUIREMENTS]. For each one, check whether it is clear, measurable and verifiable, and say which verification method fits (test, analysis, inspection, demonstration) given that full-scale lunar testing is not possible. Flag requirements that conflict, use undefined loads or factors of safety, or ignore structural standards such as NASA-STD-5001 or an agreed adaptation of terrestrial codes (e.g. ACI, ASCE). Point out missing requirements for dust, thermal cycling, maintenance and end-of-life. Output a table with the requirement ID, the issue, a suggested rewrite and the verification method, then a list of decisions for the design authority.
```

> **Caution:** No settled building code exists for lunar structures; the program must decide and record which standards apply.

## 8. Upskilling plan

**Task:** Build a learning plan to move into lunar construction from a terrestrial field

```text
I am a [CURRENT ROLE, e.g. geotechnical engineer, structural engineer, construction robotics developer] with [YEARS] years of experience who wants to work in lunar surface construction. Build a 6-month learning plan, [HOURS] hours per week. Cover lunar geology and regolith mechanics, the space environment, ISRU, space systems engineering (NASA Systems Engineering Handbook), the Artemis program and Moon to Mars architecture, and policy (Outer Space Treaty, Artemis Accords). Recommend specific real resources (e.g. the Lunar Sourcebook, LSIC working groups, ASCE Earth and Space conference proceedings, NASA Technical Reports Server) and one hands-on project per month. Finish with the organizations hiring today and the skills they ask for, noting where my information may be outdated.
```

> **Caution:** Check that resources and employers are still current; this field changes quickly.
