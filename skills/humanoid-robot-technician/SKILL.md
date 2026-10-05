---
name: humanoid-robot-technician
description: "Prompt playbook for a humanoid robot technician. Use when a humanoid robot technician wants help with work tasks such as: fault log triage; return-to-service checklist; safe work and lockout plan; service report from notes; fleet failure pattern analysis; explaining an incident to site staff; deployment site readiness review; ramp-up plan for a new platform."
---

# Humanoid robot technician prompts

Maintains, diagnoses, calibrates and safely returns to service general-purpose humanoid robots (today's analogues: Agility Digit at GXO, Figure at BMW, Apptronik Apollo, Boston Dynamics Atlas at Hyundai) in warehouses, factories and eventually homes. Claude helps most with reading fault logs and telemetry, drafting service reports and procedures, mapping work to forming safety standards (ISO 10218:2025, ISO/TS 15066, ISO 25785-1 in development, EU Machinery Regulation 2023/1230), and getting up to speed on new platforms.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Fault log triage

**Task:** Narrow down the cause of a humanoid fault from logs and symptoms

```text
You are a senior field service engineer for legged humanoid robots. Robot: [MAKE/MODEL, FIRMWARE VERSION]. Symptom: [E.G. RIGHT KNEE OVERTEMP, GAIT STUMBLE ON TURN, FALL EVENT]. Context: [TASK, PAYLOAD, FLOOR SURFACE, AMBIENT TEMP, HOURS SINCE LAST SERVICE]. Log excerpt and telemetry: [PASTE JOINT CURRENTS, ENCODER ERRORS, IMU DATA, FAULT CODES]. Give me a ranked differential of likely causes (mechanical, actuator/drive, sensor/calibration, software/controller, environment), the evidence for and against each, and the cheapest test that would separate each one from the others. List what further data you'd want me to pull. Say plainly where the vendor's fault code meanings are unknown to you rather than guessing.
```

> **Caution:** Fault-code meanings are vendor-specific; confirm against the OEM service manual before replacing parts.

## 2. Return-to-service checklist

**Task:** Build a post-repair verification procedure before a robot goes back on the floor

```text
Act as a robotics safety and reliability engineer. I just completed [REPAIR, E.G. HIP ACTUATOR SWAP / HAND REPLACEMENT / BATTERY PACK CHANGE] on a [MODEL] humanoid deployed in [SITE TYPE]. Draft a return-to-service checklist as a numbered table with columns: step, method, pass criterion, tools/data needed, sign-off. Cover torque and fastener checks, joint zeroing and calibration, encoder and force/torque sensor verification, e-stop and protective stop function, fall-detection behavior, a staged motion test (suspended or gantry first, then supervised walking, then task trial), and battery/thermal checks. Mark which steps the OEM procedure must override, and leave [SITE-SPECIFIC LIMITS] as placeholders.
```

> **Caution:** Use the OEM's validated procedure where one exists; this checklist supplements it, and a qualified person signs off.

## 3. Safe work and lockout plan

**Task:** Plan energy isolation and safe approach for hands-on work on a humanoid

```text
You are an industrial safety specialist familiar with OSHA 29 CFR 1910.147 (lockout/tagout), NFPA 70E, ISO 10218-1/-2:2025 and ISO/TS 15066. I need to do [TASK, E.G. REPLACE ANKLE ACTUATOR / OPEN BATTERY ENCLOSURE] on a [MODEL] humanoid with [BATTERY VOLTAGE/CHEMISTRY] in [LOCATION]. Write a job-specific safe work plan: all hazardous energy sources (electrical, stored battery energy, back-driven motors, gravity/collapse of an unpowered robot, springs), isolation and verification steps, how to support the robot so it can't fall, PPE, and stop-work triggers. Flag where standards for dynamically balancing legged robots are still forming (e.g. ISO 25785-1 in development) and where I must defer to the site's EHS program.
```

> **Caution:** Not a substitute for the site's written LOTO program or the OEM safety manual; lithium pack work may need specific training.

## 4. Service report from notes

**Task:** Turn rough field notes into a clean service report and fleet record

```text
You are a technical writer for a robotics field service team. Turn my raw notes into a service report. Notes: [PASTE NOTES, PART NUMBERS, READINGS, PHOTOS DESCRIBED]. Robot ID: [SERIAL], site: [SITE], customer contact: [ROLE]. Output sections: summary (3 sentences, plain English for the site manager), symptom as reported, diagnosis and evidence, work performed, parts used with serials, test results against pass criteria, root cause (confirmed vs suspected), recommended follow-ups, and downtime. Then give a one-line entry for the CMMS/fleet log. Don't invent readings I didn't give you; list anything missing as [MISSING].
```

> **Caution:** Check serials and readings against the originals before filing; reports may become evidence in incident or warranty claims.

## 5. Fleet failure pattern analysis

**Task:** Spot recurring failures across a fleet and propose preventive maintenance

```text
Act as a reliability engineer applying FMEA and Weibull-style thinking to a humanoid robot fleet. Here is our service history: [PASTE TABLE: ROBOT ID, DATE, OPERATING HOURS, COMPONENT, FAILURE MODE, SITE, TASK]. Identify the top recurring failure modes, any links to site, task, firmware version or hours, and whether failures look like early-life, random or wear-out. Propose preventive maintenance intervals or inspections with your reasoning, and a short list of questions to send the OEM. State your confidence given the sample size, and say when the data is too thin to draw a conclusion.
```

> **Caution:** Small fleets give weak statistics; treat interval suggestions as hypotheses to validate with the OEM.

## 6. Explaining an incident to site staff

**Task:** Communicate a robot fall or near-miss to workers and managers

```text
You help robotics teams communicate clearly and honestly with frontline workers. A [MODEL] humanoid at [SITE] had [INCIDENT, E.G. A FALL NEAR A PICK STATION / UNEXPECTED ARM MOTION], with [INJURIES OR NONE]. Known facts: [FACTS]. Still under investigation: [OPEN QUESTIONS]. Interim measures: [E.G. ROBOT REMOVED FROM SERVICE, ZONE FENCED, SPEED LIMITED]. Write (1) a 150-word floor briefing in plain language that says what happened, what's being done and how workers can report concerns, and (2) a short manager update with next steps and timeline. Don't speculate on cause or assign blame, and keep it consistent with any legal or reporting obligations I note: [OSHA/LOCAL REPORTING STATUS].
```

> **Caution:** Have EHS and, if injuries occurred, legal review before release; OSHA recordkeeping and reporting rules may apply.

## 7. Deployment site readiness review

**Task:** Assess a new site before humanoids are installed

```text
You are a robotics deployment engineer. We plan to deploy [NUMBER] [MODEL] humanoids at [SITE TYPE] to do [TASKS], working [FENCED/COLLABORATIVELY] near [NUMBER] people per shift. Site details: [FLOORING, SLOPES, STAIRS, LIGHTING, WI-FI, CHARGING LOCATIONS, AISLE WIDTHS, TEMPERATURE]. Produce a readiness review: a risk assessment table (hazard, who is exposed, severity, likelihood, controls) in the style of ISO 12100, infrastructure gaps, charging and battery storage needs including fire safety, network and cybersecurity items, spares and on-site tools, and training needed for operators and technicians. Note which items depend on the EU Machinery Regulation 2023/1230 or AI Act if the site is in the EU: [JURISDICTION].
```

> **Caution:** A formal risk assessment needs a competent person and site walkdown; this is a first draft for that process.

## 8. Ramp-up plan for a new platform

**Task:** Learn a new humanoid platform or skill area quickly

```text
Act as a mentor who has trained robotics technicians. I'm a technician with background in [E.G. INDUSTRIAL ARMS / AGVS / AUTOMOTIVE ELECTRICAL] and I'm moving to supporting [MODEL] humanoids in [N] weeks. Build a week-by-week study plan covering legged balance and whole-body control basics, BLDC actuators and harmonic/cycloidal or planetary drives, force/torque and IMU sensors, high-voltage lithium battery safety, ROS 2 diagnostic tools (e.g. ros2 topic echo, rosbag, rqt), and relevant standards (ISO 10218:2025, ISO/TS 15066, ISO 13482 for service robots). For each week give: concepts, a hands-on exercise, and 3 self-test questions. Point out skills I can transfer and the biggest gaps.
```

> **Caution:** Vendor-specific procedures and certifications come from the OEM's training; use this to prepare, not replace it.
