---
name: pandemic-early-warning-analyst
description: "Prompt playbook for a pandemic early warning analyst. Use when a pandemic early warning analyst wants help with work tasks such as: daily signal triage; wastewater anomaly check; rapid risk assessment draft; iHR Annex 2 notification reasoning; genomic signal interpretation; public and partner messaging; post-event surveillance review; upskilling plan for an analyst."
---

# Pandemic early warning analyst prompts

Epidemic intelligence analysts at public health agencies (WHO Hub for Pandemic and Epidemic Intelligence, ECDC, CDC's Center for Forecasting and Outbreak Analytics, UKHSA) and firms like BlueDot fuse news, wastewater, genomic and syndromic signals to spot outbreaks early and decide what to escalate. AI helps most with triaging high-volume signals, structuring risk assessments under IHR, drafting clear briefs, and stress-testing their own reasoning, while the analyst keeps the call on verification and escalation.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily signal triage

**Task:** Sort a batch of open-source event signals into verify, monitor or discard

```text
You are assisting an epidemic intelligence analyst doing daily event-based surveillance (in the style of WHO EIOS / ECDC epidemic intelligence screening). Below are [NUMBER] raw signals from [SOURCES, e.g. news, ProMED, social media, partner emails]. For each, output a table row with: signal ID, location, suspected hazard, reported cases/deaths, source type and reliability (A-D), credibility of information (1-4), novelty vs. known baseline for [REGION/SEASON], and a recommended action: Verify now / Monitor / Discard, with a one-line reason. Flag duplicates referring to the same event, and list what specific fact would change each verdict. Do not treat any signal as confirmed. Signals: [PASTE SIGNALS]
```

> **Caution:** Triage suggestions only; verification with national focal points or official sources stays with the analyst.

## 2. Wastewater anomaly check

**Task:** Decide whether a wastewater pathogen spike is a real signal or noise

```text
Act as a surveillance epidemiologist reviewing wastewater data (similar to CDC NWSS). Site: [SITE, population served]. Target: [PATHOGEN/TARGET]. Data: [PASTE dates, concentrations, normalisation e.g. PMMoV, flow]. Lab notes: [ANY QC FLAGS, method changes]. Assess whether the latest values represent a meaningful rise. Consider normalisation, lab or method changes, rainfall dilution, sewershed changes, sampling frequency and single-sample outliers. Output: (1) plain verdict (likely real / uncertain / likely artefact) with confidence, (2) the alternative explanations ranked, (3) concrete checks to run next (e.g. rerun, neighbouring sites, clinical syndromic data for [CONDITION]), and (4) whether this meets our escalation threshold of [THRESHOLD RULE].
```

> **Caution:** Do not paste data that could identify small communities or facilities beyond what your data-sharing agreement allows.

## 3. Rapid risk assessment draft

**Task:** Structure a rapid risk assessment for an emerging event

```text
Help me draft a rapid risk assessment for [EVENT, e.g. cluster of severe respiratory illness in LOCATION]. Follow the structure of WHO's Rapid Risk Assessment of Acute Public Health Events manual: hazard assessment, exposure assessment, context assessment, overall risk characterisation (likelihood x consequence) at [NATIONAL / REGIONAL / GLOBAL] level, and confidence in the available information. Use only these facts: [PASTE VERIFIED FACTS AND SOURCES]. For each section, clearly separate what is known, what is assumed, and what is unknown. End with a list of key information gaps and the specific questions to send to [COUNTERPART, e.g. national IHR focal point]. Do not fill gaps with invented figures.
```

> **Caution:** A draft for expert review; the final risk level is a signed-off judgment of the assessment team.

## 4. IHR Annex 2 notification reasoning

**Task:** Walk through whether an event may require notification under IHR

```text
You are advising a national IHR focal point team. Using the IHR (2005) Annex 2 decision instrument, including the 2024 amendments that entered into force in September 2025 (flag anything you are unsure about in the amended text), walk through whether this event may need notification to WHO: [EVENT DESCRIPTION, dates, case counts, pathogen if known, travel/trade links]. Answer each of the four Annex 2 questions (serious public health impact, unusual or unexpected, risk of international spread, risk of travel or trade restrictions) with yes / no / unclear and the evidence for each. Then give an overall reading, the information that would most change it, and a draft of the 150-word event summary we would send if we notify.
```

> **Caution:** The notification decision is a legal obligation of the State Party; confirm against the official IHR text and your national procedures.

## 5. Genomic signal interpretation

**Task:** Interpret a new variant or lineage flag from sequencing data for a non-specialist brief

```text
I am an early warning analyst, not a phylogeneticist. Our genomics team flagged [LINEAGE/VARIANT, e.g. PANGO name] in [LOCATION] based on [Nextstrain / GISAID / internal] data: [PASTE their summary, growth advantage estimates, mutations of interest, sample counts and dates]. Explain in plain language what this does and does not tell us about transmissibility, severity and immune escape, how sampling bias and small counts could mislead, and what a reasonable monitoring posture is. Output a 5-bullet brief for decision-makers plus 3 questions I should put back to the genomics team. Do not speculate about how mutations could be engineered or enhanced.
```

> **Caution:** Stay at the level of interpreting surveillance findings; avoid any discussion of enhancing pathogen properties.

## 6. Public and partner messaging

**Task:** Draft calibrated communications about an early, uncertain signal

```text
Draft communications about [EVENT] for three audiences: (1) a 120-word internal alert to [AGENCY LEADERSHIP], (2) a 200-word note to [PARTNERS, e.g. hospital infection prevention leads, neighbouring jurisdictions] with what to watch for and how to report, and (3) a 100-word public holding statement. Current facts: [VERIFIED FACTS]. Current risk level: [LEVEL] with [CONFIDENCE] confidence. Follow CDC CERC principles: be first, be right, be credible, express uncertainty honestly, and say when the next update will come. Avoid alarmist or falsely reassuring language. After the drafts, list any phrase that could be misread or turned into misinformation and suggest a safer wording.
```

> **Caution:** Public statements must go through your agency's clearance process before release.

## 7. Post-event surveillance review

**Task:** Run a blameless after-action review of a missed or late detection

```text
Act as a facilitator for a blameless after-action review in the style of a WHO intra-action / after-action review. Event: [EVENT]. Timeline: [PASTE when the first signals appeared, when we saw them, when we verified, escalated, and when partners acted]. Data sources available at the time: [LIST]. Build a timeline table showing detection, verification and response intervals (compare to the 7-1-7 target: detect in 7 days, notify in 1, respond in 7). Identify bottlenecks, signals that were missed or deprioritised and why, and contributing factors (data latency, thresholds, staffing, access). Recommend 5 specific, owner-assignable fixes ranked by impact and effort.
```

> **Caution:** Remove names and personal details of staff and patients before pasting.

## 8. Upskilling plan for an analyst

**Task:** Build a learning plan covering the methods the role needs

```text
I am a [CURRENT BACKGROUND, e.g. data analyst / nurse / microbiologist] moving into pandemic early warning work at [ORGANISATION TYPE]. I have [HOURS] hours per week for [MONTHS] months. Build a learning plan covering: field epidemiology basics, event-based and indicator-based surveillance, outbreak detection statistics (e.g. EARS, Farrington, CUSUM), nowcasting and reporting delays, wastewater and genomic surveillance interpretation, IHR and the 2025 WHO Pandemic Agreement, risk communication, and data protection rules that apply to me ([GDPR / HIPAA / OTHER]). For each week, name real free resources where possible (e.g. CDC, ECDC, WHO OpenWHO, TEPHINET), one hands-on exercise, and a self-check question. Flag which resources you are unsure still exist.
```

> **Caution:** Verify links and course availability; the governance landscape (Pandemic Agreement annexes, PABS) is still being finalised.
