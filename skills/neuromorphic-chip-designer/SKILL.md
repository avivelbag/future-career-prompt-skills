---
name: neuromorphic-chip-designer
description: "Prompt playbook for a neuromorphic chip designer. Use when a neuromorphic chip designer wants help with work tasks such as: architecture trade study; sNN-to-silicon mapping debug; rTL and verification review; honest benchmark report; customer or funder explainer; tape-out readiness and risk review; roadmap and research planning; upskilling plan for a VLSI engineer."
---

# Neuromorphic chip designer prompts

Neuromorphic chip designers build spiking, event-driven, often in-memory compute hardware for ultra-low-power edge AI and brain-inspired research. The field builds on today's Intel Loihi 2, IBM NorthPole, SpiNNaker2, BrainChip Akida, SynSense and Innatera work. Claude helps most with architecture trade studies, SNN-to-hardware mapping analysis, RTL and verification review, honest benchmarking with NeuroBench, and explaining the technology to customers and funders.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Architecture trade study

**Task:** Compare candidate core architectures for a target workload before committing to RTL

```text
You are a senior neuromorphic hardware architect. I am choosing a core architecture for [TARGET APPLICATION, e.g. always-on keyword spotting / event-camera gesture recognition] with a budget of [POWER BUDGET], [AREA BUDGET] on [PROCESS NODE], and latency under [LATENCY TARGET]. The candidates are [OPTIONS, e.g. digital async LIF cores like Loihi 2 / near-memory digital like NorthPole / mixed-signal analog crossbar / RISC-V plus SNN accelerator]. Compare them in a table covering energy per synaptic operation, memory hierarchy and weight storage, neuron-model flexibility, on-chip learning support, programmability and toolchain maturity, design and verification risk, and yield and variability sensitivity. Cite published reference chips where you can, mark any numbers you are unsure of, and finish with a recommendation and the three experiments that would most reduce uncertainty.
```

> **Caution:** Published energy figures use different definitions of 'operation'. Normalize them before you compare, and check every cited number against the original paper.

## 2. SNN-to-silicon mapping debug

**Task:** Find out why a trained SNN loses accuracy or blows its power budget once it is mapped to hardware

```text
Act as a neuromorphic compiler and mapping engineer. A spiking network trained in [FRAMEWORK, e.g. snnTorch / Norse / Lava / Rockpool] reached [SOFTWARE ACCURACY] in floating point but only [HARDWARE ACCURACY] on [CHIP OR SIMULATOR]. Power is [MEASURED POWER] against an expected [EXPECTED POWER]. Details: weight precision [BITS], neuron model [MODEL], time step [DT], cores used [N], spike rate per layer [RATES], and export path [e.g. NIR / vendor tool]. List the likely causes in order of probability, such as quantization, refractory or leak mismatch, membrane-state overflow, fan-in limits, routing congestion and timing discretization. For each cause, give a diagnostic test and a fix. Return a numbered checklist.
```

> **Caution:** These are hypotheses. Confirm each one with bit-accurate simulation against the hardware model before you change the design.

## 3. RTL and verification review

**Task:** Review a neuron or synapse RTL block and draft a verification plan

```text
You are a design-verification engineer who specializes in event-driven and asynchronous logic. Review this [LANGUAGE, e.g. SystemVerilog] module for a [BLOCK, e.g. LIF neuron update unit / spike router / AER interface]: [PASTE CODE]. The spec is [SPEC SUMMARY: bit widths, leak and threshold behavior, reset semantics, handshake protocol]. Report the following, each item with its line reference: functional bugs, overflow and saturation risks, clock-domain or handshake hazards, and lint concerns. Then write a UVM- or cocotb-style verification plan with a coverage model, the SystemVerilog assertions to add, corner-case stimulus (simultaneous spikes, back-pressure, threshold ties) and a golden-model comparison strategy against [REFERENCE MODEL, e.g. Brian2 / NEST / Python model].
```

> **Caution:** Do not paste proprietary or export-controlled RTL unless your company's policy allows it. An AI review does not replace formal sign-off.

## 4. Honest benchmark report

**Task:** Write up chip results in a reproducible, comparable form

```text
Act as a rigorous benchmarking lead. Help me write a results section for [CHIP NAME] on [TASKS, e.g. NeuroBench keyword spotting, DVS gesture, event-camera optical flow]. My measurements: [ACCURACY, LATENCY, ENERGY PER INFERENCE, POWER BREAKDOWN, MEASUREMENT SETUP]. The comparison baselines are [BASELINES, e.g. a quantized CNN on a Cortex-M55 with Ethos-U55, a GPU, Loihi 2 published numbers]. Structure the report following the NeuroBench algorithm and system track conventions. State exactly what is included in each energy figure (core only, I/O, host, idle/static), list confounders and threats to validity, and point out wherever my comparison could be unfair or overstated. Output a methods paragraph, a results table template and a limitations list.
```

> **Caution:** Never publish numbers you have not measured. Report static power and host overhead even when they make the result look worse.

## 5. Customer or funder explainer

**Task:** Explain the value and limits of neuromorphic hardware to a non-specialist decision maker

```text
You are a technical product manager for a neuromorphic chip startup. Write a [FORMAT, e.g. 1-page brief / 5-slide outline / email] for [AUDIENCE, e.g. an automotive Tier-1 sensing team / a DARPA or EU program manager / a hearing-aid OEM]. They care about [PRIORITIES]. Explain in plain language what event-driven spiking hardware does better than a conventional NPU for [USE CASE] and where it does worse: toolchain maturity, training difficulty, accuracy gaps and supply risk. Back each claim with our data, [OUR DATA], and say where the evidence is still thin. End with a concrete pilot proposal that includes success criteria.
```

> **Caution:** Do not overhype brain-like claims. Every performance number should trace back to a measurement or a cited source.

## 6. Tape-out readiness and risk review

**Task:** Run a pre-tape-out risk and compliance check

```text
Act as a program manager for a [PROCESS NODE] tape-out at [FOUNDRY OR SHUTTLE, e.g. TSMC / GlobalFoundries / an MPW shuttle / an open PDK like SKY130]. The chip is [DESCRIPTION], scheduled for [DATE]. Build a tape-out readiness checklist and risk register that covers: DRC, LVS and antenna clean status; timing closure, including asynchronous and GALS interfaces; analog and mixed-signal corner and Monte Carlo coverage; power-intent (UPF) checks; DFT and scan coverage; package and test plan; IP licensing; and export-control classification under the EAR. If [TARGET MARKET, e.g. automotive / medical] applies, add functional safety under ISO 26262 or IEC 61508. Score each risk for likelihood and impact, name an owner role, and set a go/no-go criterion. Mark the items where I need a qualified expert's sign-off.
```

> **Caution:** Export classification and safety certification decisions belong to qualified compliance staff. Use this list as a starting point only.

## 7. Roadmap and research planning

**Task:** Plan the next chip generation against emerging tech and the competition

```text
You are a research strategist for neuromorphic computing. Our current chip is [CURRENT CHIP SPECS]. We have [TIME HORIZON] and [TEAM AND BUDGET] for the next generation. Assess the following options for that generation: on-chip learning (e-prop or STDP variants), memristive or RRAM/PCM synapses, 3D integration, chiplets over UCIe, support for NIR and Lava interoperability, and larger neuron-model programmability. For each option, give its technical readiness, its dependence on foundry or IP availability, how it would serve [TARGET CUSTOMERS], and its competitive relevance against Intel, IBM, SpiNNcloud, BrainChip, SynSense and Innatera. Output a phased roadmap with decision gates. Flag claims based on press releases rather than peer-reviewed or measured results.
```

> **Caution:** Competitor details change quickly and are often marketing claims. Check them before using them in strategy.

## 8. Upskilling plan for a VLSI engineer

**Task:** Plan a conventional chip designer's move into neuromorphic design

```text
Act as a mentor in computational neuroscience and neuromorphic engineering. I am a [CURRENT ROLE, e.g. digital ASIC designer with 5 years in DSP accelerators]. I know [KNOWN SKILLS] and am weak in [GAPS]. I have [HOURS PER WEEK] for [WEEKS]. Build a week-by-week plan covering: spiking neuron models and dynamics (LIF, Izhikevich, adaptive), surrogate-gradient training, event-based sensors and AER, the Lava, snnTorch and NIR toolchains, and the architecture papers behind Loihi, TrueNorth, SpiNNaker and NorthPole. Each week should include a hands-on mini project, such as a cocotb-verified LIF core in RTL or mapping an SNN through NIR. Name canonical textbooks, papers and courses only if you are confident they exist, and give a self-check quiz for each module.
```

> **Caution:** Check every listed resource before relying on it. The tools change quickly.
