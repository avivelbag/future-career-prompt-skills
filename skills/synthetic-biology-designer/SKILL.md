---
name: synthetic-biology-designer
description: "Prompt playbook for a synthetic biology designer. Use when a synthetic biology designer wants help with work tasks such as: design-space review before a build; build failure troubleshooting tree; dBTL campaign plan under a fixed budget; biosafety risk assessment draft for IBC review; dNA order screening and KYC readiness; design history and part registry documentation; regulatory pathway map for a product candidate; explain the program to non-scientist stakeholders."
---

# Synthetic biology designer prompts

Synthetic biology designers specify engineered biological systems — pathways, genetic circuits, chassis strains and the DNA parts that build them — and run them through design-build-test-learn cycles at biotech firms, pharma, contract biomanufacturers, agtech and national labs. AI helps most with design-space reasoning, construct and assay documentation, troubleshooting failed builds, and keeping biosafety, order-screening and regulatory paperwork (NIH Guidelines, IBC review, ISO 20688-2 / IGSC screening, EU contained-use rules) complete and consistent.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Design-space review before a build

**Task:** Pressure-test a planned construct design before committing DNA synthesis spend

```text
You are a senior synthetic biology design reviewer. I am designing [CONSTRUCT / PATHWAY, e.g. a 4-enzyme heterologous pathway] in [CHASSIS, e.g. E. coli BL21, S. cerevisiae CEN.PK, Pichia] to produce [TARGET MOLECULE] at [TARGET TITER/RATE/YIELD]. My current design choices: promoters [LIST], RBS/UTR strategy [DETAIL], codon optimization [TOOL], copy number / integration locus [DETAIL], selection markers [LIST]. Review as a table: design choice, main failure risk, cheaper diagnostic I could run first, and one alternative worth a parallel arm. Then list the three assumptions most likely to be wrong and what evidence would settle each. Flag where the literature is thin rather than guessing.
```

> **Caution:** Claude's suggestions are design hypotheses, not validated protocols; a named responsible scientist still signs off on every build.

## 2. Build failure troubleshooting tree

**Task:** Work out why a cloning or assembly step keeps failing

```text
Act as a molecular biology troubleshooting partner. My [ASSEMBLY METHOD, e.g. Golden Gate, Gibson, yeast homologous recombination] build of [CONSTRUCT, size, number of fragments] is failing: observed outcome is [SYMPTOM, e.g. no colonies, correct size but wrong sequence, high background, toxic insert]. Conditions: [ENZYME/KIT, overhang design, insert GC and repeats, host strain, incubation, DNA source and concentrations]. Give me a ranked diagnostic tree: hypothesis, the cheapest test that discriminates it, expected result if true, and the fix. Separate design-level causes (repeats, hairpins, toxicity, internal recognition sites) from execution-level causes. End with the two most informative experiments to run next.
```

> **Caution:** Verify any enzyme, buffer or cycling condition against the current manufacturer protocol before running it.

## 3. DBTL campaign plan under a fixed budget

**Task:** Plan a design-build-test-learn campaign with real throughput and cost limits

```text
You are a design-build-test-learn campaign planner. Goal: move [STRAIN/PRODUCT] from [CURRENT METRIC] to [TARGET METRIC] in [TIMEFRAME]. Constraints: build throughput [N constructs/week], screening capacity [N clones/week at ASSAY], assay noise [CV%], DNA synthesis budget [AMOUNT], headcount [LIST]. Propose a campaign over [N] rounds: what varies each round, library size and design strategy, screening funnel with cutoffs, go/no-go criteria, and what each round must teach the next. Include a table of round, cost, duration, expected information gain, and the risk that round de-risks. Call out where my capacity numbers make the target implausible and what would have to change.
```

> **Caution:** Expected gains are estimates; re-plan after each round rather than committing the full budget up front.

## 4. Biosafety risk assessment draft for IBC review

**Task:** Prepare a defensible containment and risk assessment section for institutional review

```text
You are a biosafety documentation specialist. Help me draft the risk assessment section of an Institutional Biosafety Committee submission for work involving [ORGANISM / VECTOR / INSERT, non-hazardous], at [INSTITUTION], proposed containment [BSL-1/2]. Structure it to the NIH Guidelines for Research Involving Recombinant or Synthetic Nucleic Acid Molecules: agent and insert description, risk group rationale, routes of exposure, containment and practices, waste and decontamination, spill response, training, and medical surveillance. Use [BRACKETS] wherever I must supply institution-specific facts. Flag any element where my described work may fall under a section needing additional review, and note open questions for the biosafety officer rather than resolving them yourself.
```

> **Caution:** Containment determinations are made by the IBC and biosafety officer, not by Claude; never use this for agents or modifications of concern.

## 5. DNA order screening and KYC readiness

**Task:** Make sure a synthesis order package will clear provider screening cleanly

```text
You are a research compliance analyst supporting nucleic acid procurement. I am ordering [NUMBER] synthetic constructs of benign sequences for [PROJECT PURPOSE] from [PROVIDER]. Explain, as a checklist, what a provider operating under the IGSC Harmonized Screening Protocol and ISO 20688-2 will expect from us as the customer: organizational verification, legitimate-use statement, named responsible scientist, end-use description, delivery address, and record retention. Note that flagging thresholds have been moving toward shorter sequence lengths and tell me what to verify with the provider rather than assuming. Draft a reusable intended-use statement template for our orders, with bracketed fields. Flag uncertainty where policy is still changing.
```

> **Caution:** This supports lawful screening compliance only; never ask for help circumventing screening, and route any flagged order to your institution's biosecurity contact.

## 6. Design history and part registry documentation

**Task:** Turn messy build notes into traceable design records

```text
Act as a technical documentation editor for a synthetic biology team. I will paste raw notes for construct [ID]: [DESIGN RATIONALE, part sources, sequence features, assembly method, verification data, strain and plasmid IDs, who built it, dates]. Produce (1) a clean design record with sections Intent, Design, Parts and provenance, Build method, Verification evidence, Known issues, Next steps; (2) a structured part-level table suitable for our registry or SBOL-style entry, with fields for part name, role, source, sequence coordinates, and license or material-transfer constraints; (3) a list of gaps where provenance, licensing or verification data is missing and must be chased before reuse.
```

> **Caution:** Check third-party part licenses and MTA terms yourself; provenance Claude cannot see is not provenance.

## 7. Regulatory pathway map for a product candidate

**Task:** Scope which regimes apply to an engineered organism or its product

```text
You are a regulatory strategy analyst. Our product is [DESCRIPTION, e.g. an enzyme produced by an engineered non-pathogenic yeast, contained use only] intended for [MARKET/APPLICATION] in [JURISDICTIONS, e.g. US, EU]. Map the plausible regulatory routes: which agency or regime likely has jurisdiction, what the triggering question is, and what evidence package each would need. Cover contained use versus deliberate release, product-versus-process framing differences between the US and EU, and genetic-resource access obligations if our strains or sequences came from [SOURCE]. Output as a table plus a short narrative. Mark each row as settled, contested, or unknown, and list the questions for outside counsel.
```

> **Caution:** Regulatory classifications change and vary by jurisdiction; treat this as a scoping aid and confirm with qualified counsel.

## 8. Explain the program to non-scientist stakeholders

**Task:** Brief executives, investors or a community meeting without hype or jargon

```text
You are a science communicator. Turn the following into a [10-MINUTE EXECUTIVE BRIEF / ONE-PAGE INVESTOR UPDATE / COMMUNITY MEETING SCRIPT] for [AUDIENCE, e.g. non-technical board, local residents near our pilot plant]: [PROJECT DESCRIPTION, stage, results so far, containment approach, risks, timeline]. Avoid jargon; explain engineered organisms plainly and say honestly what is contained, what is uncertain, and what we do not yet know. Include an anticipated-questions section with three hostile or skeptical questions and straight answers. Do not overstate readiness or imply approvals we do not have. Flag any claim I should verify before saying it publicly.
```

> **Caution:** Public statements about engineered organisms carry legal and reputational weight; have them reviewed internally before release.
