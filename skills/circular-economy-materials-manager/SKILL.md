---
name: circular-economy-materials-manager
description: "Prompt playbook for a circular economy materials manager. Use when a circular economy materials manager wants help with work tasks such as: material flow map and circularity baseline; recycled feedstock quality troubleshooting; digital Product Passport data plan; recycled content claim evidence pack; packaging EPR fee and reporting prep; take-back program design; cSRD ESRS E5 disclosure draft; supplier engagement brief on secondary materials; upskilling plan for the role."
---

# Circular economy materials manager prompts

A manufacturer's or city's owner of material flows: sourcing recycled and secondary feedstock, designing take-back and reuse loops, and proving recycled content and circularity under rules like the EU ESPR (Digital Product Passports), the Battery Regulation, the PPWR, packaging EPR laws and CSRD ESRS E5. AI helps most with mapping material flows, analysing supplier and quality data, drafting compliance evidence and passport data, and turning shifting regulation into concrete plans.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Material flow map and circularity baseline

**Task:** Build a material flow baseline and circularity indicators for a product line or site

```text
You are a circular economy analyst using ISO 59020:2024 and the WBCSD Circular Transition Indicators. From the data below for [PRODUCT LINE / SITE], build a material flow baseline for [REPORTING YEAR]. Inputs: [MATERIAL PURCHASES BY TYPE, TONNES, % RECYCLED/RENEWABLE], outputs: [PRODUCT TONNAGE, SCRAP, WASTE BY DISPOSAL ROUTE]. Output: (1) a Sankey-style flow table (source, destination, tonnes), (2) % circular inflow and % circular outflow with formulas shown, (3) a list of data gaps and the assumptions you made to fill them, (4) the three largest linear leaks ranked by tonnes and by likely cost. Flag where ISO 59020 leaves method choices open.
```

> **Caution:** Indicators are only as good as supplier declarations; keep the assumption log with the numbers.

## 2. Recycled feedstock quality troubleshooting

**Task:** Diagnose quality defects after switching to recycled or secondary material

```text
Act as a materials engineer specialising in recycled [MATERIAL, e.g. rPET / PCR polypropylene / secondary aluminium alloy]. Since moving from [OLD FEEDSTOCK] to [NEW RECYCLED FEEDSTOCK at X% content], we see [DEFECTS, e.g. black specks, brittleness, colour drift, porosity] in [PROCESS]. Lot data: [MFI/IV, MOISTURE, CONTAMINATION, ALLOY CHEMISTRY BY LOT]. Give: a ranked list of likely root causes with the evidence that would confirm or rule each out, specific tests to run, process-window adjustments to trial, and supplier specification clauses to tighten. Say which causes you cannot judge without lab results.
```

> **Caution:** For food-contact or safety-critical parts, changes need qualification and regulatory approval, not just a process tweak.

## 3. Digital Product Passport data plan

**Task:** Prepare the data model and gaps for an EU Digital Product Passport

```text
You are advising on EU Ecodesign for Sustainable Products Regulation (EU) 2024/1781 Digital Product Passports, and for batteries the Battery Regulation (EU) 2023/1542 battery passport. For our [PRODUCT, CATEGORY, EU MARKETS], list the passport data fields likely required (composition, recycled content, substances of concern, repair and disassembly info, end-of-life instructions), map each to our current source system [PLM / ERP / SUPPLIER PORTAL], and mark gaps. Output a table: field, legal basis, owner, source, status. Clearly separate requirements already in force from those awaiting delegated acts or CEN/CENELEC standards, and list open questions to monitor.
```

> **Caution:** Delegated acts and timelines are still being set; verify against the latest Official Journal and Commission work plan.

## 4. Recycled content claim evidence pack

**Task:** Assemble defensible evidence for a recycled content or recyclability claim

```text
Act as a compliance reviewer for environmental claims. We want to state "[CLAIM]" on [PRODUCT/PACKAGING] sold in [MARKETS]. Evidence available: [SUPPLIER CERTIFICATES e.g. GRS, RecyClass, ISCC PLUS mass balance, ISO 14021 declarations, TEST REPORTS]. Assess the claim against ISO 14021, the US FTC Green Guides, the EU Empowering Consumers Directive (EU) 2024/825 and, for packaging, the PPWR (EU) 2025/40 and any applicable state laws such as California SB 343. Output: verdict (supportable / qualify / drop), required wording changes, missing evidence, and chain-of-custody risks, especially around mass-balance attribution.
```

> **Caution:** Not legal advice; final claim wording needs sign-off from legal counsel.

## 5. Packaging EPR fee and reporting prep

**Task:** Prepare extended producer responsibility reporting and model fee exposure

```text
You are an EPR compliance specialist. We place packaging on the market in [JURISDICTIONS, e.g. Oregon, Colorado, California SB 54, Germany LUCID, France]. From our packaging bill of materials [SKU, COMPONENT, MATERIAL, WEIGHT, UNITS SOLD], produce: (1) tonnage by material category per jurisdiction in the format the relevant PRO or register uses, (2) estimated fees using the rates I provide [FEE SCHEDULES] including eco-modulation bonuses or maluses, (3) the top 10 SKUs where a redesign would cut fees most. Flag categories where the material classification is ambiguous and jurisdictions whose rules are still in rulemaking.
```

> **Caution:** Use the PRO's published fee schedule; rates and categories change annually.

## 6. Take-back program design

**Task:** Plan a product take-back, refurbishment or reuse loop

```text
Act as a reverse logistics and circular business model planner. Design a take-back program for [PRODUCT] used by [CUSTOMER TYPE] in [REGION], annual sales [UNITS]. Constraints: [BUDGET, REFURB CAPACITY, PARTNER RECYCLERS, HAZARDOUS COMPONENTS e.g. Li-ion batteries]. Compare three options (mail-back, retail drop-off, B2B collection with deposit or buy-back) in a table: expected return rate with sources or stated assumptions, cost per unit recovered, recovered material value, regulatory obligations (e.g. WEEE, battery transport rules, Basel Convention for exports), and key risks. Recommend one with a 12-month pilot plan and KPIs.
```

> **Caution:** Return-rate assumptions are highly uncertain; pilot before committing capacity.

## 7. CSRD ESRS E5 disclosure draft

**Task:** Draft the resource use and circular economy section of a sustainability report

```text
You are a sustainability reporting specialist familiar with CSRD and ESRS E5 (Resource use and circular economy), including any simplifications from the EU Omnibus process. Using our double materiality outcome [MATERIAL IROs], policies [POLICIES], targets [TARGETS] and metrics [INFLOWS, OUTFLOWS, WASTE BY TYPE AND ROUTE, % RECYCLED CONTENT], draft the E5 disclosure in plain, audit-ready prose with a datapoint cross-reference table. Mark every figure with its source and estimation method, and list statements an assurance provider is likely to challenge. Note where Omnibus changes have altered scope or datapoints and where that remains unsettled.
```

> **Caution:** Reporting requirements are in flux under the Omnibus package; confirm current scope with your auditor.

## 8. Supplier engagement brief on secondary materials

**Task:** Communicate recycled-content requirements and negotiate with suppliers

```text
Act as a procurement and circularity lead. Write a supplier brief and a one-page FAQ for [SUPPLIER TYPE] explaining our move to [TARGET, e.g. 30% recycled content by 2030 / design for disassembly]. Include: why (regulatory drivers such as [PPWR targets / Battery Regulation recycled content minimums / customer requirements]), the specification and documentation we will require, how we will verify (certifications, audits), support we offer (longer contracts, price indexation to recyclate markets), and timeline. Tone: collaborative, specific. Then list likely supplier objections with suggested responses, and flag where recyclate supply may be too tight to meet the target.
```

## 9. Upskilling plan for the role

**Task:** Build a learning plan for the circular materials manager's knowledge gaps

```text
You are a mentor for circular economy professionals. My background is [BACKGROUND, e.g. procurement / process engineering / EHS] and I now manage materials circularity at [COMPANY TYPE]. Build a 12-week learning plan covering: material science of recycling for [KEY MATERIALS], LCA basics (ISO 14040/14044) and tools like openLCA or SimaPro, ISO 59000-series circularity standards, EU ESPR/PPWR/Battery Regulation, EPR systems, and secondary material markets. For each week give: objective, 2-3 named real resources (books, Ellen MacArthur Foundation materials, standards, courses), a hands-on exercise using my own data, and a self-check question. Say which areas are moving fast and how to keep current.
```

> **Caution:** Verify that resources and course links are current before relying on them.
