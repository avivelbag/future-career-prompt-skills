---
name: haptic-experience-designer
description: "Prompt playbook for a haptic experience designer. Use when a haptic experience designer wants help with work tasks such as: haptic effect spec from design intent; cross-device fallback plan; playtest feedback synthesis; haptic latency troubleshooting; accessibility and comfort review; haptic design system documentation; stakeholder pitch for haptics investment; upskilling plan in haptic science and tools."
---

# Haptic experience designer prompts

Designs touch and vibration feedback for phones, game controllers, XR gloves and vests, car interfaces and medical or accessibility devices, using tools like Apple Core Haptics, Meta Haptics Studio and Interhaptics, and increasingly the MPEG haptics coding standard (ISO/IEC 23090-31). AI helps most with turning design intent into effect specs and parameters, analysing playtest feedback, writing cross-platform design docs, and checking accessibility, comfort and vibration-exposure risks.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Haptic effect spec from design intent

**Task:** Turn an emotional or functional goal into concrete, implementable haptic parameters

```text
You are a senior haptic designer. I need an effect for [MOMENT, e.g. 'charging a bow shot' / 'payment confirmed'] on [DEVICE AND ACTUATOR, e.g. iPhone Taptic Engine / DualSense voice-coil / LRA in a wearable]. The intended feeling is [INTENT]; it lasts about [DURATION] and plays alongside [AUDIO/VISUAL CUES]. Propose 3 distinct design options. For each, give a table of time-ordered events with intensity, sharpness or frequency, envelope (attack/decay), and duration. Explain how it aligns with the audio, and the risk of it feeling like 'buzz' instead of texture. Then say which parameters this actuator can and can't reproduce. Format the best option so it maps directly to [FORMAT, e.g. Core Haptics AHAP / Android VibrationEffect.Composition / Interhaptics .haps].
```

> **Caution:** Parameter values are starting points; tune them on the real hardware, since actuator response varies by unit and enclosure.

## 2. Cross-device fallback plan

**Task:** Adapt one haptic design to devices with very different actuators

```text
Act as a haptics platform engineer. Our signature effect [DESCRIBE EFFECT OR PASTE PARAMETERS] was authored for [HIGH-END DEVICE]. It must also ship on [LIST OF TARGETS, e.g. low-cost Android ERM phones, Quest controllers, PC gamepads with rumble motors]. For each target, describe what the actuator type (ERM, LRA, voice-coil, piezo) can render. Then give the degraded version of the effect and what is lost, and propose a test to confirm that the meaning survives. Note where MPEG haptics (ISO/IEC 23090-31) or engine plugins such as Interhaptics or Meta Haptics SDK could handle adaptation, and flag anything you're unsure is supported today. Output a table, then a prioritised list of risks.
```

> **Caution:** Check SDK and platform support against current documentation; haptics APIs change frequently.

## 3. Playtest feedback synthesis

**Task:** Analyse user study notes and ratings to find what to fix

```text
You are a UX researcher specialising in haptics. Below are notes and ratings from [N] participants testing [PRODUCT/FEATURE] on [DEVICE]: [PASTE ANONYMISED DATA: quotes, Likert scores, task outcomes, settings used]. Group the findings into themes such as perceived intensity, timing/latency, fatigue, annoyance, missed cues, and accessibility. For each theme, give its frequency, representative quotes, the likely cause (design, actuator, latency or context like holding position), and a suggested change. Separate solid findings from ones based on 1-2 people. End with 3 follow-up experiments, e.g. a JND or A/B test, with sample size and measurement method.
```

> **Caution:** Remove names and identifying details before pasting; small samples don't support statistical claims.

## 4. Haptic latency troubleshooting

**Task:** Diagnose why effects feel late, mushy or out of sync

```text
Act as a haptics systems engineer. Users report that [SYMPTOM, e.g. 'impacts feel late', 'buzzy tail after hits', 'effects drop during heavy scenes'] on [PLATFORM/ENGINE, e.g. Unity on Quest 3, Unreal on PC with DualSense, native iOS]. Our pipeline: [DESCRIBE: trigger source, middleware, transport e.g. Bluetooth/USB, actuator, buffer sizes]. Measured or estimated numbers: [ANY TIMINGS]. Give a ranked list of likely causes with the reasoning for each, including thread scheduling, Bluetooth latency, audio-to-haptic conversion, actuator rise and ring-down time, and missing active braking. For each cause, give a concrete test to confirm or rule it out, e.g. a high-speed camera or accelerometer with a photodiode. Note the perceptual synchrony thresholds that matter here, and say where published values vary.
```

> **Caution:** Confirm causes with measurements on the real device before changing the shipping code.

## 5. Accessibility and comfort review

**Task:** Check a haptic design against accessibility guidance and exposure limits

```text
You are an accessibility and ergonomics reviewer for haptic interfaces. Review this design: [DESCRIBE EFFECTS, intensities, durations, how often per minute, body site, session length, target users incl. any with disabilities]. Check it against the ergonomic guidance in ISO 9241-910/920 on tactile and haptic interaction, and against WCAG 2.2 principles: no information conveyed by touch alone, and user control over intensity or off. Consider cumulative vibration exposure where relevant (ISO 5349 hand-arm concepts) and impacts on sensitive groups like people with neuropathy, sensory processing differences, implants or pregnancy. Output: a table of issue, why it matters, severity and fix, then the required user settings, then open questions for a qualified ergonomist or clinician.
```

> **Caution:** Not a safety certification; consumer haptics rarely reaches ISO 5349 action levels, but medical or wearable products need expert sign-off.

## 6. Haptic design system documentation

**Task:** Write a haptic language guide for engineers and other designers

```text
Act as a design-systems writer. Draft a haptic language guide for [PRODUCT/BRAND]. The effects we have are [LIST: name, purpose, parameters or file refs]. The platforms are [LIST]. The principles we follow are [e.g. 'haptics confirm, never surprise', 'pair with sound']. Structure: purpose and principles; effect taxonomy (notification, confirmation, error, texture, impact, ambient) with when to use and when not to; a parameter table for each effect and platform; rules for combining effects and limits on how often they repeat; required user settings and accessibility requirements; an implementation checklist for engineers; and a template for proposing new effects. Keep it concise. Mark any area where our current set has gaps or conflicts as [DECISION NEEDED].
```

## 7. Stakeholder pitch for haptics investment

**Task:** Make the case for haptics to a product or business audience

```text
You are a product strategist who knows haptics. Help me write a one-page brief for [AUDIENCE, e.g. VP Product, automotive HMI lead, game director]. I want to propose [INVESTMENT, e.g. moving from rumble to voice-coil actuators / adding haptics to our XR training app]. Context: [PRODUCT, USERS, BUDGET, TIMELINE, CURRENT PAIN POINTS]. Include the user value with evidence, citing only published studies or well-known shipped examples like DualSense or Apple's Taptic Engine, and marking anything you're unsure of. Also cover BOM and power or battery cost questions, integration effort, and IP and licensing risk: haptics has an active patent landscape, e.g. Immersion, so recommend legal review. End with a small pilot and its success metrics. Use plain language and no hype.
```

> **Caution:** Don't present unverified effect sizes as fact; have counsel review any patent or licensing statements.

## 8. Upskilling plan in haptic science and tools

**Task:** Build a structured learning path for the field's technical and perceptual foundations

```text
Act as a mentor in haptics. My background is [e.g. sound design / UX / mechanical engineering] and I want to become a strong haptic experience designer for [DOMAIN: games, XR, automotive, medical, mobile] within [TIMEFRAME] at [HOURS/WEEK]. Build a week-by-week plan covering tactile perception (mechanoreceptors, JNDs, spatial and temporal resolution), actuator physics (ERM, LRA, voice-coil, piezo, ultrasonic mid-air), and authoring tools (Core Haptics, Meta Haptics Studio, Interhaptics, bHaptics). Also cover emerging standards: MPEG haptics ISO/IEC 23090-31 and IEEE 1918.1 Tactile Internet. Include a hands-on project each phase, e.g. an Arduino or audio-amp voice-coil rig. Name foundational sources only if you're confident they exist, and tell me which ones to verify.
```

> **Caution:** Check that any cited books, courses and papers exist and are current before relying on them.
