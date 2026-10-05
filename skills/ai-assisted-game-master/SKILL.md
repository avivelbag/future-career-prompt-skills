---
name: ai-assisted-game-master
description: "Prompt playbook for an AI-assisted game master. Use when an AI-assisted game master wants help with work tasks such as: session prep from campaign notes; nPC voice and memory sheet; rules adjudication check; session zero and safety tools; recap and between-session engagement; aI content and licensing audit; post-session table retro; upskilling plan for AI-era GMing."
---

# AI-assisted game master prompts

A professional or semi-professional game master who runs tabletop, virtual-tabletop or AI-driven narrative campaigns, today via platforms like StartPlaying, Roll20 and Foundry VTT, and later as the human director overseeing AI narrators, NPCs and generated content for paying groups, schools, therapy programs and corporate team events. AI helps most with session prep, consistent NPCs and lore, rules adjudication, recap writing and safety and content planning, while the human keeps control of pacing, player wellbeing and judgment at the table.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Session prep from campaign notes

**Task:** Turn messy campaign notes into a runnable session plan

```text
You are my co-prep assistant for a [SYSTEM, e.g. D&D 5e / Pathfinder 2e / Blades in the Dark] campaign. Here are my notes from last session and the players' open threads: [PASTE NOTES]. The party is [PARTY: names, classes, levels, personal goals]. Next session runs [LENGTH] on [VTT/IN PERSON]. Build a session plan with: 1) three strong starts, 2) 4-6 scenes as situations not scripts, each with a goal, an obstacle and a way it can fail forward, 3) secrets and clues not tied to a specific location, 4) one scene that hooks each player's personal goal, 5) a pacing cut list if we run short. Flag anything in my notes that contradicts earlier canon.
```

> **Caution:** Treat output as a menu; players' choices should override the plan.

## 2. NPC voice and memory sheet

**Task:** Keep recurring NPCs consistent across human and AI narration

```text
Act as a continuity editor for my campaign. Using this lore and session log [PASTE], write NPC sheets for [NPC NAMES]. For each: one-line concept, wants and fears, what they know and do NOT know (to prevent leaking secrets), relationships to each PC, speech patterns with three sample lines, and what has changed since we met them. Format as a compact table plus a short 'system prompt' block I could paste into an AI NPC tool such as [TOOL], with explicit instructions to stay within the NPC's knowledge and to hand back to the GM on [TRIGGERS, e.g. combat, player distress, rules disputes].
```

> **Caution:** Review AI NPC prompts for leaked plot secrets before giving players access.

## 3. Rules adjudication check

**Task:** Resolve a contested rules call quickly and fairly

```text
You are a rules reference for [SYSTEM AND EDITION]. At my table this happened: [SITUATION]. Player argued [POSITION A]; I ruled [POSITION B]. Explain the rules as written with the relevant book and section names (say clearly if you are unsure or if it depends on optional rules or errata), common rulings by experienced GMs, and the trade-offs of each for fun and fairness. End with a one-paragraph ruling I can read aloud and a house-rule note for our campaign document. Do not quote long passages of copyrighted rulebook text.
```

> **Caution:** AI can misremember rules; verify against the official book or SRD before treating as canon.

## 4. Session zero and safety tools

**Task:** Plan content boundaries and consent for a new group

```text
Help me run a session zero for a new [PAID / SCHOOL / CORPORATE / THERAPY-ADJACENT] group of [NUMBER] players, ages [AGES], playing [SYSTEM/GENRE with themes such as horror or political intrigue]. Draft: 1) a lines-and-veils questionnaire tailored to this genre, 2) how we will use safety tools such as the X-card, Script Change or the TTRPG Safety Toolkit (Shaw & Bryant-Monk), 3) how AI-generated narration, images or NPCs will be used and disclosed, and how players can opt out, 4) a short script for pausing play. Flag any extra considerations for minors or vulnerable players.
```

> **Caution:** Game play is not therapy; refer players in distress to qualified professionals.

## 5. Recap and between-session engagement

**Task:** Write session recaps and player-facing updates

```text
Write a recap of our last session for my players from these raw notes and chat log [PASTE]. Tone: [IN-WORLD CHRONICLE / CASUAL DISCORD POST]. Length: under [WORD COUNT]. Include: what happened in order, loot and XP awarded, unresolved hooks, and one teaser question per player for between-session play. Keep each player's spotlight roughly equal and do not reveal anything from my GM-only notes marked [SECRET]. Then give a three-bullet private summary for me: threads I am dropping, players who got little spotlight, and continuity errors.
```

> **Caution:** Strip real names or personal info from logs before sharing outside the group.

## 6. AI content and licensing audit

**Task:** Check that published adventure material is legally and ethically clear

```text
I plan to sell or publish [PRODUCT: adventure, AI-assisted campaign service, actual-play stream] on [PLATFORM, e.g. DriveThruRPG, DMs Guild, StartPlaying, Twitch]. It uses [SOURCE MATERIAL: SRD 5.1 under CC-BY-4.0 / ORC License / original IP] and AI-generated [TEXT/ART/VOICES] from [TOOLS]. Produce a checklist covering: license attribution and what content each license permits, the platform's current AI-content disclosure rules, AI tool terms of service, voice and likeness consent, and transparency duties such as EU AI Act Article 50 if I serve EU users. Mark items that are legally unsettled and questions I should take to a lawyer.
```

> **Caution:** Not legal advice; platform AI policies change often, so check them at publication time.

## 7. Post-session table retro

**Task:** Diagnose why a session fell flat or went wrong

```text
Act as an experienced GM coach. Last session had these problems: [DESCRIBE: e.g. one player dominated, combat dragged, AI narrator contradicted canon, a player seemed upset]. Context: [GROUP, SYSTEM, FORMAT, how AI tools were used]. Give me: likely root causes ranked by probability, which were caused or worsened by the AI tooling versus GM technique, specific fixes for next session, a short non-defensive message I could send the group to ask for feedback, and signs that a problem needs a private conversation rather than a table fix.
```

> **Caution:** Ask players directly; don't diagnose individuals from AI guesses alone.

## 8. Upskilling plan for AI-era GMing

**Task:** Build a learning plan to run AI-augmented games professionally

```text
I run [CURRENT LEVEL: e.g. home games / 2 paid tables a week] and want to become a professional AI-assisted game master within [TIMEFRAME], serving [MARKET: online paid games, schools, corporate team-building, accessibility-focused play]. Create a 12-week plan covering: GM craft (e.g. Lazy DM, Angry GM, Apocalypse World principles), VTT automation in Foundry or Roll20, prompt design for AI NPCs and narration, safety and facilitation, pricing and business basics, and building a portfolio. Include weekly practice tasks, a measurable outcome per month, and an honest note on which parts of this market are established today versus speculative.
```

> **Caution:** Income claims for professional GMing vary widely; validate with working GMs.
