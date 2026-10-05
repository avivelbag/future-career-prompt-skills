---
name: elder-care-technology-coordinator
description: "Prompt playbook for an elder care technology coordinator. Use when an elder care technology coordinator wants help with work tasks such as: device fit assessment; alert fatigue triage; rPM program documentation; family and resident explainer; consent and capacity scenarios; vendor security and privacy review; rollout and grant plan; upskilling roadmap."
---

# Elder care technology coordinator prompts

Works for senior living operators, home care agencies, Area Agencies on Aging or health systems to select, deploy and support aging-in-place tech (fall detection, remote patient monitoring, medication dispensers, companion devices, telehealth) for older adults and their caregivers. AI helps most with triaging alert data, matching devices to needs, plain-language training material, privacy and consent paperwork, and keeping up with reimbursement and device rules.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Device fit assessment

**Task:** Match aging-in-place technology to one older adult's needs and preferences

```text
You are an elder care technology coordinator. Recommend a technology plan for this client: age [AGE], living situation [ALONE/WITH SPOUSE/ASSISTED LIVING], conditions [CONDITIONS], cognition [e.g. MCI, none], vision/hearing/dexterity [DETAILS], current tech comfort [LEVEL], home internet [YES/NO/CELLULAR ONLY], budget or payer [PRIVATE PAY/MEDICAID WAIVER/MEDICARE ADVANTAGE], and goals in their own words [GOALS]. Output a table: need, device category (e.g. PERS with fall detection, automatic pill dispenser, video calling tablet), key features to require, setup burden, monthly cost range, privacy intrusiveness (low/med/high). Then list 3 questions to ask the client before buying anything. Use device categories, not brand endorsements, and flag where evidence of benefit is weak.
```

> **Caution:** Recommendations need the client's own consent and, where relevant, input from their clinician or OT.

## 2. Alert fatigue triage

**Task:** Analyze a month of monitoring alerts to cut false alarms without missing real events

```text
I coordinate remote monitoring for [NUMBER] residents at [FACILITY/AGENCY] using [SYSTEM TYPE: e.g. bed sensors, wearable fall detection, motion sensors]. Below is a de-identified alert log for [PERIOD] with columns [COLUMNS]. Analyze it: alert volume by type, resident and time of day; likely false-positive patterns (e.g. device removed, low battery, pets); and which alerts were followed by a confirmed event. Propose threshold or workflow changes ranked by expected noise reduction, and for each, state what real events it could cause us to miss. Output a summary, a findings table, and a proposed change list for the care team to approve. Log: [PASTE DATA]
```

> **Caution:** Never loosen safety thresholds without clinical sign-off; remove names and other identifiers before pasting data.

## 3. RPM program documentation

**Task:** Draft workflows and documentation for a Medicare remote patient monitoring program

```text
Help me draft an operating workflow for a remote patient monitoring (RPM) program at [PRACTICE/AGENCY TYPE] for patients with [CONDITIONS, e.g. hypertension, CHF], using [DEVICE TYPES]. Cover enrollment and consent, device setup and education, data review cadence, escalation paths for out-of-range readings, and the documentation typically needed to support CPT codes 99453, 99454, 99457 and 99458 (e.g. days of data transmitted, interactive communication time). Output a step-by-step workflow with a role column (coordinator, nurse, billing provider) and a documentation checklist. Note any requirements you are unsure are current for [YEAR] and that I should verify against the CMS Physician Fee Schedule.
```

> **Caution:** Billing rules change yearly; a compliance officer or biller must confirm before claims are submitted.

## 4. Family and resident explainer

**Task:** Write plain-language explanations of a new monitoring system for residents and families

```text
Write a one-page explainer for residents and their families at [FACILITY] about our new [TECHNOLOGY, e.g. passive motion and bed-exit sensors]. Explain in plain language at about a 6th-grade reading level: what it detects and what it does not, whether there are cameras or microphones, who sees the data and how long it is kept [RETENTION], how staff respond, how to opt out or pause it, and who to contact with concerns [CONTACT]. Use large-print-friendly formatting, short sentences and no jargon. Then write a 5-question FAQ addressing likely worries about surveillance and dignity. Keep the tone respectful, not salesy, and do not overstate safety benefits.
```

> **Caution:** Have staff check every factual claim about the system against the vendor's actual data practices.

## 5. Consent and capacity scenarios

**Task:** Think through consent when a resident has cognitive decline and family wants monitoring

```text
I'm an elder care technology coordinator. Situation: [DESCRIBE, e.g. adult daughter wants in-room monitoring for her father with moderate dementia who has said he doesn't want to be watched]. Jurisdiction: [STATE/COUNTRY]. Is there a health care proxy or guardian? [DETAILS]. Lay out: the ethical tensions (autonomy, safety, dignity, least-restrictive alternative), what generally governs consent here (e.g. advance directives, guardianship scope, facility policy, HIPAA or GDPR where relevant), less intrusive alternatives, and a suggested process for a care conference including whose input is needed. Clearly mark where the answer depends on local law and needs legal or ethics committee review.
```

> **Caution:** Not legal advice; capacity and surrogate decisions belong to clinicians, legal decision-makers and ethics committees.

## 6. Vendor security and privacy review

**Task:** Vet a connected-device vendor for privacy, security and accessibility before procurement

```text
Create a vendor due-diligence questionnaire and scoring rubric for a [DEVICE TYPE, e.g. AI companion tablet / smart speaker check-in service] we are considering for [NUMBER] older adults served by [ORGANIZATION TYPE]. Cover: HIPAA business associate agreement need, data collection and secondary use (including AI model training), data location and retention, security practices (reference NISTIR 8259 IoT baseline and whether it carries the U.S. Cyber Trust Mark), FDA status (general wellness vs regulated device), accessibility (WCAG 2.2 for apps), offline behavior, support hours, and end-of-contract data deletion. Output the questionnaire grouped by section, with red-flag answers noted for each. Vendor materials so far: [PASTE].
```

> **Caution:** Have IT security and privacy/legal review final contracts; vendor self-attestation is not verification.

## 7. Rollout and grant plan

**Task:** Plan a pilot deployment and draft the funding justification

```text
Help me plan a [DURATION] pilot of [TECHNOLOGY] for [NUMBER] older adults through [ORGANIZATION, e.g. an Area Agency on Aging]. Possible funding: [SOURCES, e.g. Older Americans Act Title III, state Medicaid HCBS waiver, foundation grant]. Produce: (1) a phased plan covering site selection, device setup, user training, caregiver onboarding, tech support and device retrieval; (2) measurable outcomes with realistic data sources (e.g. falls with long lie times, social isolation score like UCLA Loneliness Scale, adoption and abandonment rates); (3) a budget table with line items I fill in; (4) a 250-word needs statement. Flag funding eligibility details I must confirm with the funder.
```

> **Caution:** Don't promise outcomes (e.g. reduced hospitalizations) the pilot can't actually measure.

## 8. Upskilling roadmap

**Task:** Build a learning plan covering gerontology, health tech and regulation

```text
I'm moving into an elder care technology coordinator role from a background in [BACKGROUND, e.g. IT support / nursing / social work]. Build a 12-week learning plan of about [HOURS] hours per week covering the gaps for my background among: aging and cognitive change basics, dementia communication, HIPAA and state privacy law, remote patient monitoring billing, FDA device categories, IoT security basics, accessibility design for older adults, elder abuse and scam recognition, and evaluating AI companion tools critically. For each week give objectives, a hands-on exercise, and the type of reputable source to use (e.g. CMS, NIA, AARP research, CAST/LeadingAge). Suggest relevant credentials and note which are widely recognized versus niche.
```

> **Caution:** Verify that any specific course or certification still exists and is respected by employers in your area.
