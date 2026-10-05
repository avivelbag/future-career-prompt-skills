---
name: telesurgery-specialist
description: "Prompt playbook for a telesurgery specialist. Use when a telesurgery specialist wants help with work tasks such as: pre-case network readiness review; dual-site case protocol; link-loss contingency plan; adverse event and near-miss write-up; cross-border credentialing and licensure map; patient consent explainer; program metrics and quality dashboard spec; upskilling plan for the role."
---

# Telesurgery specialist prompts

A clinician-engineer hybrid who plans, connects, monitors and documents robotic operations where the surgeon's console and the patient-side robot are in different hospitals, as already piloted with systems such as SSI Mantra, MicroPort Toumai and Edge Medical and studied by the Society of Robotic Surgery's telesurgery work. Claude helps most with network-readiness analysis, protocols and checklists, credentialing and cross-border compliance paperwork, incident write-ups, and patient and team communication. Clinical and go/no-go decisions stay with the licensed surgical team.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Pre-case network readiness review

**Task:** Judge whether a remote link is fit for a scheduled telesurgery case

```text
You are a telesurgery network specialist reviewing a link test before a remote robotic case. Here is the test data: [LATENCY/JITTER/PACKET-LOSS LOG OR SUMMARY], the network path: [DEDICATED FIBER / 5G SLICE / SD-WAN, CARRIERS], the robot system: [SYSTEM AND VERSION] and the planned procedure: [PROCEDURE]. Compare the results with the manufacturer's stated limits [PASTE LIMITS] and with latency figures reported in the published telesurgery literature, citing what you rely on. Output: (1) a table of each metric vs threshold with pass/marginal/fail, (2) the worst-case windows and likely causes, (3) the questions to put to the carrier, (4) a draft go/no-go note for the surgical lead. Say clearly where evidence on safe thresholds is thin.
```

> **Caution:** Manufacturer limits and the surgical lead's decision override any general latency figure; Claude only drafts the analysis.

## 2. Dual-site case protocol

**Task:** Draft a run-of-show and role checklist for a remote robotic operation

```text
Act as a perioperative workflow designer. Draft a dual-site protocol for a telesurgery case: remote surgeon at [SITE A], patient and bedside team at [SITE B], robot [SYSTEM], procedure [PROCEDURE]. Include: roles and who has authority at each phase (remote surgeon, bedside surgeon able to take over, anesthesia, network engineer, vendor support); a pre-op checklist that extends the WHO Surgical Safety Checklist with link, video and console checks; communication channels with a backup voice line; and timed steps from setup to undocking. Format as a numbered checklist plus a one-page RACI table. Mark every item that depends on local policy or the vendor's instructions for use as [CONFIRM LOCALLY].
```

> **Caution:** This is a draft for the hospital's surgical safety committee to review. It does not replace the vendor's instructions for use.

## 3. Link-loss contingency plan

**Task:** Plan the response to latency spikes, video freeze or a full disconnect

```text
You are helping a telesurgery program write contingency procedures. System: [ROBOT SYSTEM], whose documented behavior on signal loss is [PASTE VENDOR DESCRIPTION]. Network: [PRIMARY AND BACKUP PATHS]. On-site backup: [BEDSIDE SURGEON CREDENTIALS, CONVERSION CAPABILITY]. Write a tiered response plan for degraded latency, intermittent video, loss of haptic or control input, and full disconnect. For each tier give the trigger (with measurable thresholds as placeholders), who calls it, the immediate actions in order, and how to hand control to the bedside team or convert to laparoscopy or open surgery. Output as a decision table and a laminated-card summary. Where the vendor documentation is silent, flag it as an open question instead of assuming.
```

> **Caution:** Must be validated in simulation drills and signed off by surgical leadership before use.

## 4. Adverse event and near-miss write-up

**Task:** Turn logs and notes into a structured incident report

```text
Act as a patient-safety analyst. Using the de-identified timeline [EVENT NOTES], system and network logs [LOG EXCERPTS] and staff statements [SUMMARIES], draft an incident report for a telesurgery [NEAR-MISS / ADVERSE EVENT]. Structure: factual timeline with timestamps from both sites; contributing factors grouped as device, network, human, and process; a root-cause analysis (5 Whys or fishbone); immediate and systemic corrective actions with owners; and a note on whether this may meet reporting criteria such as an FDA MDR / MedWatch or [LOCAL REGULATOR] report, listed as questions for risk management. Keep facts separate from inferences and don't assign blame.
```

> **Caution:** Remove patient identifiers before pasting. Risk management and legal decide what is reportable.

## 5. Cross-border credentialing and licensure map

**Task:** Map the licensing, privileging and liability questions for a remote surgeon

```text
You are a healthcare regulatory analyst. A surgeon licensed in [JURISDICTION A] will operate remotely on patients in [JURISDICTION B] using [ROBOT SYSTEM]. Produce a checklist of what must be confirmed: medical licensure where the patient is located (e.g. the Interstate Medical Licensure Compact for US states), hospital credentialing and privileging at both sites (including credentialing by proxy where allowed), device regulatory status for remote use in each jurisdiction, malpractice coverage, data-transfer rules (HIPAA, GDPR or local equivalents), and informed-consent requirements. Format as a table: requirement, governing rule or body, status [UNKNOWN], and the person to ask. State explicitly where telesurgery law is unsettled.
```

> **Caution:** This is not legal advice. Confirm every item with counsel and the regulators concerned.

## 6. Patient consent explainer

**Task:** Explain remote robotic surgery to a patient in plain language

```text
Act as a patient-education writer working with a surgical team. Draft a plain-language explainer, at about an 8th-grade reading level, for a patient offered [PROCEDURE] performed remotely by [SURGEON ROLE] at [REMOTE LOCATION] using [ROBOT SYSTEM]. Cover: how it works, who is in the room with them, what happens if the connection fails (based on [PROGRAM CONTINGENCY SUMMARY]), how their data and video are handled, the alternatives, and the questions they should ask. Write it in a reassuring but honest tone, with no promises about outcomes. Then list the points the surgeon must cover in person for valid informed consent. Output: a one-page handout and a bulleted surgeon talking-points list.
```

> **Caution:** Supports the consent discussion; it does not replace it. The surgeon must review it for accuracy.

## 7. Program metrics and quality dashboard spec

**Task:** Define what a telesurgery program should track and report

```text
You are a surgical quality-improvement lead setting up monitoring for a new telesurgery program running [NUMBER] cases/month across [SITES]. Propose a metrics set: clinical outcomes compared with local in-person robotic cases (operative time, conversions, complications by Clavien-Dindo grade, readmissions), technical metrics (median and p99 latency, link drops, setup time), and process metrics (checklist completion, contingency drills). For each, give the definition, data source, review frequency, and an alert threshold as [PLACEHOLDER]. Suggest how to contribute to registries or published telesurgery outcome efforts. Output as a table plus a short paragraph on confounders that make comparisons with in-person cases misleading.
```

## 8. Upskilling plan for the role

**Task:** Build a learning plan that bridges the surgical and network sides

```text
Act as a career mentor for someone moving into telesurgery from [CURRENT BACKGROUND: e.g. robotic OR nurse / surgeon / clinical network engineer]. Build a 6-month learning plan covering the gaps: robotic platform fundamentals and vendor training pathways, network QoS (latency, jitter, 5G slicing, redundancy), medical device standards (IEC 80601-2-77 for robotic surgical equipment, ISO 14971 risk management, IEC 80001-1 for medical IT networks), human factors and crisis resource management, and the key telesurgery studies and consensus documents. For each month give goals, specific resources (say if you are unsure a resource exists), a hands-on exercise, and a self-check. Finish with five open questions in the field that are worth following.
```

> **Caution:** Check that each recommended course and document exists and is current before you enroll or buy.
