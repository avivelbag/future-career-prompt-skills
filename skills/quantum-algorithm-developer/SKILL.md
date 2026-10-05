---
name: quantum-algorithm-developer
description: "Prompt playbook for a quantum algorithm developer. Use when a quantum algorithm developer wants help with work tasks such as: quantum advantage reality check; fault-tolerant resource estimate; circuit code review; noisy hardware result triage; paper digest and reproduction plan; executive explainer without hype; benchmarking protocol design; export control and crypto-sensitivity check."
---

# Quantum algorithm developer prompts

Designs, benchmarks and resource-estimates quantum algorithms (chemistry, optimization, simulation, error-corrected subroutines) for hardware vendors, national labs, pharma/finance R&D teams and cloud platforms, using SDKs like Qiskit, Cirq, PennyLane and CUDA-Q. Claude helps most with reviewing circuit code, honest classical-vs-quantum comparisons, resource estimates, paper digestion and explaining results to non-specialist stakeholders without hype.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Quantum advantage reality check

**Task:** Assess whether a proposed use case plausibly beats the best classical methods

```text
Act as a skeptical quantum algorithms reviewer. A stakeholder proposes using [ALGORITHM, e.g. QAOA / VQE / quantum phase estimation / HHL] for [PROBLEM AND INSTANCE SIZE] at [ORGANIZATION]. Assess: (1) the strongest classical baselines (e.g. DMRG, coupled cluster, simulated annealing, tensor networks, Gurobi) and their scaling; (2) known dequantization or input/output bottlenecks (data loading, readout, condition number); (3) whether any claimed speedup is proven, heuristic, or disputed in the literature; (4) what hardware scale would be needed. Output a table of claims vs. evidence, then a verdict: pursue, pursue as research only, or drop. Cite papers I should verify and flag where the field is unsettled.
```

> **Caution:** Verify every cited paper exists and says what Claude claims; advantage literature moves fast and is often contested.

## 2. Fault-tolerant resource estimate

**Task:** Build a first-pass logical/physical resource estimate for an algorithm

```text
You are helping me produce a resource estimate for [ALGORITHM] applied to [PROBLEM, e.g. FeMoco ground-state energy to chemical accuracy]. Assumptions: [ERROR-CORRECTION CODE, e.g. surface code], physical error rate [p], cycle time [t], target failure probability [epsilon]. Walk through: logical qubit count, T/Toffoli count, code distance, magic-state factory footprint, physical qubits and wall-clock runtime. Show each formula and intermediate number so I can check it, compare against published estimates for similar problems, and suggest how to cross-check with Azure Quantum Resource Estimator or Qualtran. Output: assumptions table, calculation steps, summary table, and a list of the three assumptions the result is most sensitive to.
```

> **Caution:** Order-of-magnitude only; confirm with a dedicated estimator before quoting numbers externally.

## 3. Circuit code review

**Task:** Review Qiskit/Cirq/PennyLane code for correctness and efficiency

```text
Review this [SDK AND VERSION, e.g. Qiskit 1.x] code implementing [ALGORITHM/SUBROUTINE] for [TARGET BACKEND or simulator]: [PASTE CODE]. Check for: qubit-ordering and endianness errors, incorrect controlled/inverse operations, deprecated APIs, unnecessary depth or two-qubit gate count, measurement and classical post-processing bugs, and transpiler settings unsuited to the device's native gates and connectivity. For each issue give the line, why it matters, and a corrected snippet. Then suggest two small test cases (e.g. a basis-state input with known output) I can run on a statevector simulator to confirm correctness.
```

> **Caution:** Run the suggested tests yourself; SDK APIs change between releases and Claude may misremember signatures.

## 4. Noisy hardware result triage

**Task:** Diagnose why hardware results diverge from simulation

```text
My [ALGORITHM] run on [BACKEND, e.g. IBM Heron / Quantinuum H2 / IonQ Forte] gives [OBSERVED RESULT] while noiseless simulation gives [EXPECTED]. Circuit stats: [QUBITS, DEPTH, TWO-QUBIT GATES], shots [N], calibration data: [T1/T2, GATE AND READOUT ERRORS], mitigation used: [NONE / ZNE / PEC / readout mitigation / dynamical decoupling]. Act as an experienced experimentalist: rank likely causes, estimate expected fidelity from the error budget, and propose a diagnostic plan (e.g. noisy simulation with a device noise model, mirror circuits, shrinking the instance) ordered by cost. Output a ranked hypothesis table and a step-by-step plan.
```

## 5. Paper digest and reproduction plan

**Task:** Turn a new arXiv paper into a summary and reproduction plan

```text
Here is a quantum algorithms paper: [PASTE ABSTRACT + KEY SECTIONS or arXiv ID with text]. Write for an algorithm developer: (1) the core idea in five sentences; (2) the precise claim (complexity, resources, or experimental result) and its assumptions; (3) how it relates to prior work it cites; (4) weaknesses or open questions a referee would raise; (5) a reproduction plan in [SDK] at small scale, listing what I must implement and what results would confirm or refute it. Mark anything you are inferring rather than reading from the text.
```

> **Caution:** Claude can only assess the text you paste; check proofs and figures against the original.

## 6. Executive explainer without hype

**Task:** Explain project status and realistic timelines to non-specialist leadership

```text
Draft a one-page brief for [AUDIENCE, e.g. VP of R&D at a pharma company] on our quantum project: [GOAL, CURRENT RESULTS, HARDWARE USED, NEXT MILESTONES]. Requirements: plain language, no hype; separate what we have demonstrated, what is expected with near-term hardware, and what requires fault-tolerant machines; give honest timeline ranges tied to public vendor roadmaps with uncertainty stated; state the classical baseline we compare against; end with three decisions or resources we need from them. Include a short glossary of at most five terms.
```

> **Caution:** Vendor roadmaps are marketing commitments, not guarantees; say so in the brief.

## 7. Benchmarking protocol design

**Task:** Plan a fair quantum-vs-classical benchmark study

```text
Help me design a benchmarking study comparing [QUANTUM METHOD] against classical solvers for [PROBLEM CLASS]. Specify: instance families and sizes (including hard and easy cases), classical baselines and how to tune them fairly, metrics (time-to-solution, approximation ratio, energy error, total cost including queue and compilation time), statistical treatment and number of repeats, how to avoid cherry-picking, and what to publish (code, data, seeds). Reference relevant community efforts such as QED-C benchmarks or DARPA's Quantum Benchmarking Initiative where applicable. Output as a protocol document with sections and a checklist of fairness pitfalls.
```

> **Caution:** Pre-register the protocol internally before running so results cannot be tuned after the fact.

## 8. Export control and crypto-sensitivity check

**Task:** Flag compliance questions before publishing or sharing work

```text
I plan to [PUBLISH / OPEN-SOURCE / SHARE WITH PARTNER IN COUNTRY X] work on [DESCRIBE: e.g. a compiler pass, error-correction decoder, or improved factoring resource estimate]. Act as a compliance-aware colleague, not a lawyer. Identify which regimes may be relevant (e.g. US EAR quantum controls added by BIS in 2024, Wassenaar, EU dual-use regulation, our employer and funder policies), whether fundamental-research or published-information exclusions might apply, and any sensitivity around cryptanalysis claims and NIST PQC (FIPS 203/204/205) migration messaging. Output a list of questions to bring to export-control counsel and a responsible-disclosure note if relevant. Flag where you are uncertain.
```

> **Caution:** Not legal advice; final determinations belong to your export-control office or counsel.
