---
name: neural-implant-rehabilitation-therapist
description: "Prompt playbook for a neural implant rehabilitation therapist. Use when a neural implant rehabilitation therapist wants help with work tasks such as: calibration session plan; performance drop troubleshooting; trial session note; caregiver home-use guide; goal and outcome-measure plan; informed-consent and expectations talk; neural data privacy check; upskilling study plan."
---

# Neural implant rehabilitation therapist prompts

An occupational, physical or speech therapist who trains people with paralysis, ALS, stroke or spinal cord injury to use implanted brain-computer interfaces and neurostimulators (today's analogues: BrainGate, Neuralink PRIME, Synchron COMMAND, Blackrock, Onward ARC trials), from decoder calibration sessions to home use and outcome reporting. AI helps most with session planning, analyzing performance logs, trial-grade documentation, plain-language patient and caregiver materials, and keeping up with fast-moving device, regulatory and neural-data-privacy rules.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Calibration session plan

**Task:** Plan a structured BCI decoder calibration and training session for a specific participant

```text
You are an experienced occupational therapist on an implanted BCI team. Plan a [SESSION LENGTH]-minute training session for a participant with [DIAGNOSIS, e.g. C4 SCI / ALS, ALSFRS-R score] using [DEVICE/DECODER TYPE, e.g. intracortical cursor decoder]. Current status: [RECENT PERFORMANCE, e.g. bits/sec, Fitts' law throughput, typing WPM], fatigue pattern [DETAILS], participant goal [GOAL, e.g. independent texting]. Output a table: block, task (e.g. center-out, grid task, copy-typing), duration, rest, success criterion, and what to change if performance drops. Add fatigue and frustration stop rules, and note which steps need the engineer present. Stay within the study protocol [PROTOCOL CONSTRAINTS].
```

> **Caution:** Session content must stay within the approved IDE/IRB protocol; the study team, not the AI, decides parameter changes.

## 2. Performance drop troubleshooting

**Task:** Work through likely causes when a participant's BCI control degrades

```text
Act as a BCI clinical-research therapist reviewing a performance decline. Over [TIME PERIOD], [PARTICIPANT ID] went from [BASELINE METRICS] to [CURRENT METRICS]. Context: days since recalibration [N], sleep/meds/mood changes [NOTES], illness or spasticity [NOTES], setup changes (seating, screen distance, environment) [NOTES], engineer notes on signal quality/channel counts [NOTES]. Produce a ranked differential split into (a) participant/clinical factors, (b) setup and task factors, (c) signal/decoder factors to escalate to engineering. For each, give the quick check I can do in-session and what result would rule it in or out. Flag anything suggesting a medical issue (e.g. infection, seizure activity, neurological change) for immediate physician review.
```

> **Caution:** Hardware, signal or neurological concerns go to the engineer and study physician; do not adjust implant settings yourself.

## 3. Trial session note

**Task:** Turn raw session notes into a structured research/clinical note

```text
You are a documentation assistant for a neural implant rehab study. Convert my raw notes into a session note with headings: Participant ID (de-identified), Date/Session #, Tasks performed, Quantitative results [METRICS], Standardized measures administered (e.g. ARAT, GRASSP, COPM, QUEST) with scores, Participant-reported fatigue/comfort/satisfaction, Adverse events or device issues (stating 'none reported' only if my notes say so), Deviations from protocol, Plan for next session. Keep facts exactly as given; mark missing items as [MISSING] rather than guessing. Raw notes: [PASTE DE-IDENTIFIED NOTES].
```

> **Caution:** Paste only de-identified data unless your organization has approved the tool for PHI; any adverse event must also go through the formal AE reporting process.

## 4. Caregiver home-use guide

**Task:** Write a plain-language guide for family/caregivers supporting home BCI use

```text
Write a plain-language home guide (reading level about grade 6) for caregivers of [PARTICIPANT FIRST NAME OR 'the user'], who uses [DEVICE] at home for [USES, e.g. texting, computer access, wheelchair control]. Base it only on these approved instructions: [PASTE MANUFACTURER/STUDY INSTRUCTIONS]. Sections: daily setup checklist, positioning and charging, signs of tiredness and when to stop, skin/incision or headpiece checks to report, what to do if the system stops working, who to call and when (with [CONTACT NUMBERS]), and respecting the user's privacy and choice to switch it off. Use short bullets and add a one-page quick-reference version.
```

> **Caution:** Must be checked against the device IFU/study materials and approved by the study team before distribution.

## 5. Goal and outcome-measure plan

**Task:** Map a participant's functional goals to measurable outcomes over a training block

```text
Act as a rehabilitation outcomes specialist. My participant has [DIAGNOSIS, LEVEL, TIME SINCE INJURY] and an implant for [FUNCTION, e.g. computer control / spinal stimulation for hand function]. Their priorities (from COPM interview): [GOALS]. Propose a [N]-week plan: for each goal, a SMART objective, the standardized measure that fits (e.g. COPM, GRASSP, ARAT, SCIM III, QUEST, task-specific metrics like WPM), measurement schedule, and a minimal clinically important difference where one is published (say if none exists for this population). Note which outcomes reflect device performance versus real-life participation, and suggest how to capture the participant's own view of benefit.
```

> **Caution:** Verify MCID values and measure validity in the source literature before relying on them.

## 6. Informed-consent and expectations talk

**Task:** Prepare to discuss realistic expectations and risks with a prospective participant

```text
Help me prepare for a conversation with a prospective participant with [CONDITION] considering enrolling in [TRIAL NAME/DEVICE] study. Using only this approved consent summary [PASTE KEY POINTS: procedures, risks, time commitment, explant plan, end-of-study device support], draft: (1) a plain-language talking-points outline, (2) honest answers to likely questions such as 'Will this let me walk/move again?', 'What happens to my data?', 'What if the company stops supporting the device?', and 'Can I withdraw?', (3) signs the person may not understand or may feel pressured, and how to slow down. Avoid overstating benefit; flag any question I should refer to the PI or surgeon.
```

> **Caution:** Formal consent is obtained by authorized study staff using the IRB-approved form; these are preparation notes only.

## 7. Neural data privacy check

**Task:** Review a planned data use against privacy rules for neural data

```text
Act as a privacy-aware clinical research advisor. We want to [PLANNED USE, e.g. share session videos and decoded text logs with a university partner / use a home telemetry app]. Jurisdiction: [STATE/COUNTRY]. Data involved: [DATA TYPES]. Summarize which frameworks likely apply (e.g. HIPAA, Common Rule/IRB consent terms, GDPR special-category data, state neural-data laws such as Colorado's and California's 2024 amendments, Chile's neurorights provisions) and what each would require here. Then list concrete questions for our privacy officer/IRB, risks of re-identification from neural or decoded-speech data, and safeguards. Clearly flag where the law is new, unsettled, or I need legal confirmation.
```

> **Caution:** Not legal advice; confirm with your privacy officer, IRB and counsel.

## 8. Upskilling study plan

**Task:** Build a learning plan to move from conventional rehab into neural implant work

```text
I am a [OT/PT/SLP] with [YEARS] years in [SETTING, e.g. SCI inpatient rehab] and want to work on implanted BCI and neuromodulation teams. Create a 12-week self-study plan covering: basic neurophysiology of motor/speech cortex recording, how intracortical, endovascular (Stentrode) and ECoG approaches differ, decoder calibration concepts, performance metrics (bits/sec, Fitts' law), spinal cord stimulation rehab (e.g. ARC therapy evidence), the FDA's 2021 implanted BCI guidance, IDE/GCP (ISO 14155) basics, and neuroethics. For each week give objectives, 2-3 key sources (landmark papers, guidance documents, BCI Society resources) and a practical exercise. Mark sources I should verify are current.
```

> **Caution:** Check citations exist and are up to date; the field changes quickly.
