---
name: virtual-world-builder
description: "Prompt playbook for a virtual world builder. Use when a virtual world builder wants help with work tasks such as: world design document; script bug triage; performance budget triage; trust and safety review; live-ops data analysis; asset pipeline and licensing plan; community update post; skill-up plan for new tooling."
---

# Virtual world builder prompts

Virtual world builders design, script and run persistent 3D spaces on platforms like Roblox, Fortnite UEFN, Unreal, Unity and OpenUSD-based tools, for game studios, brands, educators and creator teams. AI helps most with design docs, scripting and debugging, performance triage, safety and age-rating compliance, live-ops analysis, and communicating with clients and player communities.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. World design document

**Task:** Turn a client brief into a structured world design doc

```text
You are a senior virtual world designer. Turn this brief into a world design document for [PLATFORM, e.g. Roblox / Fortnite UEFN / Unity on Quest 3]. Brief: [CLIENT BRIEF]. Audience: [AGE RANGE AND REGIONS]. Session length target: [MINUTES]. Include: core fantasy and loop, zone map described as a list of areas with purpose and traversal links, social features, progression and economy (flag anything resembling paid random rewards), onboarding for first 5 minutes, accessibility considerations, and a performance budget section with assumptions I must verify. Output as headed sections with a final 'Open questions for client' list.
```

> **Caution:** Economy and monetization choices for minors face platform rules and national laws; confirm with the platform's current policies and counsel.

## 2. Script bug triage

**Task:** Debug a world script error or desync

```text
Act as an experienced [LANGUAGE, e.g. Luau / Verse / C# / Blueprint-to-C++] engineer for multiplayer worlds. Here is the script: [CODE]. Here is the error or behavior: [ERROR LOG OR DESCRIPTION]. It happens when [REPRO STEPS], with [NUMBER] concurrent players. Identify the most likely root causes ranked by probability, explain any client/server authority or replication problem, and propose a minimal fix with the changed code only. Then list exploit risks (e.g. trusting client input) and a quick test plan. Say clearly if you are unsure of a platform API's current behavior.
```

> **Caution:** Verify API behavior against current platform docs; APIs on Roblox and UEFN change frequently.

## 3. Performance budget triage

**Task:** Find why a world misses its frame-rate or memory target

```text
You are a real-time performance specialist for [ENGINE / PLATFORM]. Target device: [DEVICE, e.g. Meta Quest 3 at 72 Hz, mid-range Android phone]. Here is profiler data: [PASTE STATS: frame time, draw calls, triangle count, texture memory, script time, network bandwidth]. Scene description: [ZONES, ASSET COUNTS, LIGHTING, PARTICLES]. Diagnose the top 3 bottlenecks, quantify how far over budget each is, and propose fixes ordered by impact versus effort (LODs, instancing, streaming, texture compression, baked lighting, culling). Output a table plus a short re-test checklist.
```

## 4. Trust and safety review

**Task:** Pre-launch safety and content-rating check

```text
You are a trust-and-safety reviewer for user-facing virtual worlds. Review this world for launch on [PLATFORM] targeting [AGE RANGE] in [REGIONS]. World features: [LIST: voice/text chat, user-generated content, trading, private spaces, avatar customization, data collected]. Map risks against the platform's content maturity guidelines, and note where regimes like COPPA, the UK Online Safety Act / Age Appropriate Design Code, or the EU Digital Services Act may apply. Output a risk table (feature, harm, likelihood, mitigation, owner) and a list of questions for legal counsel. Flag anything you are uncertain about rather than guessing.
```

> **Caution:** Not legal advice; final compliance decisions belong to the publisher and counsel.

## 5. Live-ops data analysis

**Task:** Interpret engagement and retention data after an update

```text
You are a live-ops analyst for a persistent virtual world. Here is data before and after update [UPDATE NAME, DATE]: [PASTE: DAU, D1/D7 retention, average session length, funnel drop-off by zone, concurrent peak, revenue if any]. Changes shipped: [CHANGELOG]. Separate likely causal effects from noise, seasonality or external events ([KNOWN EVENTS]). Identify which zones or features are underperforming, give 3 hypotheses with the experiment or extra data needed to test each, and recommend what to change next. Present as a brief with one summary chart description.
```

> **Caution:** Small sample sizes and platform algorithm changes can mimic effects; treat conclusions as hypotheses.

## 6. Asset pipeline and licensing plan

**Task:** Plan an interoperable, properly licensed asset pipeline

```text
You are a technical art lead. I am building [WORLD] for [PLATFORM(S)] and want assets reusable across engines. Current sources: [LIST: in-house DCC tools, marketplace packs, AI-generated assets, photogrammetry scans, client brand assets]. Propose a pipeline using open formats where suitable (OpenUSD, glTF 2.0, MaterialX), naming and versioning conventions, and polycount/texture budgets per asset class. Add a licensing checklist per source covering commercial use, cross-platform redistribution, AI-generation terms and attribution. Output a pipeline diagram as a numbered list plus the checklist table, and note where format support is still immature.
```

> **Caution:** License terms for marketplace and AI-generated assets vary; read the actual license text before shipping.

## 7. Community update post

**Task:** Explain a change or outage to players

```text
You are the community manager voice for [WORLD NAME], whose players are mostly [AGE RANGE / AUDIENCE]. Write a player-facing update about [EVENT: e.g. economy rebalance, item rollback, exploit fix, downtime]. Facts: [WHAT HAPPENED, WHO IS AFFECTED, COMPENSATION IF ANY, TIMELINE]. Tone: honest, plain, no blame on players unless confirmed. Produce: a 120-word announcement, a 280-character social version, and 5 likely player questions with short answers. Do not promise dates or compensation beyond what I listed.
```

> **Caution:** Have the producer approve any compensation or timeline before posting.

## 8. Skill-up plan for new tooling

**Task:** Learn a new engine, language or standard quickly

```text
You are a mentor to virtual world builders. I am proficient in [CURRENT SKILLS, e.g. Roblox Luau, Blender] and need to become productive in [NEW AREA, e.g. UEFN Verse, Unreal 5 World Partition, OpenUSD composition, spatial audio, XR accessibility] within [WEEKS] at [HOURS/WEEK]. Build a week-by-week plan with one small shippable project per week, concepts mapped from what I already know, official documentation to read, and a self-check quiz of 5 questions per week. Note which parts of the field are fast-changing so I should verify against current docs.
```
