---
name: wildfire-resilience-specialist
description: "Prompt playbook for a wildfire resilience specialist. Use when a wildfire resilience specialist wants help with work tasks such as: home ignition zone assessment report; cWPP section draft; red flag day operations checklist; utility wildfire mitigation plan gap check; resident risk explainer; fuels treatment prioritization; grant application narrative; upskilling plan for new codes and science."
---

# Wildfire resilience specialist prompts

Works for counties, fire districts, utilities, insurers and HOAs to cut wildfire risk to communities and infrastructure: home hardening and defensible-space assessments, Community Wildfire Protection Plans, utility wildfire mitigation plans, fuels projects and grant applications. AI helps most with turning field notes into standards-referenced reports, drafting plans and grant narratives, translating risk data for residents, and keeping up with fast-changing codes such as California's Zone 0 rules and NFPA 1140.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Home ignition zone assessment report

**Task:** Turn field notes from a parcel visit into a prioritized homeowner report

```text
You are a wildfire mitigation specialist writing a home ignition zone assessment. Using my field notes below, produce a homeowner report with: (1) a one-paragraph summary of the top risks; (2) a table organized by zone (Zone 0: 0-5 ft, Zone 1: 5-30 ft, Zone 2: 30-100 ft, plus the structure itself: roof, vents, eaves, gutters, decks, windows, fencing) listing each finding, why it matters for ember, radiant heat or flame contact, recommended fix, rough cost tier ($/$$/$$$), and priority. Reference NFPA 1140 / IBHS Wildfire Prepared Home and [LOCAL CODE, e.g. CA PRC 4291 or county ordinance] where relevant, and mark anything that is a legal requirement versus a recommendation. Jurisdiction: [JURISDICTION]. Notes: [FIELD NOTES].
```

> **Caution:** Verify every code citation against the current adopted version; Zone 0 rules and insurer discount criteria are still changing.

## 2. CWPP section draft

**Task:** Draft a section of a Community Wildfire Protection Plan

```text
Act as a planner helping update a Community Wildfire Protection Plan under the Healthy Forests Restoration Act. Draft the [SECTION, e.g. WUI boundary definition / risk assessment / prioritized fuel treatments / action plan] for [COMMUNITY], using these inputs: [DATA, e.g. Wildfire Risk to Communities scores, LANDFIRE fuel models, evacuation routes, past fire history, stakeholder meeting notes]. Use clear subsections, a table of prioritized projects with lead agency, timeline and funding source (e.g. Community Wildfire Defense Grant, FEMA BRIC/HMGP), and note where the plan requires concurrence from local government, the local fire authority and the state forestry agency. List data gaps and any assumptions I should verify.
```

> **Caution:** CWPP content must be agreed by the required signatories; treat the draft as a starting point for collaborative review.

## 3. Red flag day operations checklist

**Task:** Build a pre-event checklist for elevated fire weather

```text
I coordinate wildfire readiness for [ORGANIZATION TYPE, e.g. a utility district / county OES / HOA] in [REGION]. The NWS forecast shows [RED FLAG WARNING / FIRE WEATHER WATCH details: wind, RH, duration] and current fuel conditions are [ERC/fuel moisture or NFDRS indices]. Create a time-phased checklist (72 h, 24 h, 6 h, during, after) covering: internal staffing, communication with fire agencies, resident alerts, vulnerable-population outreach, evacuation route checks, [PSPS coordination if utility], and documentation to keep. Format as a table with owner role and done criteria. Flag any step that depends on decisions only the incident commander or authority having jurisdiction can make.
```

> **Caution:** Defer to official incident command, NWS and emergency alerts; this is planning support, not tactical fire guidance.

## 4. Utility wildfire mitigation plan gap check

**Task:** Review a draft utility WMP section against regulator expectations

```text
You are reviewing a draft section of an electric utility Wildfire Mitigation Plan for [STATE/REGULATOR, e.g. California OEIS under PUC 8386, or another state commission]. Here is the section on [TOPIC, e.g. vegetation management / covered conductor / PSPS / situational awareness]: [PASTE TEXT]. Compare it with the regulator guidance I paste here: [GUIDELINE EXCERPTS]. Output a table: requirement, where the draft addresses it, gap or weakness, suggested fix, and evidence needed (metrics, maps, data). Then list three questions a regulator or intervenor would likely ask. Do not assume requirements I haven't provided; mark any you infer as 'to verify'.
```

> **Caution:** Regulatory filings need legal and engineering sign-off; guidelines change each cycle.

## 5. Resident risk explainer

**Task:** Explain a wildfire risk score and actions in plain language

```text
Write a plain-language explainer (grade 7-8 reading level, under 400 words) for residents of [COMMUNITY] who just received [RISK PRODUCT, e.g. a state hazard severity zone map / an insurer wildfire score / a parcel assessment]. Explain what the rating measures and doesn't measure (hazard vs. risk vs. likelihood of a specific home burning), why embers cause most home losses, the five cheapest highest-impact actions, local help available [PROGRAMS/GRANTS/CHIPPER DAYS], and how to appeal or ask questions [CONTACT]. Provide an English version plus a [LANGUAGE] version, and keep tone calm and practical, not alarming.
```

> **Caution:** Have a native speaker check translations and confirm program details before distribution.

## 6. Fuels treatment prioritization

**Task:** Rank candidate fuel reduction projects with transparent criteria

```text
Help me prioritize fuel treatment projects for [AREA]. Candidates: [LIST with acreage, fuel type/LANDFIRE fuel model, slope, proximity to homes or evacuation routes, treatment type such as mastication, hand thinning, prescribed burn, grazing, cost, permitting status, environmental constraints]. Propose a weighted scoring matrix (explain each weight), score each project, and present a ranked table. Then do a sensitivity check: which rankings change if I weight evacuation-route protection or cost more heavily? Note permitting and environmental review (e.g. NEPA/CEQA, air quality smoke permits, endangered species, cultural resources) that could delay each project. State clearly which judgments need field verification or fire behavior modeling (e.g. FlamMap) rather than your estimate.
```

> **Caution:** Scoring is a decision aid; fire behavior outcomes require qualified modeling and field validation.

## 7. Grant application narrative

**Task:** Draft a Community Wildfire Defense Grant or FEMA mitigation narrative

```text
Draft the project narrative for a [GRANT, e.g. USDA Forest Service Community Wildfire Defense Grant / FEMA BRIC / state fire prevention grant] for [APPLICANT]. Project: [DESCRIPTION, scope, budget, match source, timeline]. Community context: [POPULATION, underserved/low-income status, risk data, CWPP reference]. Structure it to the scoring criteria I paste here: [CRITERIA]. Include measurable outcomes (acres treated, homes assessed/retrofitted, residents reached), a risk-reduction logic chain, partners, and sustainability after the grant. Keep within [WORD LIMIT]. After the draft, list any claims I must back with documentation.
```

> **Caution:** Do not let the draft overstate data; every statistic must be sourced before submission.

## 8. Upskilling plan for new codes and science

**Task:** Build a learning plan on wildfire codes, science and tools

```text
I'm a [BACKGROUND, e.g. former firefighter / planner / arborist] moving into wildfire resilience work in [REGION]. Create a 12-week learning plan covering: ember and structure ignition science (IBHS, NIST WUI research), relevant codes (NFPA 1140, ICC IWUIC, CBC Chapter 7A or local equivalent, defensible-space law), CWPPs and Firewise USA, fire behavior basics and tools (NWCG courses like S-190, FlamMap, Wildfire Risk to Communities), insurance and mitigation discount programs, and community engagement. Format as a weekly table with goals, specific resources, and a practical exercise. Note relevant certifications (e.g. NFPA Certified Wildfire Mitigation Specialist) and which areas are still unsettled policy I should keep tracking.
```

> **Caution:** Confirm course and certification availability with NWCG, NFPA and your state agency.
