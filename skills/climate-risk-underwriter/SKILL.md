---
name: climate-risk-underwriter
description: "Prompt playbook for a climate risk underwriter. Use when a climate risk underwriter wants help with work tasks such as: submission triage with climate lens; explain cat model output differences; forward-looking loading rationale; parametric trigger design review; regulatory climate disclosure draft; non-renewal or rate increase explanation; portfolio accumulation and climate stress plan; climate science upskilling plan."
---

# Climate risk underwriter prompts

Underwriters at insurers, reinsurers, MGAs and Lloyd's syndicates who price and select property, agriculture, infrastructure and parametric risks using forward-looking climate and catastrophe models rather than historical losses alone, under growing supervisory scrutiny (NAIC climate disclosure, IFRS S2, EIOPA/PRA climate scenario expectations, California's forward-looking cat model rules). AI helps most with interpreting model output, stress-testing assumptions, drafting referral and regulatory documentation, and explaining decisions to brokers and policyholders, while the underwriter keeps pricing authority.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Submission triage with climate lens

**Task:** Screen a new commercial property submission for climate-driven perils before quoting

```text
You are a senior commercial property underwriter at [CARRIER/MGA]. Review this broker submission for [INSURED NAME]: SOV summary [PASTE LOCATIONS, TIV, CONSTRUCTION, OCCUPANCY, YEAR BUILT], requested limits/deductibles [DETAILS], and our appetite guide [PASTE KEY RULES]. For each location, flag exposure to flood, wind, wildfire, convective storm and heat, noting which data points are missing or suspect (e.g. unknown first-floor elevation, roof age, defensible space). Output a table: location | key perils | data gaps | info to request from broker | preliminary appetite (in/refer/decline) with one-line reason. Do not invent hazard scores; say where I need to run [CAT MODEL / HAZARD TOOL].
```

> **Caution:** Hazard ratings must come from licensed models or hazard data, not the AI's guess; appetite decisions stay with the underwriter.

## 2. Explain cat model output differences

**Task:** Troubleshoot why two catastrophe models or model versions disagree on a portfolio

```text
Act as a catastrophe modeling analyst supporting an underwriter. I ran [PORTFOLIO/ACCOUNT] through [MODEL A, e.g. Verisk Touchstone vX] and [MODEL B, e.g. Moody's RMS vY / Oasis LMF model], with results: AAL [VALUES], 1-in-100 and 1-in-250 OEP [VALUES], by peril/region [PASTE]. Settings: [CLIMATE-CONDITIONED OR NEAR-TERM CATALOG?, DEMAND SURGE, SECONDARY UNCERTAINTY, VULNERABILITY OVERRIDES]. List the most plausible drivers of the gap (hazard catalog, vulnerability curves, exposure mapping, financial terms, climate conditioning), ranked, with a specific check for each. End with which number I can defend in a referral memo and why, flagging what remains uncertain.
```

> **Caution:** The model vendor's documentation is authoritative; treat explanations as hypotheses to verify.

## 3. Forward-looking loading rationale

**Task:** Document a climate trend load applied on top of a historical or vendor-model baseline

```text
You are helping a [LINE, e.g. homeowners in WILDFIRE STATE] underwriter document a forward-looking climate adjustment. Baseline: [MODEL/EXPERIENCE BASIS AND LOSS COST]. Proposed load: [X%] for [PERIOD, e.g. 2026-2030 policy years], based on [EVIDENCE: IPCC AR6 chapter, NGFS scenario, vendor climate-conditioned catalog, academic paper]. Draft a 1-page rationale memo: method, evidence and its limits, sensitivity range (low/central/high), how it avoids double-counting trends already in the model, and open questions for actuarial review. Where regulators restrict use of forward-looking models (e.g. state rate filing rules like California's 2024 catastrophe model regulation), note that I must confirm applicability.
```

> **Caution:** Rate filing use requires actuarial sign-off and jurisdiction-specific regulatory approval; do not cite AI-summarised science without checking sources.

## 4. Parametric trigger design review

**Task:** Stress-test a proposed parametric cover's trigger and basis risk

```text
Act as a parametric insurance structurer reviewing a draft cover for [CLIENT TYPE, e.g. municipal utility / agricultural cooperative] against [PERIL]. Trigger: [INDEX, e.g. wind speed within cat-in-a-circle radius, rainfall from DATA PROVIDER, NDVI], payout schedule [TIERS], data source and reporting latency [DETAILS]. Identify basis-risk scenarios (loss with no payout, payout with no loss), data integrity and dispute risks, how trigger frequency may shift under climate trends, and questions for the data provider. Output: a risk register table (scenario | likelihood | impact | mitigation) plus 3 trigger design alternatives with trade-offs.
```

> **Caution:** Back-test against historical index data before binding; regulatory treatment of parametric covers varies by jurisdiction.

## 5. Regulatory climate disclosure draft

**Task:** Draft underwriting-related sections of a climate risk disclosure or ORSA

```text
You are drafting for a [INSURER TYPE] filing [NAIC Climate Risk Disclosure Survey / IFRS S2 report / ORSA climate scenario section under EIOPA or PRA SS3/19 expectations]. Using our inputs [PASTE: exposure concentrations, scenario results such as NGFS or vendor stress tests, underwriting actions taken, governance structure], draft the sections on underwriting strategy, physical risk scenario analysis, and risk management. Use plain, verifiable statements only; mark any claim lacking supporting data as [NEEDS EVIDENCE]. Add a short list of disclosure requirements I should confirm against the current framework text, since these rules are still evolving.
```

> **Caution:** Disclosures carry legal liability; compliance and legal must verify against the current official framework text.

## 6. Non-renewal or rate increase explanation

**Task:** Explain a climate-driven underwriting decision to a broker or policyholder

```text
You are an underwriter at [CARRIER] writing to [BROKER / POLICYHOLDER] about [NON-RENEWAL / X% RATE INCREASE / NEW DEDUCTIBLE] on [PROPERTY TYPE, LOCATION]. Key drivers: [e.g. updated wildfire model score, reinsurance cost, loss history]. Mitigation credits available: [e.g. Wildfire Prepared Home, IBHS FORTIFIED roof, flood vents]. Draft a clear, respectful 200-word letter and a short broker talking-points list explaining the reasons, what the insured can do, and alternatives (e.g. state FAIR plan, NFIP, surplus lines). Avoid jargon and do not overpromise future terms. Flag any statement that may need state-mandated notice wording.
```

> **Caution:** Non-renewal notices have state-specific timing and content rules; have compliance review before sending.

## 7. Portfolio accumulation and climate stress plan

**Task:** Plan the underwriting response to concentration and climate stress results

```text
Act as a portfolio underwriting manager at [COMPANY]. Current accumulations: [PASTE TIV AND PML BY ZONE/PERIL], reinsurance program [ATTACHMENT, LIMIT, RETENTION], risk appetite limits [DETAILS], and climate stress results [e.g. 2040 SSP2-4.5 / NGFS hot-house scenario uplift by peril]. Propose a 12-month underwriting plan: where to grow, hold or shrink, referral thresholds, data quality requirements, mitigation-based pricing incentives, and triggers for reinsurance renegotiation. Present as a prioritized action table with owners and KPIs, and note where scenario uncertainty is too wide to act on yet.
```

> **Caution:** Withdrawal from regions has availability and fairness implications regulators watch closely; decisions require management and actuarial approval.

## 8. Climate science upskilling plan

**Task:** Build the climate and modeling literacy needed to challenge model output

```text
I am a [YEARS]-year property underwriter strong in [SKILLS] but weak in climate science and cat modeling. Create an 8-week study plan (about [HOURS] per week) to understand: emission scenarios (SSPs, RCPs, NGFS), CMIP6 downscaling and its limits, hazard-vulnerability-exposure-financial model structure, attribution science, and how to interrogate vendor climate-conditioned catalogs. For each week give: concepts, real free sources (e.g. IPCC AR6 WG1 summary, Oasis LMF docs, NGFS scenario portal, CAS/IFoA climate papers), a hands-on exercise using [MY TOOLS], and 3 questions I should be able to ask a modeler afterwards.
```

> **Caution:** Verify links and source currency; credentials such as CPCU or IFoA climate courses may be worth pursuing alongside.
