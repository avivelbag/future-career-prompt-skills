---
name: quantum-hardware-technician
description: "Prompt playbook for a quantum hardware technician. Use when a quantum hardware technician wants help with work tasks such as: cooldown anomaly triage; qubit characterization drift report; wiring and attenuation budget check; maintenance procedure writer; explain a hardware outage to non-specialists; helium-3 and cryogen supply plan; export control and compliance check; upskilling path from fab/cryo tech to quantum hardware."
---

# Quantum hardware technician prompts

Quantum hardware technicians build, cool down, wire, calibrate and maintain quantum processors and their cryogenic, vacuum, laser and microwave control systems at companies like Google, IBM, Rigetti, IonQ and Quantinuum and at national labs. AI helps most with triaging sensor and calibration data, drafting SOPs and outage reports, planning cryogen and spares logistics, flagging export-control questions, and structured upskilling.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Cooldown anomaly triage

**Task:** Diagnose an abnormal dilution refrigerator cooldown from sensor logs

```text
You are a senior cryogenics engineer helping a quantum hardware technician. Our [FRIDGE MODEL, e.g. Bluefors XLD / Oxford Triton] cooldown is behaving abnormally: [SYMPTOM, e.g. mixing chamber stalls at 45 mK, still pressure rising]. Below are timestamped readings for stage temperatures, pressures (P1-P6 or equivalent), flow and still heater power: [PASTE LOG EXCERPT]. Recent changes: [WIRING/SAMPLE/MAINTENANCE CHANGES]. Give: 1) a ranked list of likely causes (e.g. leak, blocked impedance, heat load from new wiring, mixture loss) with the evidence for each, 2) the next safe diagnostic check for each, 3) what would rule it out. Flag anything that requires stopping and escalating to the system owner or vendor.
```

> **Caution:** Follow the vendor manual and site procedures; never vent or open a cold or pressurized system on AI advice alone.

## 2. Qubit characterization drift report

**Task:** Summarize nightly calibration data and flag degraded qubits

```text
Act as a superconducting qubit characterization specialist. Here is tonight's calibration output for device [DEVICE ID] on [FRIDGE]: per-qubit T1, T2 echo, qubit frequency, readout fidelity, and single/two-qubit gate errors from randomized benchmarking: [PASTE TABLE/CSV]. Baseline from last week: [PASTE BASELINE]. Produce: a table of qubits whose metrics moved beyond [THRESHOLD], likely physical explanations (TLS defects drifting into resonance, frequency collisions, readout amplifier/TWPA gain change, thermalization, cosmic-ray events), a suggested recalibration or retune order, and a three-line summary for the device team's standup. State which conclusions are statistically weak given the sample sizes.
```

> **Caution:** Correlation in a single night's data is weak evidence; confirm with repeated measurements before swapping hardware.

## 3. Wiring and attenuation budget check

**Task:** Review a proposed cryogenic wiring plan for heat load and noise

```text
You are a cryogenic microwave engineer. I'm adding [NUMBER] new drive/flux/readout lines to a [FRIDGE MODEL] for a [QUBIT COUNT]-qubit chip. Proposed plan per stage (50 K, 4 K, still, cold plate, mixing chamber): cable types [e.g. stainless/CuNi/NbTi coax, flex lines], attenuators [dB per stage], filters [e.g. Eccosorb, low-pass], amplifiers [HEMT, TWPA]. Available cooling power per stage: [VALUES]. Estimate passive and active heat load per stage, effective noise temperature reaching the qubit for drive lines, and margin against cooling capacity. Present as a stage-by-stage table, list assumptions and material data you used, and flag where my numbers are missing or where vendor data should be checked.
```

> **Caution:** Treat estimates as first-pass; verify thermal conductivities and attenuator specs against vendor datasheets.

## 4. Maintenance procedure writer

**Task:** Turn rough notes into a step-by-step SOP with hazards

```text
Act as a technical writer for a quantum hardware lab. Convert my rough notes into a standard operating procedure for [TASK, e.g. warming up and swapping a sample on the mixing chamber plate / cold trap regeneration / pulse tube service]. Notes: [PASTE NOTES]. Format: purpose, scope, required PPE and tools, prerequisites and lockouts, numbered steps with expected readings and hold points, hazards (oxygen deficiency from helium/nitrogen, cryogenic burns, pressure, ESD damage to junctions, magnetic fields), sign-off fields, and a revision log. Mark any step where my notes are ambiguous with [CONFIRM] rather than guessing values.
```

> **Caution:** SOPs must be reviewed and approved by the lab safety officer and system owner before use.

## 5. Explain a hardware outage to non-specialists

**Task:** Write an outage update for users of a cloud quantum system

```text
You are a communications lead for a quantum computing team. Our system [SYSTEM NAME] was unavailable from [START] to [END] because of [TECHNICAL CAUSE, e.g. fridge warm-up after a pulse tube compressor fault, recalibration after TLS drift]. Affected: [USERS/QUEUES]. Write two versions: 1) a 120-word status-page note for external users of the cloud service, plain language, with what happened, impact on queued jobs, and expected return; 2) a 200-word internal summary for management with root cause, recovery time, and what prevents recurrence. Don't speculate beyond the facts I've given; mark unknowns explicitly.
```

> **Caution:** Check with your team before sharing anything on unreleased hardware or confidential metrics externally.

## 6. Helium-3 and cryogen supply plan

**Task:** Plan cryogen, He-3 and spares inventory for a fridge fleet

```text
Act as an operations planner for a lab running [NUMBER] dilution refrigerators ([MODELS]). Inputs: planned cooldowns per quarter [NUMBER], typical liquid nitrogen/helium use per cooldown [VALUES], He-3/He-4 mixture held [LITERS STP], compressor and pulse tube service intervals [VALUES], lead times for critical spares [LIST]. Build a 12-month plan: consumables forecast, spares to stock, service calendar, and single points of failure. Note supply risks known for He-3 and liquid helium and how labs typically mitigate them (mixture recovery, dry systems, multi-vendor), and say where current market information should be verified.
```

> **Caution:** He-3 availability and pricing change; confirm with suppliers rather than relying on model knowledge.

## 7. Export control and compliance check

**Task:** Flag export-control questions before shipping or sharing hardware

```text
You are a compliance-aware assistant, not a lawyer. Our lab plans to [ACTION, e.g. ship a cryogenic amplifier to a partner in [COUNTRY], host a visiting researcher from [COUNTRY], share chip layout files]. Items involved: [DESCRIBE HARDWARE/SOFTWARE/TECHNICAL DATA]. Using what you know of the US EAR (including the September 2024 BIS rule adding controls on quantum computing items and cryogenic components) and [OTHER REGIME, e.g. EU dual-use regulation], list the questions our export compliance officer will need answered, which item categories may be relevant, and what documentation to gather. Clearly flag where rules are recent or evolving and where you are uncertain.
```

> **Caution:** Export classification is a legal determination; always route through your export compliance office.

## 8. Upskilling path from fab/cryo tech to quantum hardware

**Task:** Build a personal learning plan for the role

```text
Act as a mentor in experimental quantum computing. My background: [e.g. semiconductor fab technician / vacuum and cryogenics tech / electronics tech], comfortable with [SKILLS], weak at [GAPS]. I have [HOURS/WEEK] for [MONTHS]. Design a learning plan to become an effective quantum hardware technician on [PLATFORM: superconducting / trapped ion / neutral atom / photonic]. Include: core physics concepts in the order I need them, hands-on skills (microwave measurement with VNA/spectrum analyzer, cryo operation, wirebonding, Python with QCoDeS/Qiskit/Cirq), real textbooks, free courses or reviews worth reading, and a weekly checkpoint exercise. Quiz me with three questions at the end of each phase.
```
