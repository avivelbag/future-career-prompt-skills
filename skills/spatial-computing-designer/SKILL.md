---
name: spatial-computing-designer
description: "Prompt playbook for a spatial computing designer. Use when a spatial computing designer wants help with work tasks such as: flat-to-spatial adaptation spec; comfort and motion-sickness review; spatial accessibility audit; sensor and gaze data privacy review; usability test plan for a headset prototype; design rationale for engineers and stakeholders; 3D asset and performance budget planning; upskilling plan from 2D to spatial."
---

# Spatial computing designer prompts

Designs apps, interfaces and experiences for headsets and AR glasses (Apple Vision Pro, Meta Quest, Android XR, OpenXR/WebXR devices), working out where content sits in 3D space, how people point, look, pinch and speak, and how to keep them comfortable, safe and private. AI helps most with turning flat UI into spatial specs, critiquing comfort and accessibility, writing design docs and usability-test plans, and keeping up with fast-changing platform guidelines.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Flat-to-spatial adaptation spec

**Task:** Turn an existing 2D app screen into a spatial layout proposal

```text
You are a senior spatial computing designer. I'm adapting [APP NAME]'s [SCREEN/FEATURE] from [iOS/Android/web] to [visionOS / Meta Horizon OS / Android XR]. Current screen: [DESCRIBE OR PASTE COMPONENTS AND USER FLOW]. Users are [WHO] in [SETTING: seated at desk, standing, walking]. Propose a spatial layout: which elements stay in a window, which become volumes or ornaments, and what (if anything) earns a full or immersive space. For each element, give placement (distance from user in metres, angle from eye line), size, and input method (gaze+pinch, direct touch, controller, voice). Output a table plus a short rationale, and cite the relevant platform guideline section (e.g. Apple HIG for visionOS) where you rely on one. Flag anything that is guesswork rather than documented guidance.
```

> **Caution:** Platform guidelines change with each OS release; check numbers against the current HIG or vendor docs and test on device.

## 2. Comfort and motion-sickness review

**Task:** Critique an experience for visual fatigue, cybersickness and ergonomics

```text
Act as an XR comfort reviewer. Review this experience for [DEVICE]: [DESCRIBE SCENES, CAMERA/LOCOMOTION, MOVING CONTENT, TEXT SIZES, SESSION LENGTH, POSTURE]. Assess risks from vection and artificial locomotion, vergence-accommodation conflict from content placed too close, head-locked content, sustained arm-raised interaction ('gorilla arm'), flicker or high-contrast motion, and neck strain from content placed high or low. Reference established guidance where it exists (vendor comfort guidelines, ISO 9241-392 on stereoscopic visual fatigue). Output: a ranked risk table (issue, where it occurs, severity, who is most affected, fix), then three changes with the biggest comfort payoff. Say which findings need confirmation through user testing.
```

> **Caution:** This is a desk review, not a substitute for testing with real users, including people prone to motion sickness. Include a photosensitivity check if anything flashes.

## 3. Spatial accessibility audit

**Task:** Check a spatial design against accessibility requirements

```text
You are an accessibility specialist for XR. Audit this spatial design: [DESCRIBE UI, INTERACTIONS, AUDIO CUES, TEXT, TIME LIMITS]. Target platform: [PLATFORM]. Check it against the W3C XR Accessibility User Requirements (XAUR), the WCAG 2.2 criteria that carry over, and the platform's built-in features (e.g. visionOS Pointer Control, Dwell Control, VoiceOver; Quest accessibility settings). Cover: one-handed and seated use, users who cannot use eye tracking, low vision, deaf/hard-of-hearing (captions placed in space), cognitive load, and limited mobility. Output a checklist table: requirement, pass/fail/unclear, evidence, fix. End by listing where XR accessibility standards are still unsettled and what I should test with disabled users directly.
```

> **Caution:** WCAG was written for 2D; XR conformance is not formally defined yet. Test with disabled users rather than relying on a checklist alone.

## 4. Sensor and gaze data privacy review

**Task:** Assess privacy risks of eye, hand, room and face data in a feature

```text
Act as a privacy-minded design reviewer. My feature [DESCRIBE FEATURE] on [PLATFORM] uses or could use [eye tracking / hand skeleton / room mesh / camera passthrough / face or persona data / spatial anchors / bystander capture]. Our users are in [JURISDICTIONS]. Explain what data the platform actually exposes to apps (e.g. visionOS doesn't give apps raw gaze), what we would collect or infer, and how it could reveal sensitive information (health, identity, home layout, attention). Map risks to GDPR, CCPA/CPRA, Illinois BIPA and any other law I name, marking where legal treatment of XR data is unsettled. Output: a data-flow table, a risk list, and design mitigations (on-device processing, minimisation, clear consent moments, bystander indicators).
```

> **Caution:** This is design input, not legal advice. Have privacy counsel review anything involving biometric or bystander data.

## 5. Usability test plan for a headset prototype

**Task:** Plan a moderated in-headset usability study

```text
You are a UX researcher for spatial computing. Draft a moderated usability test plan for [PROTOTYPE] on [DEVICE], built in [Reality Composer Pro / Unity / Unreal / ShapesXR / Bezel / WebXR]. Goals: [RESEARCH QUESTIONS]. Participants: [NUMBER, PROFILE, incl. glasses wearers, first-time headset users]. Include: screener, consent covering recording and sensor data, hygiene and fit procedure, session timeline capped at [MINUTES] in-headset with breaks, tasks with success criteria, how to observe what the participant sees (casting/mirroring), metrics (task success, errors, SUS, Simulator Sickness Questionnaire), stop rules if someone feels unwell, and a debrief script. Format as a document with headings and a one-page moderator cheat sheet.
```

> **Caution:** Screen out or take extra care with participants who have epilepsy, are pregnant or have balance disorders, following the device maker's health and safety warnings.

## 6. Design rationale for engineers and stakeholders

**Task:** Write a design decision record explaining a spatial interaction choice

```text
Help me write a design decision record for [PRODUCT]. The decision: [E.G. use a volume rather than a window for the 3D product viewer / use direct touch rather than gaze+pinch for the control panel]. Alternatives we considered: [LIST]. Evidence: [TEST FINDINGS, PERFORMANCE LIMITS, PLATFORM GUIDANCE]. Audience: [ENGINEERS / PRODUCT MANAGER / EXECUTIVES]. Structure: context, decision, options compared in a table (comfort, discoverability, accessibility, engineering cost, frame-rate/thermal impact, cross-platform portability via OpenXR or Unity PolySpatial), consequences, open questions, and what would make us revisit this. Keep it under [WORD LIMIT] words and in plain language, without XR jargon the audience won't know.
```

## 7. 3D asset and performance budget planning

**Task:** Set asset, polygon and texture budgets for a spatial scene

```text
Act as a technical artist working alongside a spatial designer. I'm planning [SCENE/EXPERIENCE] for [DEVICE(S)] using [RealityKit / Unity / Unreal / WebXR with three.js]. Content: [LIST OBJECTS, ANIMATIONS, LIGHTING, PASSTHROUGH OR FULLY IMMERSIVE]. Propose a performance budget: target frame rate, draw calls, triangle counts, texture resolution and compression, material and shader limits, and dynamic light count. Recommend asset formats (USDZ/OpenUSD, glTF) and pipeline steps (LOD, baking, mesh optimisation). Output a budget table and a checklist for artists. Clearly separate vendor-published figures from your own rule-of-thumb estimates, and tell me how to measure the real numbers with the platform's profiler (e.g. Xcode RealityKit Trace, Meta OVR Metrics Tool, Unity Profiler).
```

> **Caution:** Rule-of-thumb budgets vary a lot by device and OS version; treat them as starting points and profile on hardware.

## 8. Upskilling plan from 2D to spatial

**Task:** Build a personal learning plan for moving into spatial design

```text
I'm a [CURRENT ROLE, e.g. product designer with Figma, no 3D experience] moving into spatial computing design for [TARGET PLATFORM/INDUSTRY]. I have [HOURS PER WEEK] for [WEEKS]. Build a learning plan covering: spatial UX fundamentals (depth, scale, ergonomics, input models), platform guidelines (Apple HIG for visionOS, Meta Horizon OS design docs, Android XR), a prototyping tool path (e.g. ShapesXR or Bezel, then Reality Composer Pro or Unity), 3D basics (Blender, USD/glTF), accessibility and comfort, and the basics of OpenXR/WebXR so I can talk to engineers. Each week: goals, free or official resources (only ones you are confident exist), a small portfolio exercise, and how to check I've learned it. End with three portfolio projects that would convince a hiring manager.
```

> **Caution:** Check that linked courses and docs are still current. Tools in this field change fast.
