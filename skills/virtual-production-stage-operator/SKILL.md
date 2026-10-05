---
name: virtual-production-stage-operator
description: "Prompt playbook for a virtual production stage operator. Use when a virtual production stage operator wants help with work tasks such as: pre-shoot volume checklist; tearing and sync diagnosis; color pipeline sanity check; shot and stage log; explain a limitation to the director; volume booking feasibility plan; stage safety and rights review; upskilling study plan."
---

# Virtual production stage operator prompts

Runs the LED volume on an in-camera VFX (ICVFX) stage: Unreal Engine nDisplay render nodes, LED processors, camera tracking, genlock/timecode and color pipeline, so real-time backgrounds look right through the lens during the shoot. AI helps most with pre-shoot checklists, troubleshooting sync, tracking and color issues, shot logging, and turning technical problems into clear notes for directors, DPs and VFX vendors.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Pre-shoot volume checklist

**Task:** Build a day-of startup and verification checklist for the LED volume

```text
You are a senior ICVFX stage engineer. Write a pre-call startup and verification checklist for an LED volume with this setup: wall panels [PANEL MODEL], processors [e.g. Brompton Tessera / Megapixel Helios], [NUMBER] Unreal Engine [VERSION] nDisplay render nodes managed via Switchboard, camera tracking [e.g. Mo-Sys StarTracker / stYpe RedSpy / OptiTrack], camera [CAMERA MODEL] at [FRAME RATE] and shutter [ANGLE]. Order steps by dependency (power, genlock and timecode, processors, render nodes, tracking, lens calibration, color). For each step give the check, the expected result, and what to do if it fails. Output a numbered table that fits on two printed pages.
```

> **Caution:** Adapt to your stage's own SOPs and vendor documentation; electrical and rigging checks remain the responsibility of qualified crew.

## 2. Tearing and sync diagnosis

**Task:** Troubleshoot tearing, flicker or scan lines seen on camera

```text
Act as a virtual production systems engineer. On camera we see [SYMPTOM: tearing / rolling bands / flicker / scan lines] on [WHICH PART OF THE WALL], at [FRAME RATE], shutter [ANGLE], processor refresh/frame multiplier [VALUE], genlock source [SOURCE]. Render node frame times are [VALUES] and Switchboard/nDisplay logs show [PASTE RELEVANT LINES]. Give a ranked list of likely causes (e.g. genlock or sync policy mismatch, shutter vs LED refresh, render frame drops, cabling, processor settings), a fast isolation test for each that can be done between takes, and the fix. Mark which items you are inferring versus which the logs actually support.
```

> **Caution:** Don't change processor or sync settings mid-take without telling the DP and VP supervisor.

## 3. Color pipeline sanity check

**Task:** Diagnose color mismatch between wall, foreground and camera

```text
You are a color scientist on an LED volume. The DP reports [ISSUE: e.g. skin tones look green near the wall, background looks too saturated in camera, color shift at oblique angles]. Our pipeline: Unreal working space [e.g. ACEScg / sRGB], OpenColorIO config [VERSION/NAME], processor color target [e.g. P3 / Rec.2020, PQ or gamma], wall calibration last done [DATE], camera [MODEL] recording [LOG FORMAT/LUT]. Walk through where in this chain the error most likely enters, what to measure (with which tools, e.g. spectroradiometer, test charts) to confirm, and corrections ordered from least to most disruptive. Flag anything that should go back to the colorist or VFX vendor rather than be fixed on set.
```

> **Caution:** LED spectral limits can't be fully corrected in software; confirm changes with the DP on a monitor before shooting.

## 4. Shot and stage log

**Task:** Turn raw notes into a clean daily stage report

```text
You are the volume operator writing the daily stage report. From my raw notes below, produce: (1) a shot-by-shot table with slate/take, Unreal level and variant, camera/lens, tracking status, issues and timecode; (2) a downtime log with cause, duration and resolution; (3) open issues for tomorrow with owners; (4) a three-line summary for the producer. Keep technical terms accurate and don't invent details; mark anything missing as [UNKNOWN]. Raw notes: [PASTE NOTES, SWITCHBOARD/TRACKING LOG EXCERPTS, TIMECODES].
```

> **Caution:** Check timecodes and take numbers against the script supervisor's report before sending.

## 5. Explain a limitation to the director

**Task:** Communicate a technical constraint to creative stakeholders

```text
I'm the virtual production stage operator. The director wants [REQUEST: e.g. a very wide lens showing the floor seam, a fast whip pan, shooting at the wall at a steep angle]. The technical problem is [ISSUE: e.g. moiré, frustum lag from tracking latency of X ms, color shift off-axis, visible panel seams]. Write a short, non-jargony note (under 150 words) for the director and DP explaining what will happen on camera and why, then offer 2-3 practical alternatives (lens, blocking, set dressing, practical foreground, post fix) with the tradeoff for each. Respectful, solution-first tone.
```

## 6. Volume booking feasibility plan

**Task:** Plan stage setup and prep for an upcoming shoot

```text
You are a virtual production supervisor helping me plan. Upcoming shoot: [NUMBER] days, [NUMBER] scenes, environments [LIST, with whether they are Unreal-built, 2D/2.5D plates or photogrammetry], cameras [LIST], special needs [e.g. moving vehicle process shots, multi-camera, interactive lighting]. Our volume: [SIZE, PANEL PITCH, NUMBER OF RENDER NODES, TRACKING SYSTEM]. Produce: a prep timeline working back from day 1 (virtual art department handoff, optimization to hit frame rate, tech scout, lens calibration, color tests), a risk list with mitigation, and the questions I must answer with the VFX supervisor and DP before locking the schedule.
```

> **Caution:** Assumes typical prep durations; validate against your team's actual throughput.

## 7. Stage safety and rights review

**Task:** Check safety, labor and AI/likeness compliance before a shoot

```text
Act as a production compliance advisor for an LED volume stage in [COUNTRY/STATE]. Shoot details: [DESCRIPTION, incl. rigging of ceiling panels, crowd or performer count, any use of digital doubles, AI-generated backgrounds or scanned likenesses]. Produce a checklist covering: physical safety (rigging, electrical load, heat, trip hazards, LED brightness/flicker exposure for cast and crew, emergency egress); union and contract points (e.g. SAG-AFTRA digital replica and AI provisions, if a signatory); licensing of 3D assets, plates and scans; and data handling for scanned people. For each, say who owns sign-off. Flag where rules vary by jurisdiction or are still changing.
```

> **Caution:** Not legal advice; confirm with the production's safety officer, union reps and legal counsel.

## 8. Upskilling study plan

**Task:** Build a learning plan to move from operator to VP engineer

```text
I work as a [CURRENT ROLE, e.g. LED tech / Unreal artist / camera assistant] and want to become a lead virtual production stage engineer within [TIMEFRAME], with [HOURS] per week. I already know [SKILLS]. Build a week-by-week plan covering Unreal nDisplay and Switchboard, multi-user editing, Live Link and camera tracking, lens calibration, genlock/timecode and SMPTE ST 2110 basics, color management (ACES, OpenColorIO), LED processor configuration, and render performance profiling. For each block give hands-on exercises, free resources (e.g. Epic's Virtual Production Field Guide and Unreal Online Learning, SMPTE RIS on-set VP materials) and a check that I've learned it. Note which skills are likely to change as the tech evolves.
```

> **Caution:** Verify resource links and course availability; they change often.
