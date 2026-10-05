---
name: robot-teleoperation-trainer
description: "Prompt playbook for a robot teleoperation trainer. Use when a robot teleoperation trainer wants help with work tasks such as: operator onboarding curriculum; demonstration quality rubric; operator performance analysis; teleop incident review; latency and degraded-mode drills; remote operation SOP; regulatory landscape brief; trainer upskilling plan."
---

# Robot teleoperation trainer prompts

Trains and certifies the people who remotely pilot robots, whether that's VR and leader-follower rigs collecting demonstration data for humanoid and manipulation models (as at Tesla Optimus, Figure, 1X and TRI with ALOHA/GELLO-style setups), remote drivers for vehicles, or operators in nuclear, subsea and surgical settings. AI helps most with curriculum and assessment design, analyzing operator and demo-quality data, writing SOPs and safety documentation, and tracking fast-moving standards.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Operator onboarding curriculum

**Task:** Design a staged training program for new teleoperators

```text
You are an instructional designer for robot teleoperation. Build a 2-week onboarding curriculum for new operators on [ROBOT PLATFORM, e.g. bimanual arms / humanoid] using [INTERFACE, e.g. VR headset + hand tracking / leader-follower arms]. Trainees' background: [BACKGROUND]. Their end job: [GOAL, e.g. collecting manipulation demos for policy training]. Output a day-by-day table with these columns: learning objective, sim vs. real-hardware time, drills, the safety content required (e-stop, workspace limits, ISO 10218 / ISO/TS 15066 collaborative-operation basics), and pass criteria. Ramp task difficulty gradually and schedule breaks against VR fatigue and simulator sickness. End with a list of the assumptions I should check against our hardware.
```

> **Caution:** Hardware-specific safety limits and e-stop procedures must come from the manufacturer's manual and your site risk assessment, not from Claude.

## 2. Demonstration quality rubric

**Task:** Define what makes a good teleop demo for robot learning

```text
Act as a robot learning data lead. Our operators collect teleoperated demonstrations for training [POLICY TYPE, e.g. diffusion policy / VLA model] on tasks like [TASKS]. Draft a scoring rubric that reviewers can apply in under 60 seconds per episode. Cover task success, smoothness (no jerks, hesitations or re-grasps), consistency of strategy across operators, staying in camera view, recovery behaviors worth keeping, and reasons to discard an episode. For each criterion, give a 1-3 scale with concrete examples. Add metadata fields to log (operator ID, latency, failure tag). Note where the research (e.g. ALOHA, DROID, Open X-Embodiment) is unsettled on whether diverse or consistent demos train better.
```

> **Caution:** Validate the rubric against actual downstream policy performance; reviewer intuition about 'good demos' is often wrong.

## 3. Operator performance analysis

**Task:** Find skill gaps from session logs

```text
You are a training analyst. Below is a CSV of teleop session data: [PASTE DATA: operator_id, date, task, success, episode_duration_s, interventions, collisions, latency_ms, hours_experience]. Analyze it and produce: (1) learning curves by operator, flagging anyone plateauing or regressing; (2) which tasks have the highest failure rates and whether latency or experience explains them; (3) 3-5 targeted drills for the weakest skill areas; (4) any patterns that suggest a hardware or interface problem rather than operator skill. Show your calculations, state sample-size limitations, and don't over-interpret small differences.
```

> **Caution:** Use results for coaching, not as the sole basis for discipline or termination; check local worker-monitoring and privacy rules.

## 4. Teleop incident review

**Task:** Write a blameless post-incident report

```text
Act as a safety facilitator running a blameless post-incident review. Incident: [DESCRIPTION, e.g. arm struck fixture during remote session]. Data available: [LOGS, VIDEO NOTES, OPERATOR STATEMENT, LATENCY TRACE]. Write a report with these sections: timeline, immediate cause, contributing factors (human factors such as workload, mode confusion, depth perception and latency; interface design; training gaps; procedures), what worked, and corrective actions, each with an owner and due date. Use the hierarchy of controls, preferring engineering fixes over 'retrain the operator'. List the open questions the evidence can't answer yet.
```

> **Caution:** Injuries or serious near-misses may trigger OSHA (or local) reporting duties; involve your safety officer and don't treat this draft as the official record.

## 5. Latency and degraded-mode drills

**Task:** Plan training for network delay and link loss

```text
You are a teleoperation human-factors specialist. Our operators control [ROBOT/VEHICLE] over [NETWORK, e.g. 5G / Wi-Fi / satellite] with typical latency [X ms] and worst case [Y ms]. Design a drill set that teaches operators to work under rising latency, jitter, frame drops, video freezes and full link loss. For each drill, give the injected condition, the expected operator behavior (slow down, move-and-wait, hand over to autonomy, safe stop), the success criteria, and the debrief questions. Explain the human-performance effects of delay at each latency band, and say where the research supports specific thresholds and where it doesn't.
```

> **Caution:** Inject faults only in simulation or in a physically safeguarded cell; the robot's safe-stop behavior must be verified engineering, not something operator training replaces.

## 6. Remote operation SOP

**Task:** Draft a standard operating procedure for a teleop station

```text
Act as a technical writer for robotics operations. Draft an SOP for operators running [ROBOT] remotely from [STATION SETUP] in a [ENVIRONMENT, e.g. warehouse / customer home / lab]. Include: pre-shift checks (e-stop test, camera and latency check, workspace clear), session start and handover, ergonomic limits (maximum continuous VR time, breaks), handling bystanders entering the workspace, privacy rules for video from homes or workplaces, abort criteria, and end-of-shift logging. Use numbered steps, mark the safety-critical steps, and include a one-page quick-reference checklist. Leave [TBD] wherever a site-specific value is needed.
```

> **Caution:** Have the SOP reviewed against the robot's risk assessment (ISO 10218 / ISO 12100) and, for home deployments, against applicable privacy law such as GDPR or CCPA.

## 7. Regulatory landscape brief

**Task:** Track standards and rules affecting remote robot operation

```text
You are a regulatory analyst. Brief me on the standards and regulations that apply to remotely operated robots in [JURISDICTION] for [USE CASE, e.g. data-collection humanoids / remote driving / service robots]. Consider ISO 10218-1/2 (2025 revision), ISO/TS 15066, ISO 13482, the EU Machinery Regulation 2023/1230, the EU AI Act, and any remote-driving rules such as Germany's teleoperated driving ordinance. Give each its scope, its status and effective dates, and what it implies for operator training or certification. Clearly separate settled requirements from emerging or proposed ones, and give your knowledge cutoff and what I should verify from primary sources.
```

> **Caution:** Regulatory details and dates change; verify against official texts and consult counsel before relying on them for compliance.

## 8. Trainer upskilling plan

**Task:** Learn the robot-learning side of the job

```text
I'm a robot teleoperation trainer with a background in [BACKGROUND, e.g. game QA / drone piloting / manufacturing]. I want to understand how my operators' demonstrations become trained robot policies, so I can coach operators on what actually matters. Build me an 8-week self-study plan at about 5 hours per week. Cover behavior cloning, action chunking, diffusion policies and vision-language-action models, along with why data quality and diversity matter and how sim-to-real works. For each week, give concepts, 1-2 concrete resources (well-known papers, courses or open-source repos like LeRobot), a hands-on exercise, and a question to test my understanding. Flag any resources you're unsure still exist.
```
