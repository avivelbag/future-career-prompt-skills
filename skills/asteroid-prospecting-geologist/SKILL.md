---
name: asteroid-prospecting-geologist
description: "Prompt playbook for an asteroid prospecting geologist. Use when an asteroid prospecting geologist wants help with work tasks such as: target shortlist triage; spectrum-to-composition reasoning; resource estimate with uncertainty; cRIRSCO-style resource statement; legal landscape briefing; mission instrument requirements; risk and planetary protection review; upskilling plan."
---

# Asteroid prospecting geologist prompts

A planetary geologist at a space-resources startup (e.g. AstroForge, Karman+, TransAstra), agency or investor who ranks near-Earth asteroids for water or metals using telescope spectra, meteorite analogues and sample-return data (Hayabusa2, OSIRIS-REx), then reports estimates whose uncertainty is mostly unquantified. Claude helps most with keeping track of the literature and taxonomy, structuring uncertainty, drafting resource statements in the style of terrestrial mining codes, and following the legal regimes as they form.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Target shortlist triage

**Task:** Rank candidate near-Earth asteroids for a prospecting mission

```text
You are a planetary geologist screening near-Earth asteroids for a [WATER / PLATINUM-GROUP METAL] prospecting mission launching around [YEAR]. Here are the candidates with data I pulled from the JPL Small-Body Database and NHATS: [TABLE: designation, H magnitude, albedo, Bus-DeMeo class, rotation period, NHATS min delta-v, mission duration, data sources]. Rank them in a markdown table. Give columns for estimated diameter range (with the albedo assumption stated), likely meteorite analogue, accessibility, key unknowns and the confidence in each. For every ranking, say which single new observation (spectrum, radar, lightcurve, thermal) would change it the most. Do not supply values I did not give you. Mark them 'needs lookup'.
```

> **Caution:** Check every orbital and physical parameter against JPL SBDB/Horizons. Claude cannot query them live and may misremember values.

## 2. Spectrum-to-composition reasoning

**Task:** Interpret a reflectance spectrum and its compositional ambiguity

```text
Act as a reviewer with expertise in asteroid reflectance spectroscopy. I have a [VISIBLE / NEAR-IR, wavelength range] spectrum of [ASTEROID] from [INSTRUMENT/SURVEY]. Features: [BAND CENTERS, BAND DEPTHS, SLOPE, ALBEDO, PHASE ANGLE]. Walk through the Bus-DeMeo classification, plausible meteorite analogues (e.g. CI/CM, ordinary chondrite, iron/enstatite) and competing interpretations, including space weathering and phase reddening. Give the result as: 1) most likely interpretation, 2) alternatives with the reason each stays open, 3) what a 3-micron hydration band observation or radar albedo would resolve, 4) references I should check. Keep established results separate from your own inference.
```

> **Caution:** Verify every reference Claude suggests. Spectral interpretation of M-types and hydration is still disputed (e.g. the pre-Psyche-mission debates).

## 3. Resource estimate with uncertainty

**Task:** Build a transparent tonnage/grade estimate with error propagation

```text
Help me build a first-order resource estimate for [ASTEROID]. Inputs, each with a range: diameter [RANGE], bulk density [RANGE or analogue], macroporosity [RANGE], target constituent [WATER/Ni-Fe/PGM] grade [RANGE, source], and an extractable fraction for a [PROCESS, e.g. thermal volatile extraction] process of [RANGE]. Propagate the uncertainty with a Monte Carlo approach. Give Python (numpy) code, then a table of P10/P50/P90 contained and recoverable mass, and rank the inputs by how much each drives the variance. Then explain in plain words why this is an exploration target and not a reserve under JORC/CRIRSCO-style terminology.
```

> **Caution:** Check the code and its distributions yourself. Grade inputs taken from meteorite analogues can be off by orders of magnitude.

## 4. CRIRSCO-style resource statement

**Task:** Draft an investor or board resource disclosure without overclaiming

```text
You are helping a Competent-Person-style geologist draft a disclosure for [AUDIENCE: board / investors / agency partner] on [ASTEROID]. Adapt the structure of terrestrial reporting codes (JORC 2012, NI 43-101, CRIRSCO template): data sources, sampling (remote vs in-situ), interpretation, estimation method, classification and modifying factors (extraction, transport, market). Our data: [SUMMARY]. There is no adopted reporting code for extraterrestrial resources. Point out where the terrestrial categories do not transfer, and mention the UNECE/UNFC work on space resources only as an open development. Write it as a 1-page statement and add a list of claims a skeptical reviewer would challenge.
```

> **Caution:** Securities rules on forward-looking statements apply. Legal and qualified-person review is required before release.

## 5. Legal landscape briefing

**Task:** Summarize the space-resources law that affects a planned mission

```text
Brief me as a geologist, not a lawyer, on the legal framework for a [US / Luxembourg / UAE / Japan]-licensed company prospecting and possibly extracting from [ASTEROID]. Cover the Outer Space Treaty (Art. II, VI, IX), the US CSLCA 2015 Title IV and comparable national laws, Artemis Accords Section 10 and deconfliction 'safety zones', the Hague Working Group building blocks, and the status of the UN COPUOS Working Group on Space Resources. Format: a table of instrument, binding?, what it means for my survey or sampling work, and open questions. Flag anything that may have changed after your training data, and give me a list of questions for counsel.
```

> **Caution:** This is orientation, not legal advice. National licensing (e.g. FAA/NOAA/Commerce in the US) and the COPUOS process are still changing.

## 6. Mission instrument requirements

**Task:** Translate geologic questions into a prospecting payload requirement set

```text
I'm defining science and prospecting requirements for a [FLYBY / RENDEZVOUS / TOUCH-AND-GO] mission to [ASTEROID], with a [MASS/POWER/BUDGET] limit. Key geologic questions: [e.g. is hydration present at >X wt%, metal fraction, regolith grain size, boulder abundance]. Produce a traceability matrix in the style of a NASA science traceability matrix (STM). Rows are question, measurement, instrument type (e.g. VIS-NIR spectrometer, gamma-ray/neutron spectrometer, thermal IR, radar, lidar), required performance, heritage example (Hayabusa2, OSIRIS-REx, Psyche, Lucy), and the descope consequence. Mark the requirements I can't meet within the limits.
```

> **Caution:** Confirm the heritage instrument specs against mission papers. Engineering margins and flight readiness need sign-off from the instrument team.

## 7. Risk and planetary protection review

**Task:** Pre-review safety, contamination and failure risks for sampling ops

```text
Act as an independent reviewer before our [MISSION PHASE] review for a sampling attempt on [ASTEROID, class]. Using lessons from Hayabusa2, OSIRIS-REx (the low-strength Bennu surface, the sample-container overflow) and failed commercial missions, list the geologic and operational risks: regolith mechanical properties, rubble-pile behavior, rotation, ejecta and debris, sample contamination, and COSPAR planetary protection category for [ONE-WAY / EARTH RETURN]. Output a risk register: risk, likelihood, consequence, mitigation, evidence gap and owner. End with three questions the review board will probably ask.
```

> **Caution:** The COSPAR category and licensing conditions must be confirmed with the relevant authority. Final go/no-go stays with the mission team.

## 8. Upskilling plan

**Task:** Build a 12-week learning path from terrestrial geology into asteroid prospecting

```text
I'm a [ECONOMIC GEOLOGIST / GEOCHEMIST / REMOTE SENSING ANALYST] with [YEARS] of experience in [SPECIALTY], moving into asteroid prospecting. Make a 12-week plan at [HOURS/WEEK]. Cover meteoritics and asteroid taxonomy, reflectance spectroscopy, small-body dynamics and delta-v basics, results from Hayabusa2/OSIRIS-REx sample analysis, the Psyche mission, regolith mechanics and space-resources law. Each week needs a learning goal, 2-3 named textbooks, review papers or public datasets (e.g. RELAB, PDS Small Bodies Node, JPL SBDB), a hands-on exercise, and a self-check question. Tell me which of my existing skills carry over directly.
```

> **Caution:** Check that every recommended source exists and is current. Claude can misattribute titles or authors.
