---
name: digital-fashion-designer
description: "Prompt playbook for a digital fashion designer. Use when a digital fashion designer wants help with work tasks such as: virtual sample review checklist; multi-platform asset spec; drop launch troubleshooting; iP and trademark pre-check; client brief to collection plan; sustainability claim review; explaining digital fashion to a buyer; upskilling roadmap."
---

# Digital fashion designer prompts

Designs garments that exist only (or first) as 3D assets: virtual samples for brands using CLO3D, Browzwear or Style3D, AR try-on filters, and wearables for games and platforms like Roblox, Fortnite and Zepeto. AI helps most with technical asset specs and QA checklists, platform rule and IP checks, collection briefs, client communication and learning new pipelines like OpenUSD.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Virtual sample review checklist

**Task:** QA a 3D garment before it goes to the brand for sign-off

```text
You are a senior 3D apparel technical designer. I'm reviewing a virtual sample built in [CLO3D / Browzwear VStitcher / Style3D] for [BRAND], style [STYLE NAME], fabric [FABRIC + PHYSICAL PROPERTIES OR U3M/xTex FILE SOURCE], on avatar [AVATAR / SIZE]. Known issues so far: [NOTES]. Write a QA checklist grouped as: pattern and grading, fabric physics and drape, fit on avatar (strain/pressure map readings), trims and stitching, texture/UV and colorway accuracy, and render settings. For each item give what to check, what 'pass' looks like, and the likely fix if it fails. End with the 3 issues most likely to make the physical sample differ from the digital one.
```

> **Caution:** A digital fit check does not replace a physical fit sample until the brand has validated its fabric data against real swatches.

## 2. Multi-platform asset spec

**Task:** Plan one garment's export to several game/AR platforms

```text
Act as a technical artist for digital fashion. I need to ship [GARMENT DESCRIPTION] to [PLATFORMS, e.g. Roblox layered clothing, Snapchat Lens Studio, Zepeto, a glTF web viewer]. Source file: [TOOL + POLY COUNT + TEXTURE RESOLUTION + RIG STATUS]. Produce a table with one row per platform: target format (FBX, glTF/GLB, USDZ etc.), triangle and texture budgets, rigging/cage requirements, PBR material setup, and submission or moderation steps. Only state limits you are confident are current; mark anything that may have changed as 'verify in current docs' and list the doc page I should check. Then suggest an order of work that avoids re-doing topology.
```

> **Caution:** Platform limits and creator rules change often; confirm against each platform's current documentation before submitting.

## 3. Drop launch troubleshooting

**Task:** Diagnose why a digital garment looks wrong in try-on or in-game

```text
You are debugging a digital fashion asset. Symptoms: [e.g. clipping at the elbows, texture stretching, shimmering at distance, cloth popping during animation] seen in [PLATFORM / ENGINE / AR SDK] on [DEVICES]. Pipeline: [SOURCE TOOL] -> [RETOPO/UV TOOL] -> [EXPORT FORMAT] -> [PLATFORM]. Relevant settings: [LOD, NORMAL MAP SPACE, SKIN WEIGHTS, CAGE, SIMULATION]. Give a ranked list of probable causes, a quick test that confirms or rules out each, and the fix. Flag any cause that I can only confirm by inspecting the file myself.
```

## 4. IP and trademark pre-check

**Task:** Screen a collection for IP risk before release

```text
Act as a careful research assistant (not a lawyer) to a digital fashion studio. Before releasing [COLLECTION NAME] on [PLATFORMS / MARKETS], list the IP questions I should raise with counsel. Inputs: design references [REFERENCES / MOODBOARD SOURCES], any logos, patterns or brand names used [LIST], AI tools used in creation [TOOLS], licensed assets [TEXTURES, FONTS, BASE MESHES + LICENSES]. Cover trademark (e.g. lessons from Hermès v. Rothschild over MetaBirkins), copyright in garment graphics vs. unprotected garment shapes, licence terms of base meshes and textures, and the unsettled copyrightability of AI-generated elements. Output a risk table: item, issue, why it matters, question for counsel.
```

> **Caution:** Not legal advice; IP law for virtual goods and AI-generated designs varies by country and is still developing. Have counsel review before release.

## 5. Client brief to collection plan

**Task:** Turn a brand brief into a scoped digital collection plan

```text
You are a creative producer at a digital fashion studio. Client brief: [PASTE BRIEF]. Budget [BUDGET], deadline [DATE], team [ROLES + HOURS], channels [e.g. e-commerce virtual samples, AR try-on, game skins, campaign renders]. Draft a collection plan with: concept summary in 3 sentences, look list with complexity rating, deliverables per channel with file specs, a week-by-week schedule with review gates, assumptions, and the questions I must ask the client before signing. Flag any part of the brief that is likely out of scope for the budget.
```

## 6. Sustainability claim review

**Task:** Check marketing claims about digital sampling and virtual fashion

```text
Act as a compliance-minded editor. Our marketing copy says: [PASTE COPY], e.g. claims that digital sampling cuts waste or carbon by [X%]. Evidence available: [STUDIES, INTERNAL DATA, METHOD]. Review each claim against greenwashing rules, including the EU Green Claims and Empowering Consumers for the Green Transition directives, the UK CMA Green Claims Code and the US FTC Green Guides as relevant to [MARKETS]. For each claim, say whether the evidence supports it, suggest safer wording, and note what substantiation we would need. Flag where the rules are still being finalised.
```

> **Caution:** Regulatory status of the EU green-claims rules has shifted; confirm current requirements with counsel or a compliance specialist.

## 7. Explaining digital fashion to a buyer

**Task:** Write a plain-language pitch or FAQ for a traditional fashion stakeholder

```text
You are a digital fashion lead writing for [AUDIENCE, e.g. a merchandising director / factory partner / retail buyer] who is skeptical of 3D. Explain how [SPECIFIC WORKFLOW, e.g. 3D virtual sampling replacing first and second proto rounds] works at our company, using our numbers where available: [SAMPLE COUNTS, LEAD TIMES, COSTS]. Write a one-page FAQ with 8 questions they are likely to ask (accuracy of fit, fabric data, factory handoff via tech pack, who approves), honest answers including limits, and a proposed small pilot. No hype; use clear placeholders where I lack data.
```

> **Caution:** Do not quote savings figures that your own pilot has not measured.

## 8. Upskilling roadmap

**Task:** Plan learning for a new pipeline or role step

```text
Act as a mentor in digital fashion. My background: [e.g. fashion design graduate who knows CLO3D basics / 3D game artist new to garment patterns]. Goal in [TIMEFRAME]: [e.g. ship Roblox layered clothing, set up an OpenUSD-based asset pipeline, build AR try-on in Lens Studio, learn pattern making and grading]. Hours per week: [HOURS]. Create a weekly plan with concrete exercises, one portfolio piece per phase, free or official learning sources (vendor docs, Alliance for OpenUSD material, platform creator hubs), and self-check criteria. Point out the fundamentals from physical garment construction I must not skip.
```
