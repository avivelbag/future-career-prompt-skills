---
name: brain-computer-interface-technician
description: "Prompt playbook for a brain-computer interface technician. Use when a brain-computer interface technician wants help with work tasks such as: signal-quality session triage; decoder recalibration plan; adverse event and deviation write-up; participant and caregiver guide; neural data privacy check; hardware fault troubleshooting tree; expectation-setting conversation prep; upskilling study plan."
---

# Brain-computer interface technician prompts

BCI technicians support people living with implanted or wearable brain-computer interfaces (today mostly in FDA IDE trials run by Neuralink, Synchron, Blackrock Neurotech, Paradromics and Precision Neuroscience, plus academic labs like BrainGate). They run calibration sessions, monitor signal quality, troubleshoot hardware and software, train users and caregivers, and keep trial-grade records. AI helps most with structuring signal-quality triage, drafting protocol-compliant documentation, plain-language user training material, and learning the neuroscience, decoding and regulatory background, while clinicians and investigators keep medical and safety decisions.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Signal-quality session triage

**Task:** Interpret a session's signal metrics and decide what to check first

```text
You are assisting a BCI technician supporting a participant with a [DEVICE TYPE, e.g. intracortical Utah array / endovascular stentrode / ECoG] system. Here are today's session metrics compared with the baseline: [CHANNEL COUNT WITH USABLE UNITS OR SPIKE BAND POWER, IMPEDANCE VALUES, NOISE FLOOR, 60/50 Hz LINE NOISE, DROPPED PACKETS, DECODER PERFORMANCE e.g. bits per second or cursor success rate]. Environment notes: [LOCATION, NEARBY ELECTRONICS, PARTICIPANT STATE]. Produce: (1) a table of the anomalies ranked by likely impact, (2) for each, plausible causes split into environmental, external hardware, software/decoder drift, and possible implant or physiological change, (3) a step-by-step non-invasive check order I can do myself, and (4) which findings must be escalated to the study engineer or clinical investigator today. Say clearly where the data is insufficient to tell causes apart.
```

> **Caution:** Possible implant, tissue or neurological changes go to the clinical team; the technician does not diagnose.

## 2. Decoder recalibration plan

**Task:** Plan a recalibration session after performance drift

```text
Act as an experienced BCI research engineer. A participant's [DECODER TYPE, e.g. Kalman filter / RNN cursor or speech decoder] has dropped from [BASELINE PERFORMANCE] to [CURRENT PERFORMANCE] over [TIME PERIOD]. Constraints: session length [MINUTES], participant fatigue notes [NOTES], protocol limits [PROTOCOL RULES ON SESSION DURATION / TASKS]. Draft a recalibration session plan: warm-up, open-loop and closed-loop calibration blocks, number of trials per block, rest breaks, stopping criteria tied to fatigue or discomfort, metrics to record, and how to decide whether to keep or roll back the new decoder. Present it as a timed checklist. Note which steps depend on our specific software stack, and flag anything that would require protocol amendment or investigator approval.
```

> **Caution:** Follow the approved study protocol; participant comfort and consent to continue override performance targets.

## 3. Adverse event and deviation write-up

**Task:** Draft a factual incident note for the sponsor and IRB

```text
You are helping a BCI technician document an event during an investigational device study under an FDA IDE (21 CFR 812). Raw notes: [TIMELINE, WHAT WAS OBSERVED, PARTICIPANT REPORTS, DEVICE LOGS, ACTIONS TAKEN, WHO WAS NOTIFIED]. Draft a neutral, factual event report with sections: summary, chronology with timestamps, device and software versions, participant status, immediate actions, notifications made, and open questions. Do not assign causality or severity; leave clearly marked fields for the investigator to classify (adverse event vs. device malfunction vs. protocol deviation, seriousness, relatedness, and whether it may be an unanticipated adverse device effect). List any facts missing from my notes that a reviewer will ask for.
```

> **Caution:** Remove direct identifiers before pasting; causality and reporting decisions belong to the investigator and sponsor.

## 4. Participant and caregiver guide

**Task:** Turn technical setup steps into plain-language home-use instructions

```text
Write a home-use guide for a person with [CONDITION, e.g. ALS / high cervical spinal cord injury] using a [DEVICE TYPE] BCI, and for their caregiver [CAREGIVER CONTEXT]. Source steps from our technical procedure: [PASTE STEPS FOR CHARGING, HEADPIECE OR RECEIVER PLACEMENT, STARTING THE SOFTWARE, CALIBRATION, SHUTDOWN]. Requirements: 6th-8th grade reading level, one action per step, a short 'If this happens' troubleshooting table, a 'Stop and call us' section listing [SYMPTOMS AND DEVICE ALERTS FROM PROTOCOL] with our contact [CONTACT], and notes on accessibility (the user may operate it via eye-gaze or the BCI itself). Flag any step where my source text is ambiguous rather than guessing.
```

> **Caution:** Medical warning content must come from the approved protocol and labeling; have the clinical team review before use.

## 5. Neural data privacy check

**Task:** Review a data-handling workflow for neural data privacy risks

```text
Act as a privacy and compliance reviewer for a BCI program. Our data flow: [DESCRIBE COLLECTION, ON-DEVICE PROCESSING, UPLOAD, CLOUD STORAGE, ANALYSTS AND THIRD PARTIES WITH ACCESS, RETENTION]. Jurisdictions: [STATES / COUNTRIES]. Identify risks and gaps against HIPAA, the consent form language [PASTE RELEVANT CONSENT TEXT], state neural-data laws such as Colorado's and California's amendments treating neural data as sensitive, GDPR if applicable, and FDA premarket cybersecurity expectations. Output a table: data element, risk, relevant rule, suggested mitigation, owner. Explicitly mark where neural-data law is new or untested and where I need counsel or the privacy officer to decide.
```

> **Caution:** This is a checklist aid, not legal advice; confirm current law with the privacy officer or counsel.

## 6. Hardware fault troubleshooting tree

**Task:** Build a fault tree for recurring external-hardware failures

```text
You are a medical-device field service engineer. Our BCI system's external components are [LIST, e.g. transcutaneous pedestal connector, headstage, wireless receiver, charging coil, tablet app]. Recurring complaints over [PERIOD]: [SYMPTOMS AND FREQUENCY]. Build a troubleshooting decision tree limited to external, user-serviceable parts, using the manufacturer's service steps I paste here [SERVICE MANUAL EXCERPTS]. For each branch give: the check, expected result, next step, and when to stop and escalate. Then suggest which data to log so we can spot patterns (e.g. by component lot, firmware version, environment) and feed a CAPA under ISO 13485. Note where you're inferring beyond the manual.
```

> **Caution:** Never open, modify or service implanted components or anything outside the manufacturer's documented procedures.

## 7. Expectation-setting conversation prep

**Task:** Prepare for a hard conversation about what the BCI can and cannot do

```text
I'm a BCI technician preparing for a conversation with [PARTICIPANT / FAMILY MEMBER] who expects [THEIR EXPECTATION, e.g. walking again, faster typing, permanent device use]. The facts: [CURRENT PERFORMANCE, STUDY DURATION, WHAT HAPPENS AT STUDY END PER PROTOCOL, KNOWN LIMITATIONS]. Help me prepare: key messages in plain, honest language; likely questions and accurate answers; phrases to avoid that overpromise or sound dismissive; which topics I should hand off to the investigator or study coordinator (prognosis, explant, post-trial access); and how to acknowledge frustration. Format as a one-page briefing.
```

> **Caution:** Do not make medical or post-trial access commitments; route those to the investigator.

## 8. Upskilling study plan

**Task:** Build a learning plan for neuroscience, decoding and device regulation

```text
Act as a mentor for someone moving into BCI technician work from [BACKGROUND, e.g. EEG tech, biomedical engineering, clinical research coordinator]. In [HOURS PER WEEK] over [MONTHS], I need to get competent in: neural signal basics (spikes, local field potentials, ECoG), common decoders, signal processing in Python (e.g. MNE, NumPy/SciPy), electrical safety and implant standards (IEC 60601-1, ISO 14708-3, ISO 14971), Good Clinical Practice (ICH E6), 21 CFR 812, and FDA's 2021 guidance on implanted BCI devices. Produce a week-by-week plan with concrete reading and hands-on exercises using public datasets, plus self-check questions each month. Point out which resources you're unsure still exist so I can verify them.
```

> **Caution:** Verify standard versions and links; regulations and guidance documents are updated periodically.
