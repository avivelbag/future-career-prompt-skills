---
name: autonomous-vehicle-remote-operator
description: "Prompt playbook for an autonomous vehicle remote operator. Use when an autonomous vehicle remote operator wants help with work tasks such as: shift handover brief; edge-case decision playbook; incident narrative from logs; latency and connectivity review; operator fatigue and workload plan; regulatory comparison; public and first-responder messaging; upskilling study plan."
---

# Autonomous vehicle remote operator prompts

Remote operators work in a fleet operations center. They answer robotaxis, autonomous trucks and delivery robots that stop and ask for help, giving path guidance as remote assistance or, where the law allows, driving the vehicle remotely. AI helps most by turning event logs into clear incident narratives, writing escalation playbooks, checking work against SAE J3016 and rules like Germany's Level 4 'Technical Supervisor' law, and helping operators stay alert and handle odd edge cases. It cannot make the live call for them.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Shift handover brief

**Task:** Summarize open fleet issues for the incoming remote operations shift

```text
You are helping a remote assistance operator at an autonomous vehicle fleet operations center hand over a shift. Here are my shift notes and ticket export: [PASTE NOTES/TICKETS]. Fleet: [VEHICLE TYPE, e.g. robotaxi / L4 truck / sidewalk robot], operating area: [CITY/ODD]. Write a handover brief with these parts: (1) a 3-line situation summary; (2) a table of open issues with vehicle ID, location, issue, current state, owner and next action; (3) recurring hotspots such as construction zones, school zones or event closures, with times; (4) anything waiting on field support, police or the safety team. Mark anything time-critical at the top. Do not guess the state of a vehicle. If the notes leave it unclear, list it as 'needs confirmation'.
```

> **Caution:** Check vehicle states against the live fleet console before you rely on the brief. It is only a summary of your notes.

## 2. Edge-case decision playbook

**Task:** Draft a remote-assistance playbook for a recurring scenario

```text
Act as an operations lead for an autonomous vehicle remote assistance team. Our vehicles keep stopping and asking for help in this situation: [SCENARIO, e.g. police officer hand-directing traffic, double-parked delivery truck on a single-lane street, flooded underpass]. Our remote role is [REMOTE ASSISTANCE ONLY (path/advice, vehicle keeps the driving task) / REMOTE DRIVING PERMITTED], as defined in SAE J3016. Write a step-by-step playbook covering: what to check on cameras and sensors, which actions are allowed and which are not, when to send the vehicle to a minimal risk condition, when to call field support or emergency services, and the time limits. Format it as a decision tree followed by a one-page checklist. Point out any step where our role definition or local law decides what is allowed.
```

> **Caution:** This is a draft only. Your safety case owner and legal or compliance team must approve it before anyone uses it in live operations.

## 3. Incident narrative from logs

**Task:** Turn event data into a factual incident report draft

```text
You are helping me draft an internal incident report for an event involving an autonomous vehicle and a remote operator intervention. Inputs: timeline from the event log [PASTE], operator actions and timestamps [PASTE], vehicle and perception notes [PASTE], outcome [DAMAGE/INJURY/NONE]. Write: (1) a neutral, timestamped narrative; (2) the remote operator's actions and how long each step took (request to connect, connect to guidance, guidance to resolution); (3) contributing factors, labelled as observed or hypothesized; (4) open questions for engineering. Then list the reporting obligations that may apply, for example the NHTSA Standing General Order crash reporting in the US or [STATE/COUNTRY] DMV or regulator rules. Do not assign blame. Flag every gap in the data.
```

> **Caution:** Reporting deadlines and thresholds are legal duties. Confirm them with your compliance team; do not rely on Claude's list.

## 4. Latency and connectivity review

**Task:** Analyze link quality data to set safe operating limits

```text
Act as a teleoperations systems analyst. Here is connectivity data for our remote operations links: [PASTE OR DESCRIBE: latency, jitter, packet loss, video bitrate, dropouts by location/time, cellular carrier(s)]. Our mode is [REMOTE ASSISTANCE / REMOTE DRIVING at up to X km/h]. Analyze: where and when the link gets worse, how that would affect operator situational awareness and response time, and what the vehicle should do when the link drops. Suggest limits we could use as triggers (for example, a latency threshold that restricts remote driving), plus the data we would need to validate them. Present findings as a summary, a table of hotspots and a list of recommended thresholds with how confident you are in each. Say clearly where published evidence on safe teleoperation latency is thin.
```

> **Caution:** The thresholds are only hypotheses until they are validated in your safety case, for example under ISO 21448 (SOTIF) or UL 4600.

## 5. Operator fatigue and workload plan

**Task:** Design staffing and break rules for remote supervision

```text
You are a human factors advisor for an autonomous vehicle remote operations center. Context: [NUMBER] operators per shift, each covering about [N] vehicles, [SHIFT LENGTH] shifts, average [X] assistance requests per hour with peaks at [TIMES]. Propose a workload and fatigue plan covering: the vehicle-to-operator ratio and when to lower it, break schedules, how to handle surges, alerts for vigilance drop and missed requests, and metrics to track. Base it on established human factors research, such as vigilance decrement and air traffic control or rail control-room practice, and name which analogues you are drawing on. Give a table of rules and then a list of the assumptions to check against our own data. Note where regulation (for example, Germany's Technical Supervisor rules) might set limits.
```

## 6. Regulatory comparison

**Task:** Compare remote-operation rules across target markets

```text
Act as a regulatory research assistant for an autonomous vehicle company planning remote operations in [MARKETS, e.g. California, Arizona, Germany, UK, Japan]. For each market, summarize what is publicly known about rules for remote assistance and remote driving: required qualifications or roles (such as Germany's 'Technical Supervisor' under its Level 4 law, and the UK Automated Vehicles Act 2024), permits, incident reporting, data recording, and limits on remote driving. Use a comparison table with a 'confidence / last known status' column, then a list of open or pending rulemakings. Do not invent statute numbers. If you are unsure, say so and suggest which primary source to check.
```

> **Caution:** These rules change quickly, and Claude's knowledge has a cutoff date. Check every row against official sources and counsel.

## 7. Public and first-responder messaging

**Task:** Write clear communications about stalled vehicles

```text
You are helping a remote operations team communicate with people outside the company. Situation: [e.g. a robotaxi stopped in an intersection during a power outage / a vehicle blocking a fire lane]. Draft three short messages: (1) a script the remote operator reads over the vehicle's two-way speaker to the passenger or a first responder, under 60 words, calm and with concrete next steps; (2) a note for the local fire and police liaison explaining how to reach the operations center, how to move or disable the vehicle under our first-responder interaction plan [DETAILS], and expected response times; (3) a two-sentence public status update. Avoid claims about cause that are not yet confirmed. Mark any placeholder that legal or communications staff must fill in.
```

> **Caution:** Public statements about incidents should go through your communications and legal review before release.

## 8. Upskilling study plan

**Task:** Build a learning plan for a new remote operator

```text
I am a new autonomous vehicle remote operator with a background in [BACKGROUND, e.g. rideshare driving / dispatch / drone piloting]. Build me a 6-week study plan covering: SAE J3016 levels and the difference between remote assistance and remote driving; the basics of AV perception and planning, enough to read the vehicle's 'intent' display; operational design domain (ODD) concepts; minimal risk conditions; the ideas behind ISO 26262, ISO 21448 (SOTIF) and UL 4600 at an overview level; incident reporting; and human factors of supervisory control. For each week, give goals, free public resources where they exist, and 5 self-quiz questions. End with 10 realistic scenario drills I can talk through with a trainer.
```

> **Caution:** Your employer's certification and procedures take priority over any general study plan.
