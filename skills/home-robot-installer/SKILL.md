---
name: home-robot-installer
description: "Prompt playbook for a home robot installer. Use when a home robot installer wants help with work tasks such as: pre-install home site survey; household hazard and risk assessment; privacy and data setup review; commissioning troubleshooting log; family handover guide; install-day schedule and parts plan; incident and near-miss report; standards and skills upskilling plan."
---

# Home robot installer prompts

Field technicians who survey homes, set up and commission household robots (from today's robot vacuums, lawn mowers and Astro-style home monitors to early humanoids such as 1X NEO), configure safety zones, Wi-Fi and smart-home links, and train families to live with them. Claude helps most with site-survey checklists, hazard and privacy reviews, plain-language handover guides, troubleshooting logs and keeping up with fast-moving safety standards like ISO 13482, UL 3300 and the EU Machinery Regulation.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Pre-install home site survey

**Task:** Turn a walkthrough into a readiness report and install plan

```text
You are a lead installer for household service robots. From my walkthrough notes below, produce a site-readiness report for installing a [ROBOT MODEL / TYPE, e.g. wheeled home assistant, humanoid, robotic mower]. Notes: [ROOM-BY-ROOM NOTES: floor types, thresholds, stairs, rug edges, cables, Wi-Fi signal readings, charging outlet locations, pets, children, mobility aids, fragile items]. Output: (1) a table of each area with Go / Fix first / Keep-out, and the reason; (2) a prioritized list of fixes for the homeowner before install day; (3) a charging-dock placement recommendation; (4) open questions to confirm with the manufacturer's install guide. Do not assume capabilities the robot's spec sheet [PASTE SPECS] doesn't state.
```

> **Caution:** The manufacturer's install manual and spec sheet override any general recommendation.

## 2. Household hazard and risk assessment

**Task:** Draft a home-specific risk assessment before commissioning

```text
Act as a safety engineer familiar with ISO 13482 (personal care robots), ISO 12100 risk assessment method and UL 3300. For a [ROBOT TYPE, MASS, SPEED, PAYLOAD, MANIPULATOR Y/N] being installed in a home with [OCCUPANTS: e.g. toddler, elderly person with walker, dog] and [LAYOUT FEATURES: stairs, pool, kitchen with gas range], draft a risk assessment table: hazard, who is exposed, scenario, severity, likelihood, existing robot safeguard (from the spec: [PASTE]), additional mitigation (no-go zones, gates, schedule limits, supervision), and residual risk. Flag any hazard where you're unsure the robot's certified safety functions cover it, and list what I should ask the manufacturer.
```

> **Caution:** A draft only; a qualified person signs off, and certification claims must come from the manufacturer's documentation.

## 3. Privacy and data setup review

**Task:** Configure cameras, mics and cloud settings with informed consent

```text
I'm installing a [ROBOT MODEL] with [SENSORS: cameras, microphones, lidar, room mapping] and [CLOUD FEATURES / TELEOPERATION: e.g. remote human operator can take over]. The household is in [COUNTRY / STATE]. Using the vendor privacy policy and settings below [PASTE], produce: (1) a plain-language summary of what data is collected, where it goes and who can see it, including any remote operators; (2) a recommended privacy settings checklist for this family (bedrooms, bathrooms, guests, children); (3) consent points I must explain to every adult resident; (4) relevant laws to check (e.g. GDPR, CCPA/CPRA, BIPA, COPPA) with a note that I'm not giving legal advice. Flag anything in the policy that is vague.
```

> **Caution:** Not legal advice; escalate unclear data practices to your employer or the vendor.

## 4. Commissioning troubleshooting log

**Task:** Diagnose a failed mapping, docking or connectivity issue

```text
You are a senior field service engineer for home robots. During commissioning of a [ROBOT MODEL, FIRMWARE VERSION], the robot [SYMPTOM: e.g. loses localization in the hallway, fails to dock, drops off Wi-Fi, won't pair over Matter/Thread]. Environment: [FLOORING, LIGHTING, MIRRORS/GLASS, ROUTER MODEL, MESH NODES, 2.4/5 GHz bands]. Error codes/logs: [PASTE]. Steps already tried: [LIST]. Give me a ranked list of likely causes, a step-by-step diagnostic sequence starting with the least invasive checks, what evidence would confirm each cause, and when to stop and escalate to vendor support. Do not suggest opening the chassis, battery work or firmware modifications outside the vendor's service procedures.
```

> **Caution:** Never bypass safety interlocks or modify battery packs; follow the vendor's service authorization.

## 5. Family handover guide

**Task:** Write a one-page owner guide tailored to the household

```text
Write a friendly one-page handover guide for the [FAMILY NAME] household after I installed their [ROBOT MODEL]. Readers include [e.g. an 80-year-old with low vision, a teenager, a Spanish-speaking caregiver]. Include: what the robot will and won't do; how to stop it immediately (emergency stop: [DESCRIBE]); the no-go zones I set and why; daily/weekly care (charging, cleaning sensors, emptying bins); what normal vs. worrying behaviour looks like; privacy controls; and who to call [SUPPORT CONTACT]. Use short sentences and headings, at a 6th-grade reading level. Then provide a [LANGUAGE] translation and flag any terms that should be checked by a native speaker.
```

> **Caution:** Check every instruction against the official manual before handing it over.

## 6. Install-day schedule and parts plan

**Task:** Plan a multi-robot or multi-home install day

```text
Help me plan installs for [DATE]. Jobs: [LIST: address, robot type, scope, e.g. vacuum + mower + humanoid onboarding, customer constraints]. Resources: [TECHNICIANS, VEHICLE, PARTS AND DOCKS IN STOCK, TOOLS]. Typical durations: [YOUR ESTIMATES]. Produce a time-blocked schedule with travel buffers, a per-job parts and tools pick list, pre-arrival customer messages (what to clear, pets secured, Wi-Fi password ready), and a contingency plan if a job overruns or a robot arrives damaged. Point out any job where my time estimate looks unrealistic and why.
```

## 7. Incident and near-miss report

**Task:** Document a robot incident clearly for the vendor and employer

```text
Draft a factual incident report about a [NEAR-MISS / INJURY / PROPERTY DAMAGE] involving a [ROBOT MODEL, FIRMWARE] at a customer home on [DATE]. My notes: [WHAT HAPPENED, WHO WAS PRESENT, ROBOT MODE (autonomous/teleoperated), LOGS OR VIDEO AVAILABLE, IMMEDIATE ACTIONS]. Structure: summary, timeline, conditions, immediate actions, data preserved, possible contributing factors (clearly marked as hypotheses, not conclusions), and follow-up actions with owners. Also list reporting channels I should check, such as my employer's procedure, the manufacturer, and a product safety regulator (e.g. CPSC SaferProducts.gov in the US or the EU Safety Gate in Europe), noting thresholds I should verify.
```

> **Caution:** Stick to facts; do not assign blame or speculate on liability in the report. Preserve logs before any reset.

## 8. Standards and skills upskilling plan

**Task:** Build a learning plan as home robots evolve

```text
I'm a home robot installer with a background in [e.g. smart-home AV installs / appliance repair / electrician]. I want to be qualified to install and maintain [e.g. humanoid household robots] within [TIMEFRAME]. Create a 12-week learning plan covering: robot safety standards (ISO 13482, ISO 12100, UL 3300, and the EU Machinery Regulation 2023/1230 and AI Act if I work in the EU); lithium-ion battery safety; networking (Wi-Fi mesh, Matter/Thread); basic ROS/mapping concepts; and customer-facing privacy explanations. For each week give goals, free or vendor resources to look for, and a hands-on exercise. Mark which standards are settled vs. still being drafted for humanoids, and say where you're uncertain.
```

> **Caution:** Verify current standard editions and any vendor certification requirements yourself; this area is changing quickly.
