---
name: biosecurity-screening-officer
description: "Prompt playbook for a biosecurity screening officer. Use when a biosecurity screening officer wants help with work tasks such as: screening SOP drafting; framework requirement crosswalk; customer verification checklist; escalation and referral playbook; audit evidence package; board and leadership briefing; tabletop exercise design; role learning plan."
---

# Biosecurity screening officer prompts

A compliance and governance role at DNA synthesis providers, benchtop-synthesizer makers, cloud labs, research institutions and funders: running customer and order screening programs against frameworks like the 2023 US Executive Order 14110 synthesis-screening requirements, the HHS Screening Framework Guidance, IGSC Harmonized Protocol, UK Screening Guidance and export-control lists, then documenting decisions and audits. AI helps most with the paperwork and program layer - drafting SOPs and policies, structuring audit evidence, comparing framework requirements, writing escalation and training material, and preparing stakeholder communications - while every judgment on an actual order stays with cleared humans and official channels.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Screening SOP drafting

**Task:** Turn a screening program's practices into a reviewable written SOP.

```text
You are a biosecurity compliance writer. Help me draft a standard operating procedure for our [CUSTOMER / ORDER SCREENING] program at [ORGANIZATION TYPE: synthesis provider / benchtop device maker / core facility]. Write the SOP structure only - scope, roles and authorities, intake, record-keeping, escalation path, decision log, retention period, periodic review, and training requirements - as numbered sections with placeholders where our specifics go: [SCREENING TOOL/VENDOR], [DESIGNATED REVIEWER ROLE], [RETENTION PERIOD], [REGULATOR CONTACT]. Reference the published frameworks we cite: [e.g. HHS Screening Framework Guidance, IGSC Harmonized Screening Protocol]. Do not include, infer or describe any sequences, agents or technical screening criteria - those stay in controlled annexes. Flag sections where published guidance is ambiguous or still evolving.
```

> **Caution:** Process scaffolding only. Any agent-specific or sequence-level content belongs in controlled annexes maintained under your institution's access controls, never in a chat tool.

## 2. Framework requirement crosswalk

**Task:** Compare obligations across the screening frameworks that apply to you.

```text
Act as a regulatory analyst. Build a crosswalk table of the programmatic obligations that apply to [ORGANIZATION] under the frameworks we are subject to or voluntarily follow: [LIST, e.g. US HHS Screening Framework Guidance, Executive Order 14110 synthesis provisions, IGSC Harmonized Screening Protocol, UK Screening Guidance, relevant export-control regimes]. Columns: obligation area (customer verification, order review, record-keeping, reporting, audit, training), what each framework asks for, who it binds, and whether it is mandatory, funding-conditional or voluntary. Keep it at the level of process duties - no technical screening content. End with open questions, recent or pending changes you are unsure about, and which ones I must confirm with counsel or the issuing body before relying on them.
```

> **Caution:** Treat the output as a starting map, not legal advice - verify every citation against the primary document and your counsel, since these frameworks change often.

## 3. Customer verification checklist

**Task:** Build a due-diligence checklist for vetting a new institutional customer.

```text
You are helping me design a know-your-customer workflow for [ORGANIZATION], which supplies [PRODUCT/SERVICE] to research customers. Draft a verification checklist covering: legitimacy of the ordering institution, verifiable institutional affiliation and contact channel, named responsible researcher, stated research purpose and whether it is plausible for that institution type, shipping destination and export-control exposure, payment and intermediary red flags, and sanctions/denied-party list checks against [LIST SOURCES WE USE]. For each item give the evidence to collect, who signs off, and how it is recorded. Output as a table plus a short escalation ladder. Note where judgment is unavoidable and should not be automated.
```

> **Caution:** Checklist design only - do not paste real customer or personal data into a chat tool, and run actual list checks in your official compliance system.

## 4. Escalation and referral playbook

**Task:** Write the decision ladder for handling a flagged order or inquiry.

```text
Act as a biosecurity program manager. Draft an escalation playbook for [ORGANIZATION] describing what happens after our screening process raises a concern, framed purely procedurally. Cover: hold-and-pause rules, who is notified and within what timeframe, internal review panel composition, documentation required at each step, criteria for release vs. refusal vs. external referral, how to contact [RELEVANT AUTHORITY, e.g. FBI WMD Directorate field coordinator / national contact point], confidentiality and need-to-know handling, and customer communication that neither tips off nor defames. Present it as a numbered ladder with a one-page summary card. Flag where our legal obligations to report are unclear and need counsel sign-off.
```

> **Caution:** Keep the content non-specific about what triggered a hold; substantive details of a live case go only through your cleared internal channel and the designated authority.

## 5. Audit evidence package

**Task:** Organize a program audit or funder attestation submission.

```text
You are a compliance documentation specialist. Help me assemble the evidence package for an upcoming [INTERNAL AUDIT / FUNDER ATTESTATION / CUSTOMER SECURITY REVIEW] of our screening program at [ORGANIZATION]. Here is the list of artifacts I have: [PASTE LIST OF SOP VERSIONS, TRAINING RECORDS, DECISION LOG SUMMARY STATS, TOOL CONFIGURATION CHANGE LOG, INCIDENT RECORDS - titles and dates only]. Produce: a mapping of each artifact to the requirement it evidences under [FRAMEWORK], a gap list ranked by how likely an auditor is to ask, suggested remediation with owners and dates, and a two-page cover memo summarizing program maturity. Ask me for anything missing rather than assuming.
```

> **Caution:** Share only artifact titles, dates and aggregate counts - not the contents of decision logs or customer records.

## 6. Board and leadership briefing

**Task:** Explain program posture and resourcing needs to non-expert executives.

```text
Act as a communications advisor. Write a [LENGTH]-slide-equivalent briefing for [AUDIENCE: board / executive team / university research committee] on our biosecurity screening program. Inputs: program scope [DESCRIBE], aggregate volume and outcome statistics [PASTE AGGREGATE NUMBERS ONLY], current gaps [LIST], and the ask [BUDGET / HEADCOUNT / TOOLING]. Structure: why screening matters to this organization commercially and reputationally, what we do today in plain language, how we compare to the published expectations we are measured against, three risks if we do nothing, and the specific decision I need. No technical or agent-level detail. Keep the tone calm and non-alarmist, and tell me which claims need a source before I present them.
```

> **Caution:** Avoid implying certainty about threat levels; executives repeat briefings externally, so keep every claim defensible and sourced.

## 7. Tabletop exercise design

**Task:** Plan a drill to test the screening and escalation process.

```text
You are an exercise designer. Build a [DURATION] tabletop exercise for [ORGANIZATION] to test our screening escalation process, not our technical detection. Participants: [ROLES, e.g. screening officer, legal, security, commercial lead, comms]. Use deliberately non-technical injects - for example an order held at a gate, a customer whose institutional affiliation cannot be verified, a shipping destination change mid-order, a journalist inquiry, a tool outage during peak volume. For each inject give the facilitator prompt, the decision under test, the clock pressure, and the observable we score. Include an after-action review template and a metrics sheet. Explicitly keep all injects free of any agent, sequence or capability detail.
```

> **Caution:** Design injects around process failures only; a realistic-sounding threat scenario is itself a sensitive document and is unnecessary for testing decision flow.

## 8. Role learning plan

**Task:** Build a study path into the biosecurity governance field.

```text
Act as a career mentor in biosecurity governance. I am [BACKGROUND, e.g. molecular biology MSc / export compliance analyst / lab manager] moving into a screening-officer role at [ORGANIZATION TYPE]. Build a [TIMEFRAME] learning plan covering: the public policy landscape and its history, the organizations and standards bodies whose documents I should read, export-control and dual-use research-of-concern governance basics, audit and records discipline, the professional communities and conferences worth joining, and credentials or courses that actually carry weight. Output as a phased table with primary sources to read first and what each one teaches. Flag where the field has no settled training path yet, and where my gaps most need a human mentor rather than reading.
```

> **Caution:** Verify that linked courses, bodies and documents currently exist and are current - this field's institutions and guidance turn over quickly.
