---
name: synthetic-performer-director
description: "Prompt playbook for a synthetic performer director. Use when a synthetic performer director wants help with work tasks such as: consent and scope checklist for a digital replica; performance direction notes for a synthetic take; character continuity bible; uncanny or artifact triage; explain AI performer use to cast and crew; audience disclosure and provenance plan; ethics and risk review for a posthumous or sensitive replica; upskilling plan for the role."
---

# Synthetic performer director prompts

Directs AI-generated and digitally replicated performers (digital doubles, de-aged actors, voice clones, fully synthetic characters) for film, games, ads and virtual production, working between VFX/ML teams, human performers, unions and legal. AI helps most with consent and union-compliance tracking, performance direction notes, continuity bibles, disclosure language and explaining technical limits to non-technical stakeholders.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Consent and scope checklist for a digital replica

**Task:** Check a planned replica use against the performer's consent and union terms before production

```text
You are a production compliance assistant for a synthetic performer director. We plan to use a digital replica of [PERFORMER NAME / ROLE] in [PROJECT TYPE: feature, series, game, ad] produced in [JURISDICTION]. Union status: [SAG-AFTRA TV/Theatrical, Interactive Media Agreement, Equity UK, non-union]. The signed consent says: [PASTE CONSENT/CONTRACT LANGUAGE]. Planned uses: [LIST SCENES, LINES, DIALOGUE CHANGES, LANGUAGES, MARKETING USES]. Produce a table: planned use | covered by consent (yes/no/unclear) | relevant rule (e.g. SAG-AFTRA 2023 digital replica provisions, California AB 2602, Tennessee ELVIS Act) | action needed. Then list questions for our attorney. Flag anything where you are unsure of the current rule text rather than guessing.
```

> **Caution:** Not legal advice; contract and right-of-publicity law is changing fast, so have entertainment counsel and the union rep confirm every 'covered' row.

## 2. Performance direction notes for a synthetic take

**Task:** Turn creative intent into precise, actionable notes for the ML/animation team

```text
Act as an experienced acting coach working alongside a synthetic performer director. Scene: [SCENE DESCRIPTION, CHARACTER, EMOTIONAL BEAT]. Current synthetic take problems as I see them: [e.g. eyes don't track partner, smile reads as polite not grief-stricken, breath doesn't match line delivery]. Pipeline: [e.g. performance capture driving a MetaHuman, neural face swap over a body double, voice clone + lip-sync]. Write director's notes in two layers: (1) the acting intent in plain performance language, (2) concrete, observable adjustments the team can execute (timing in frames, gaze targets, micro-expression onsets, breath placement). Keep to 10 notes max, prioritized, and say which notes are better solved by reshooting the human driver performance.
```

## 3. Character continuity bible

**Task:** Document a synthetic character so it stays consistent across shots, sequels and vendors

```text
Help me build a continuity bible for the synthetic character [CHARACTER NAME] in [PROJECT]. Inputs: [APPEARANCE NOTES, VOICE DESCRIPTION, BACKSTORY, APPROVED REFERENCE SHOTS/TAKES, KNOWN ARTIFACTS TO AVOID]. Output a structured document with sections: identity and boundaries (what the character never does or says), physical and facial behavior baselines, voice and prosody, movement signature, approved/forbidden lighting and angles that break the likeness, data lineage (which human performers or datasets it derives from and under what licenses: [FILL IN]), version log, and a QA checklist reviewers can tick per shot. Mark any section where my inputs are too thin.
```

> **Caution:** Record data lineage honestly; undocumented training sources are a legal and union risk.

## 4. Uncanny or artifact triage

**Task:** Diagnose why a synthetic shot looks wrong and route the fix

```text
You are a VFX supervisor helping triage a synthetic performer shot. Symptoms: [DESCRIBE, e.g. teeth flicker on plosives, skin looks waxy under backlight, identity drifts in profile, lip-sync lags 2-3 frames]. Pipeline and tools: [e.g. face-swap model, Unreal Engine MetaHuman, Wav2Lip-style sync, comp in Nuke]. Shot conditions: [LIGHTING, ANGLE, MOTION BLUR, RESOLUTION]. Give a ranked list of likely causes, a quick test to confirm each, and who owns the fix (capture, training data, model, comp, grade). Also tell me whether it's cheaper to fix in post, re-drive with a new human performance, or recut around it.
```

## 5. Explain AI performer use to cast and crew

**Task:** Draft a clear, honest briefing for human performers working alongside synthetic ones

```text
Draft a one-page briefing for the cast and crew of [PROJECT] explaining how synthetic performers will be used. Facts: [WHICH CHARACTERS ARE SYNTHETIC OR REPLICAS, WHO THEY DERIVE FROM, WHAT DATA IS CAPTURED FROM CAST (scans, voice, mocap), RETENTION AND DELETION TERMS, WHO TO ASK]. Tone: respectful, plain-English, no hype; acknowledge that people may have concerns about jobs and likeness. Include a short FAQ (what gets scanned, can it be reused, how am I paid, how do I withdraw or raise a concern) and leave [BRACKETS] wherever the answer depends on contract terms I haven't given you instead of inventing them.
```

> **Caution:** Have production legal and the union rep review before distribution; never imply terms that are not in signed contracts.

## 6. Audience disclosure and provenance plan

**Task:** Plan disclosure labels and content credentials for release

```text
I'm releasing [PROJECT] in [MARKETS, e.g. EU, US, UK] on [PLATFORMS]. It contains [DESCRIBE SYNTHETIC CONTENT: de-aging, fully synthetic character, voice clone of a deceased performer, AI dubbing]. Create a disclosure plan: where and how to disclose (credits, on-screen labels, marketing, metadata), whether to attach C2PA Content Credentials and at which pipeline stage, how EU AI Act Article 50 transparency obligations for deep fakes may apply (note artistic/fictional work carve-outs and that implementing guidance is still being finalized), and platform policies to check. Output a table by channel plus open questions. Flag clearly where obligations are uncertain.
```

> **Caution:** Regulatory timelines and guidance under the EU AI Act and US state laws are evolving; verify current text before release.

## 7. Ethics and risk review for a posthumous or sensitive replica

**Task:** Pressure-test a creative proposal before greenlight

```text
Act as a skeptical ethics reviewer. Proposal: [e.g. recreate deceased actor X for a cameo, have a synthetic version of a real public figure deliver new lines, create a child-likeness synthetic character]. Consent obtained: [ESTATE/PERFORMER/GUARDIAN CONSENT DETAILS]. Context of use: [STORY, TONE, MARKETING]. Assess risks across: consent quality and whether it covers this specific use, dignity and reputational harm, audience deception, misuse if assets leak, labor displacement, and jurisdictional law (e.g. post-mortem publicity rights, California AB 1836). Give a risk rating with reasons, mitigations, and the conditions under which you'd recommend we not proceed.
```

> **Caution:** The director and producers remain accountable for the decision; use this as a challenge, not a sign-off.

## 8. Upskilling plan for the role

**Task:** Build a learning plan covering craft, tech and law

```text
I'm a [CURRENT BACKGROUND, e.g. theater director, animation director, VFX artist] moving into synthetic performer direction. I have [HOURS/WEEK] for [MONTHS]. Build a learning plan in three tracks: (1) performance craft for digital characters (directing mocap and voice talent, reading micro-expression), (2) technology literacy (performance capture, MetaHuman/Unreal, neural rendering and face replacement, voice synthesis, their failure modes), (3) rights and ethics (SAG-AFTRA and Equity AI terms, right of publicity, EU AI Act transparency, C2PA). For each: milestones, a hands-on exercise, real resources to look up, and how to tell I've learned it. Mark resources you're unsure still exist.
```
