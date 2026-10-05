---
name: smart-city-systems-operator
description: "Prompt playbook for a smart city systems operator. Use when a smart city systems operator wants help with work tasks such as: shift alert triage; traffic signal anomaly diagnosis; post-incident report; sensor deployment privacy review; public service disruption notice; oT cybersecurity hardening plan; council dashboard briefing; upskilling plan for the role."
---

# Smart city systems operator prompts

Works in a city's integrated operations center (like Rio's COR or a traffic management center), watching and coordinating sensor networks, adaptive traffic signals, smart lighting, water and transit telemetry, and dispatching responses across departments. AI helps most with triaging alerts across many systems, drafting incident logs and public notices, writing up privacy and cybersecurity documentation, and turning dashboard data into decisions that council members and residents can understand.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Shift alert triage

**Task:** Prioritize a backlog of mixed alerts at the start of an operations-center shift

```text
You are helping a smart city operations center operator start a shift. Below is an export of open alerts from [PLATFORM, e.g. FIWARE-based dashboard / vendor IOC] covering [SYSTEMS: traffic signals, streetlights, flood sensors, water pressure, transit AVL]. Group alerts that probably share a root cause (same location, time window, network segment or power feed). Rank the groups by public-safety impact first, then service impact. For each group, give the likely cause, the department to notify, the first check to run, and whether it looks like a sensor or comms fault rather than a real-world event. Output a table, then a 5-line handover summary. Say where the data is too thin to judge.

Alerts: [PASTE ALERT EXPORT]
```

> **Caution:** Triage suggestions only; life-safety events go through 911/CAD and established SOPs, not an AI ranking.

## 2. Traffic signal anomaly diagnosis

**Task:** Troubleshoot a corridor where adaptive signal timing is misbehaving

```text
Act as a traffic signal systems engineer. Our corridor [CORRIDOR NAME, N intersections] runs [SCOOT / SCATS / InSync / other adaptive system] with NTCIP 1202 controllers. Since [DATE], travel times rose [X%] in the [DIRECTION] peak. Data attached: [DETECTOR OCCUPANCY / SPLIT AND CYCLE LOGS / ATSPM PURDUE COORDINATION DIAGRAMS / COMPLAINTS]. Give a ranked list of hypotheses (failed loop or video detector, comms dropout, preemption events, plan transition, demand change, construction), the evidence that would confirm or rule out each, and the order to check them. Then list what I can safely change from the TMC versus what needs a field technician or traffic engineer sign-off.
```

> **Caution:** Timing changes should be approved by the licensed traffic engineer of record; verify against MUTCD and local policy.

## 3. Post-incident report

**Task:** Write a structured after-action report for a multi-system city incident

```text
You are drafting an after-action report for a smart city operations center. Incident: [DESCRIPTION, e.g. power outage that took down 40 signals and flood sensors during a storm]. Timeline from logs: [PASTE TIMESTAMPED LOG ENTRIES]. Departments involved: [LIST]. Write the report in this structure: summary; timeline (UTC and local); systems affected and how they failed (fail-safe, fail-dark, stale data); what went well; gaps in detection, communication and handoff; root cause and contributing factors (mark which are confirmed vs. suspected); corrective actions with owner and due date placeholders. Use neutral, no-blame language suitable for city council. Flag any timeline gaps I need to fill.
```

> **Caution:** Check every timestamp and claim against source logs before release; reports may be public records.

## 4. Sensor deployment privacy review

**Task:** Prepare a privacy impact assessment for a new sensor or camera deployment

```text
Act as a privacy analyst for a city government. We plan to deploy [TECHNOLOGY, e.g. computer-vision pedestrian counters / ALPR / acoustic gunshot detection / Wi-Fi presence sensors] at [LOCATIONS] for [STATED PURPOSE]. Jurisdiction: [CITY, STATE/COUNTRY]. Draft a privacy impact assessment covering: data collected and whether it is personal data; retention and deletion; on-device vs. cloud processing; access and sharing (including law enforcement requests); less-invasive alternatives; equity of placement. Map it to what applies to us, e.g. GDPR Article 35 DPIA, the EU AI Act limits on remote biometric identification, state privacy law, or a local surveillance technology ordinance (CCOPS-style). Mark which legal points need confirmation by city counsel.
```

> **Caution:** Not legal advice; city attorney and privacy officer must review, and many cities require council approval for surveillance tech.

## 5. Public service disruption notice

**Task:** Explain an outage or new system to residents in plain language

```text
You write public communications for a city's operations center. Draft a resident notice about [EVENT, e.g. smart streetlight outage in Ward 3 / new adaptive signals on Main St / flood sensor alert system launch]. Facts: [WHAT HAPPENED OR IS CHANGING, AREAS, DATES, WHAT RESIDENTS SHOULD DO, CONTACT / 311 INFO]. Produce three versions: a 280-character social post, a 150-word website notice, and a short SMS alert. Use plain language at about 8th-grade reading level, say what data (if any) the system collects, and avoid technical jargon and overpromising. Note anything that should also be translated into [LANGUAGES].
```

> **Caution:** Confirm facts with the owning department before posting; emergency alerts follow the city's official alerting channels (e.g. WEA/IPAWS).

## 6. OT cybersecurity hardening plan

**Task:** Assess and plan security improvements for connected city infrastructure

```text
Act as an OT/ICS security advisor for municipal infrastructure. Our environment: [DEVICES, e.g. signal controllers, LoRaWAN sensors, SCADA for water, smart lighting gateways], network layout [DESCRIBE SEGMENTATION], remote access [VPN / vendor access], and known issues [DEFAULT CREDENTIALS, UNPATCHED FIRMWARE, ETC.]. Map our gaps to NIST CSF 2.0 functions and IEC 62443 zones and conduits, and note relevant CISA guidance. Output a prioritized 90-day plan: quick wins, items needing vendor coordination, items needing budget, and how to test changes without disrupting live operations. Keep it defensive; flag where a qualified ICS security assessor should verify.
```

> **Caution:** Defensive planning only; never test on live safety-critical systems without change control and the system owner's approval.

## 7. Council dashboard briefing

**Task:** Turn operations KPIs into a briefing for elected officials

```text
You are preparing a quarterly briefing for city council on smart city operations. Data: [PASTE KPIs, e.g. signal uptime, average incident response time, streetlight outage repair days, sensor network availability, 311 resolution times, energy savings], with last quarter and last year for comparison. Write a 1-page briefing: 3 headline findings, a short table of KPIs with trend arrows, what changed and why (separating measured cause from likely cause), equity notes by neighborhood if the data allows, and 2-3 decisions or budget asks for council. Where useful, reference ISO 37120/37122 indicator definitions so figures are comparable with other cities. Flag metrics that could mislead.
```

> **Caution:** Double-check every number against the source dashboard; don't infer causation the data doesn't support.

## 8. Upskilling plan for the role

**Task:** Build a learning path for an operator moving into integrated city operations

```text
I work as a [CURRENT ROLE, e.g. traffic management center operator / IT network admin / 911 dispatcher] and am moving into a smart city systems operator role at [CITY / ORGANIZATION]. I have [HOURS] per week for [MONTHS]. Build a learning plan covering: IoT and LPWAN basics (LoRaWAN, NB-IoT), data platforms and standards (FIWARE / NGSI-LD, open data), traffic systems (NTCIP, ATSPM), OT cybersecurity (NIST CSF, IEC 62443), privacy and AI governance (GDPR, EU AI Act, NIST AI RMF), and incident command (ICS/NIMS). For each week list one concept, one hands-on exercise, and one real resource or certification. Tell me which parts of this field are still unsettled and where standards are likely to change.
```

> **Caution:** Verify course names, certification requirements and links are current before enrolling.
