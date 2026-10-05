---
name: ai-trainer-and-evaluator
description: "Prompt playbook for an AI trainer and evaluator. Use when an AI trainer and evaluator wants help with work tasks such as: grading rubric builder; rater disagreement triage; eval suite design; lLM-as-judge validation; eval results write-up; safety red-team test set; training-data compliance check; upskilling plan for raters."
---

# AI trainer and evaluator prompts

AI trainers and evaluators write rubrics, rate and correct model outputs, and design the tests that decide whether a model or agent is good and safe enough to ship. The work is done today by RLHF annotators at firms like Scale AI and Surge AI and by eval teams at AI labs and government AI institutes. Claude helps most with rubric design, diagnosing rater disagreement, checking automated graders, eval planning, and the documentation that emerging rules like the EU AI Act expect.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Grading rubric builder

**Task:** Turn a vague quality goal into a scoreable annotation rubric

```text
You are an experienced RLHF and evaluation lead. I need a grading rubric for human raters scoring model responses on [TASK TYPE, e.g. multi-step tax questions] for [MODEL/PRODUCT]. The quality goal is: [GOAL IN PLAIN WORDS]. Build a rubric with 4-7 criteria. For each criterion give a definition, a 1-5 scale with a concrete anchor description for each score, and one short example response at score 2 and score 5. Then list the 5 edge cases raters are most likely to disagree on, with a ruling for each. Flag any criterion that is likely to reward length or confident tone over correctness. Output as a markdown table plus a numbered edge-case list.
```

> **Caution:** Pilot the rubric on 20-50 items with several raters before scaling; anchors written in the abstract often fail on real data.

## 2. Rater disagreement triage

**Task:** Diagnose low inter-annotator agreement on a labeling batch

```text
Act as an annotation quality analyst. Below is a sample of [N] items where raters disagreed, with each rater's score and comment, plus our rubric. Our agreement this batch was [METRIC, e.g. Krippendorff's alpha = 0.41] versus a target of [TARGET]. Group the disagreements into causes: ambiguous rubric wording, genuinely ambiguous items, rater misunderstanding, or a likely individual rater problem. For each cause give the item IDs, a one-line explanation, and a specific fix (rubric edit, calibration example, or item removal). End with the 3 changes that would most raise agreement. Do not guess which rater is 'right' where the item is genuinely ambiguous; say so instead.

Rubric: [PASTE]
Disagreements: [PASTE]
```

> **Caution:** Strip rater names or other personal data before pasting; rater performance judgments should be made by a person, not from this output alone.

## 3. Eval suite design

**Task:** Plan a capability and regression eval for a model or agent release

```text
You are an evaluation engineer familiar with tools such as UK AISI's Inspect, EleutherAI's lm-evaluation-harness and HELM-style reporting. Design an eval plan for [MODEL OR AGENT] before [RELEASE/MILESTONE]. Its intended use is [USE CASE] and the main risks we worry about are [RISKS]. Propose: (1) the capabilities and failure modes to measure, (2) for each, whether to use an existing public benchmark, a custom set, model-graded scoring, or human review, and why, (3) sample size and how to report confidence intervals, (4) how to check for benchmark contamination, (5) pass/fail thresholds that need human sign-off. Output as a table followed by open questions I must answer.
```

> **Caution:** Public benchmark scores may be contaminated or saturated; treat them as one signal, not a release gate on their own.

## 4. LLM-as-judge validation

**Task:** Check whether an automated grader agrees with humans before trusting it

```text
Act as a skeptical evaluation methodologist. We want to replace some human grading of [TASK] with an LLM judge using this judge prompt: [PASTE JUDGE PROMPT]. I have [N] items scored by both humans and the judge: [PASTE OR SUMMARIZE RESULTS]. Analyze: overall agreement and which statistic is appropriate, where the judge systematically diverges (e.g. favors longer answers, its own model family, first position in pairwise comparisons), and which item types it should never grade alone. Suggest concrete judge-prompt revisions and a re-validation plan with a sample size. Output: findings list, revised judge prompt, then a recommendation of 'adopt', 'adopt with spot checks at [rate]', or 'do not adopt'.
```

> **Caution:** Keep a recurring human-graded sample even after adoption; judge drift is common when the model under test changes.

## 5. Eval results write-up

**Task:** Turn raw eval numbers into a decision memo for product and leadership

```text
You are writing for a non-specialist product and leadership audience. Using the eval results below for [MODEL VERSION] versus [BASELINE], draft a one-page decision memo. Sections: bottom line (2 sentences), what improved, what regressed, what we could not measure, confidence and caveats (sample sizes, error bars, rater agreement), and a recommendation with the decision owner named as [OWNER]. Translate metrics into concrete user-facing examples. Do not overstate small differences; mark any difference within the confidence interval as 'no clear change'.

Results: [PASTE TABLE]
Notable examples: [PASTE 3-5 TRANSCRIPTS]
```

> **Caution:** The release decision stays with the named owner; the memo should support, not make, the call.

## 6. Safety red-team test set

**Task:** Draft a policy-aligned harmful-request test set without producing harmful content

```text
Act as a trust-and-safety evaluation designer. Our usage policy for [PRODUCT] prohibits [POLICY CATEGORIES]. Draft a test-set specification, not the test items themselves, to check refusal and over-refusal behavior. For each category give: subcategories, the kinds of benign-but-borderline requests that should be answered (to measure over-refusal), the kinds of disallowed requests described at a high level, multi-turn and role-play variants to include, and how to score each response (comply / safe-complete / refuse). Map coverage to the NIST AI 600-1 Generative AI Profile risk areas where relevant. Output as a coverage table and a scoring guide.
```

> **Caution:** Never ask for real uplift content (weapons, CBRN, malware) in test items; have cleared specialists write sensitive items under your organization's handling rules.

## 7. Training-data compliance check

**Task:** Prepare data-governance documentation for a fine-tuning dataset

```text
You are an AI governance specialist. I am preparing a fine-tuning or preference dataset: [DESCRIBE SOURCES, SIZE, ANNOTATOR WORKFORCE, PERSONAL DATA PRESENT?]. The model will be deployed in [JURISDICTIONS] for [USE]. Draft a datasheet (in the style of 'Datasheets for Datasets') and a checklist covering EU AI Act Article 10 data-governance expectations if the use could be high-risk, the GPAI training-content summary obligation if relevant, GDPR lawful basis for any personal data, copyright and licence status of sources, and annotator labor and wellbeing practices. Mark each item as met / unknown / gap, and clearly flag where requirements are still being clarified by guidance or standards.
```

> **Caution:** This is a drafting aid, not legal advice; have counsel confirm which AI Act obligations apply and their current effective dates.

## 8. Upskilling plan for raters

**Task:** Plan the move from generalist annotator to eval specialist

```text
Act as a career mentor in AI evaluation. I currently [DESCRIBE WORK, e.g. do freelance RLHF rating on platforms like Outlier or DataAnnotation, X hours/week] and my background is [BACKGROUND/DOMAIN EXPERTISE]. I want to move into [TARGET ROLE, e.g. evaluation engineer or domain-expert rubric lead] within [TIMEFRAME]. Build a 12-week plan with weekly goals covering: evaluation statistics (agreement metrics, confidence intervals), a hands-on eval framework (e.g. Inspect or lm-evaluation-harness), basic Python, rubric and benchmark design, and AI risk frameworks (NIST AI RMF, ISO/IEC 42001 at overview level). Include 2 portfolio projects I could publish without breaching platform NDAs. Output as a week-by-week table.
```

> **Caution:** Check your annotation platform contract before publishing anything derived from paid work.
