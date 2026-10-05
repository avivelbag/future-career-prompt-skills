---
name: synthetic-data-engineer
description: "Prompt playbook for a synthetic data engineer. Use when a synthetic data engineer wants help with work tasks such as: fidelity-utility-privacy evaluation plan; debug a generator failure; eU AI Act Article 10 data governance record; is it still personal data?; simulation domain-gap plan for perception data; explain synthetic data to stakeholders; lLM-generated text data and model-collapse risk; upskilling roadmap."
---

# Synthetic data engineer prompts

Synthetic data engineers build generators (tabular models like SDV or CTGAN, simulators like NVIDIA Omniverse Replicator, and LLM pipelines) that produce training and test data when real data is scarce, sensitive or unsafe to collect. They answer to ML teams, privacy officers and regulators. Claude helps most with designing evaluation plans for fidelity, utility and privacy, debugging generator failures, writing data-governance documentation under the EU AI Act and GDPR, and explaining the trade-offs to people who aren't specialists.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Fidelity-utility-privacy evaluation plan

**Task:** Design an evaluation suite before releasing a synthetic dataset

```text
You are a senior synthetic data engineer. I generated a synthetic version of [DATASET DESCRIPTION: rows, columns, data types, sensitive fields] using [GENERATOR, e.g. SDV GaussianCopula / CTGAN / a fine-tuned LLM]. Its intended use is [DOWNSTREAM USE]. Design an evaluation plan in three sections: (1) fidelity, covering marginals, pairwise correlations and constraint violations; (2) utility, using train-on-synthetic, test-on-real (TSTR) against a train-on-real baseline; (3) privacy, covering distance to closest record, membership-inference and attribute-inference attacks. For each metric give the library or method, a proposed pass threshold with your reasoning, and what a failure would mean. Say which thresholds are judgment calls with no accepted standard.
```

> **Caution:** Passing these metrics does not prove the data is anonymous. A privacy or legal reviewer should approve the release.

## 2. Debug a generator failure

**Task:** Troubleshoot mode collapse, broken constraints or missing rare classes

```text
Act as an ML engineer who specialises in generative models for tabular and time-series data. My synthetic data from [GENERATOR AND VERSION] shows these problems: [SYMPTOMS, e.g. a rare class with 0.4% prevalence is missing, ages below 0 appear, the joint distribution of X and Y has collapsed]. Training config: [EPOCHS, BATCH SIZE, PREPROCESSING, CONDITIONING]. Here are summary stats comparing real and synthetic data: [PASTE TABLE]. Rank the most likely causes. For each one, give a diagnostic I can run and a fix to try, such as conditional sampling, constraint handling, rebalancing or changing the transformer or encoder. Put the answer in a table with the columns cause / evidence / test / fix.
```

## 3. EU AI Act Article 10 data governance record

**Task:** Document a synthetic training set for a high-risk AI system

```text
You are helping me write the data-governance documentation for a training dataset. The dataset is partly synthetic and will be used in [SYSTEM], which may be high-risk under the EU AI Act (Annex III category: [CATEGORY]). Using these facts: [SOURCE DATA, GENERATOR, VERSIONS, FILTERING, BIAS CHECKS, KNOWN GAPS], draft a record that follows the Article 10 elements: design choices, collection and origin, preparation operations, assumptions, an assessment of availability and suitability, bias examination and mitigation, and identified gaps. Format it as headed sections, and mark every claim I still need to evidence with [EVIDENCE NEEDED]. Flag any points where guidance on synthetic data under the Act is still unsettled, including the harmonised standards from CEN-CENELEC JTC 21.
```

> **Caution:** This is a draft for compliance and legal review, not a conformity assessment.

## 4. Is it still personal data?

**Task:** Prepare questions for a privacy and DPO review of a synthetic release

```text
Act as a privacy engineer who knows GDPR Recital 26, the Article 29 Working Party Opinion 05/2014 on anonymisation, and the HIPAA de-identification methods (Safe Harbor and Expert Determination). We want to share synthetic data derived from [SOURCE, e.g. patient records] with [RECIPIENT] for [PURPOSE]. The generator is [GENERATOR], with [DP / NO DP, EPSILON IF ANY], and here are our privacy test results: [RESULTS]. Produce: (1) the residual re-identification risks, assessed against singling out, linkability and inference; (2) the arguments for and against treating this output as anonymous; (3) a list of questions for our DPO or Expert Determination provider. Be explicit about where regulators have not taken a settled position.
```

> **Caution:** Claude cannot decide legal status. The DPO or counsel makes that call.

## 5. Simulation domain-gap plan for perception data

**Task:** Plan a synthetic image or sensor dataset and measure the sim-to-real gap

```text
Act as a perception data lead who uses simulation tools such as NVIDIA Omniverse Replicator, CARLA or Unity Perception. We need synthetic [SENSOR: camera/LiDAR/radar] data to train [MODEL TASK] for [DOMAIN, e.g. warehouse robots]. Real data is scarce for [RARE SCENARIOS]. Produce a plan covering: the scenario taxonomy and coverage targets; domain randomization parameters with ranges; labeling outputs; the real-to-synthetic mixing ratios to test; and how to measure the domain gap (held-out real test set, per-scenario metrics, FID or feature-space distance). Format it as a numbered plan with a short experiment schedule, and list the assumptions I must confirm with field data.
```

> **Caution:** For safety-critical systems, validate against real-world data. Simulation results alone are not enough to sign off.

## 6. Explain synthetic data to stakeholders

**Task:** Brief non-technical leaders, customers or ethics boards

```text
You are a technical communicator. Write a [LENGTH, e.g. 400-word] briefing for [AUDIENCE, e.g. hospital ethics board / product VP / customers] explaining how we use synthetic data in [PROJECT]. Cover what synthetic data is, what it does and does not protect, how we tested privacy and quality (summarise from these results: [RESULTS]), the known limitations (e.g. rare subgroups may be under-represented, and models trained on it can inherit the source data's biases), and who is accountable. Avoid hype and do not say the data is "fully anonymous" or "risk-free". End with 3 likely questions from this audience and plain-language answers.
```

## 7. LLM-generated text data and model-collapse risk

**Task:** Govern LLM-generated training or evaluation data

```text
Act as a data quality lead for an LLM post-training team. We plan to generate [VOLUME] synthetic [INSTRUCTIONS / DIALOGUES / EVAL ITEMS] with [MODEL] for [PURPOSE]. Check the model's terms of service for restrictions on using its outputs to train other models. Design a pipeline review that covers: diversity and deduplication checks; filtering for factual errors and harmful content; contamination of benchmarks; risks of recursive training on model outputs (model collapse) and how to mix in human-written data; and provenance tagging so synthetic items can be traced. Output a checklist with owner, method and acceptance criterion for each item. Then list the open research questions where evidence is still thin.
```

> **Caution:** Read the provider's terms yourself. Never generate data that teaches dangerous capabilities, even for red-team sets, without a security review.

## 8. Upskilling roadmap

**Task:** Build a 12-week learning plan for the role

```text
I am a [CURRENT ROLE, e.g. data scientist / privacy analyst / simulation engineer] moving into synthetic data engineering, focused on [TABULAR / TIME-SERIES / VISION / TEXT] for [INDUSTRY]. I can study [HOURS] per week. Build a 12-week plan with weekly topics, one hands-on exercise each week using open-source tools (e.g. SDV, SynthCity, OpenDP, Replicator), and key readings. Include foundational papers (CTGAN, PATE-GAN, membership inference attacks), NIST SP 800-226, the EU AI Act Article 10, and ISO/IEC 5259 on data quality for ML. End with a portfolio project that demonstrates a full fidelity, utility and privacy evaluation. Mark any resource you are unsure still exists so I can verify it.
```

> **Caution:** Check links and resource availability yourself. Tools in this field change quickly.
