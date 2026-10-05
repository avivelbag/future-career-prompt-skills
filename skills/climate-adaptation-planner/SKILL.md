---
name: climate-adaptation-planner
description: "Prompt playbook for a climate adaptation planner. Use when a climate adaptation planner wants help with work tasks such as: hazard exposure screening; adaptation pathways comparison; hazard mitigation plan section; council briefing on heat; community meeting prep; resilience grant narrative; climate disclosure physical risk; learning plan: climate data skills."
---

# Climate adaptation planner prompts

Climate adaptation planners work for cities, counties, utilities, ports, consultancies and companies to turn climate projections into risk assessments, adaptation plans, hazard mitigation plans and disclosures, then fund and coordinate the projects. AI helps most with synthesizing projection data and guidance documents, drafting plan sections and grant narratives, structuring option comparisons, and translating technical risk for councils and residents.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Hazard exposure screening

**Task:** First-pass climate risk screen of a jurisdiction's assets

```text
You are a climate adaptation planner using ISO 14091 (vulnerability and risk assessment) as the framework. For [JURISDICTION/ORGANIZATION], screen these assets: [ASSET LIST WITH LOCATIONS, AGE, CRITICALITY]. Hazards to consider: [e.g. coastal flooding, extreme heat, riverine flood, wildfire, drought]. Using the projection sources I provide [e.g. NOAA 2022 sea level rise scenarios, LOCA2 downscaled CMIP6, FEMA National Risk Index excerpts], produce a table: asset, hazard, exposure, sensitivity, adaptive capacity, risk rating (low/med/high) for [TIME HORIZONS, e.g. 2050 and 2100], and data gaps. Flag any rating that depends on scenario choice, and state assumptions explicitly. Do not invent numbers not in my sources.
```

> **Caution:** A screening only; site-level decisions need engineering analysis and locally validated hazard data.

## 2. Adaptation pathways comparison

**Task:** Compare adaptation options with decision triggers

```text
Act as an adaptation planner applying the adaptation pathways approach (as used in the Thames Estuary 2100 plan). For [PLACE/SYSTEM] facing [HAZARD], compare these options: [e.g. elevate, protect with levee, nature-based living shoreline, managed retreat, do-minimum]. For each give: what it protects against and up to what threshold (e.g. sea level rise in feet or meters), lifetime, rough cost class from my inputs [COST DATA], co-benefits, equity impacts, maladaptation risks, and lock-in. Then propose a pathway map in text: which options to start with, measurable trigger points for switching, and lead times. List open questions I must resolve with engineers and the community.
```

> **Caution:** Cost and threshold figures must come from your own studies; Claude should not supply them.

## 3. Hazard mitigation plan section

**Task:** Draft a FEMA-compliant plan section from my notes

```text
You are helping update a local hazard mitigation plan under 44 CFR 201.6 and the current FEMA Local Mitigation Planning Policy Guide. Using my notes [PASTE RISK ASSESSMENT RESULTS, PLANNING PROCESS RECORDS, CAPABILITY ASSESSMENT], draft the [SECTION, e.g. mitigation strategy / risk assessment] for [JURISDICTION]. Integrate future conditions (climate projections) as the guide requires. Output: draft text with headings, a table of mitigation actions (action, hazard, responsible agency, funding source, timeline, priority rationale), and a checklist mapping the section to the relevant FEMA plan review elements, noting any element my notes don't yet satisfy.
```

> **Caution:** Confirm against the current FEMA guide version and your state hazard mitigation officer; requirements change.

## 4. Council briefing on heat

**Task:** Plain-language briefing for elected officials

```text
Write a 2-page briefing memo for [CITY] council on extreme heat risk and proposed actions. Audience: non-technical officials with budget authority. Inputs: [LOCAL HEAT DATA, e.g. days above 95F now vs. projected 2050], [HEAT-RELATED ER VISITS OR DEATHS], [VULNERABLE NEIGHBORHOODS, e.g. CDC SVI or tree canopy data], [PROPOSED ACTIONS AND COSTS]. Structure: the bottom line in 3 sentences, what is changing, who is most affected, options with cost and benefit, a recommendation, and what happens if we wait. Present uncertainty honestly (ranges, scenario names) without hedging the decision away. Avoid jargon; define any term you must use.
```

> **Caution:** Check every statistic against the source before it goes to council.

## 5. Community meeting prep

**Task:** Plan engagement for a contentious managed-retreat discussion

```text
I'm a climate adaptation planner preparing a community meeting in [NEIGHBORHOOD] about [TOPIC, e.g. future buyouts / rezoning in a projected flood zone]. Residents include [DEMOGRAPHICS, LANGUAGES, RENTERS VS. OWNERS, PAST GRIEVANCES]. Produce: a meeting agenda using IAP2 public participation principles, plain-language explanations of the hazard and the options, the 10 hardest questions residents are likely to ask with honest answers or 'we don't know yet' where true, accessibility and translation needs, and how input will visibly affect the decision. Flag anything that would be promising outcomes the city cannot guarantee.
```

> **Caution:** Do not let AI draft commitments about buyouts, property values or legal rights; route those to counsel and leadership.

## 6. Resilience grant narrative

**Task:** Draft a competitive grant or funding application

```text
Help me draft the project narrative for [FUNDING PROGRAM, e.g. FEMA Hazard Mitigation Grant Program, a state resilience fund, or a philanthropic program] for [PROJECT]. Paste-in materials: [NOFO SCORING CRITERIA], [PROJECT SCOPE], [BENEFIT-COST ANALYSIS RESULTS], [COMMUNITY DATA]. Output: a narrative organized exactly by the scoring criteria, with a word count per section within [LIMITS], a list of claims that need supporting documents, and weak spots a reviewer would score down. Note that federal program availability and priorities have changed recently; list what I should verify about the program's current status and eligibility.
```

> **Caution:** Never fabricate benefit-cost results or letters of support; verify the program is open.

## 7. Climate disclosure physical risk

**Task:** Map a physical risk assessment to disclosure frameworks

```text
I advise [COMPANY/UTILITY/PUBLIC ENTITY] on climate-related physical risk. Using our assessment [PASTE SUMMARY OF HAZARDS, SITES, FINANCIAL EXPOSURE], draft the physical risk and adaptation sections for [FRAMEWORK, e.g. IFRS S2, ESRS E1 under CSRD, California SB 261, or TCFD-aligned report]. Output: draft disclosure text, a table mapping each paragraph to the specific framework requirement, scenario analysis description (scenarios, horizons, limitations), and a list of statements that need audit evidence. Flag where regulatory requirements are in flux or delayed and where our data is too weak to support a quantitative claim.
```

> **Caution:** Disclosures carry legal liability; legal and assurance review is required before publication.

## 8. Learning plan: climate data skills

**Task:** Upskill on projections and tools

```text
I'm a [CURRENT ROLE, e.g. land use planner] moving into climate adaptation planning with [SKILLS, e.g. basic GIS, no coding]. Build me a 12-week learning plan covering: how CMIP6 scenarios (SSPs) and downscaling work and their limits, choosing between NOAA sea level rise scenarios, using tools like the U.S. Climate Resilience Toolkit, FEMA National Risk Index and NOAA Sea Level Rise Viewer, basics of benefit-cost analysis, ISO 14090/14091, and equity screening. For each week give objectives, free resources from real organizations (no invented links; say if unsure), a hands-on exercise using my region [REGION], and a self-check quiz of 3 questions.
```

> **Caution:** Verify that resources and tools still exist and are current; some federal climate sites have changed.
