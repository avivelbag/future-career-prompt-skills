---
name: model-behavior-designer
description: "Prompt playbook for a model behavior designer. Use when a model behavior designer wants help with work tasks such as: draft a behavior spec section; build an eval set from a spec; triage behavior regression transcripts; over-refusal vs. harm tradeoff memo; persona and tone style guide; map behavior work to regulation; explain a behavior change to stakeholders; upskilling plan for the role."
---

# Model behavior designer prompts

Model behavior designers decide how AI models and products should act. They write behavior specs and system prompts, define how the model handles refusals, tone and persona, and turn those choices into evals, much like today's model-spec, character and policy teams at AI labs and the conversation designers at companies that deploy AI. Claude helps most by drafting and stress-testing specs, generating eval cases and rubrics, triaging transcripts and explaining behavior decisions to stakeholders.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Draft a behavior spec section

**Task:** Turn a product's intent into a clear, testable behavior specification

```text
You are a senior model behavior designer. Draft a behavior spec section for [PRODUCT/ASSISTANT NAME], used by [USER POPULATION] for [PRIMARY USE CASES]. Cover the following: the default behaviors; what operators may adjust and what users may adjust; hard limits that cannot be changed; how to prioritise when [VALUE A] conflicts with [VALUE B]; and tone and persona. For each rule, give the rationale, one example the rule allows and one it forbids, and one borderline case with the preferred response. Write it the way public model specs are written (e.g. the OpenAI Model Spec, Anthropic's published guidelines for Claude), with numbered sections. End with a list of the ambiguities you could not resolve, for the team to decide.
```

> **Caution:** The spec states intent; trained behavior can differ, so verify every rule with evals before you rely on it.

## 2. Build an eval set from a spec

**Task:** Generate test prompts and grading rubrics for a behavior rule

```text
Act as an evaluation designer. Here is a behavior rule from our spec: [PASTE RULE]. Write [NUMBER] test prompts that probe it: clear-pass cases, clear-fail cases, borderline cases, multi-turn escalations, and cases where operator instructions conflict with user requests. For each prompt, give the ideal response in one or two sentences, a 1-5 grading rubric that a human or an LLM grader could apply, and the specific failure mode it targets (over-refusal, under-refusal, sycophancy, persona drift, etc.). Output JSONL compatible with [EVAL TOOL, e.g. Inspect, promptfoo, OpenAI Evals]. Point out any cases where reasonable graders would disagree.
```

> **Caution:** Do not include real user data or operational uplift for dangerous capabilities in test prompts; use abstracted placeholders for high-risk categories.

## 3. Triage behavior regression transcripts

**Task:** Diagnose why a new model or prompt version behaves worse

```text
You are helping me debug a behavior regression after we changed from [OLD MODEL/PROMPT VERSION] to [NEW VERSION]. Below are [N] transcript pairs (old vs new) for the same inputs, along with our spec excerpt: [PASTE]. Group the differences into failure patterns. For each pattern, give how often it appears, a representative example, the spec clause it violates (or 'spec is silent'), and the likely cause: system prompt wording, a model change, the context or tool setup, or a grader artifact. Suggest a minimal prompt or spec fix for each and say how to confirm it worked. Show the findings as a table, followed by a ranked fix list.
```

> **Caution:** Strip personal data from production transcripts before pasting, in line with your privacy policy and GDPR/CCPA obligations.

## 4. Over-refusal vs. harm tradeoff memo

**Task:** Recommend where to set a refusal boundary for a sensitive topic

```text
Act as a model policy analyst. Our assistant for [DEPLOYMENT CONTEXT] currently [CURRENT BEHAVIOR] on requests about [SENSITIVE TOPIC, e.g. medication dosages, self-harm, security research]. Write a 1-2 page decision memo for [DECISION MAKERS]. It should name who is harmed by refusing too much and who is harmed by refusing too little. Give 3 policy options with example responses for each, plus mitigations such as safe-messaging guidelines, pointers to resources and calibrated caveats. Cover the metrics to watch after launch and your recommendation. Where they apply, cite real frameworks (NIST AI RMF and the Generative AI Profile NIST AI 600-1, WHO/AFSP safe-messaging guidelines). Separate settled practice from open judgment calls.
```

> **Caution:** The final policy decision and accountability belong with your safety/policy owners; get domain experts to review it for medical, legal or security topics.

## 5. Persona and tone style guide

**Task:** Define a consistent assistant personality across channels

```text
You are a conversation and character designer. Create a persona and tone guide for [ASSISTANT NAME], built for [BRAND/ORGANIZATION] and serving [AUDIENCE]. Include: 5 core traits, each with 'sounds like / doesn't sound like' examples; how formality changes across [CHANNELS, e.g. chat, voice, email]; how the persona handles errors, uncertainty, angry users and questions about whether it is an AI; and how it stays honest about being an AI while staying warm. Add 6 example exchanges. Flag any trait likely to encourage sycophancy, over-attachment or deceptive anthropomorphism, and say how to guard against it.
```

> **Caution:** The persona must never deny being an AI when sincerely asked; EU AI Act Article 50 transparency duties may apply.

## 6. Map behavior work to regulation

**Task:** Connect behavior design artifacts to compliance obligations

```text
Act as an AI governance advisor working with a model behavior team. We ship [MODEL/PRODUCT] in [JURISDICTIONS] for [USE CASES]. Map our behavior design artifacts (spec, system prompts, evals, red-team results, release notes) to the relevant obligations in the EU AI Act (incl. Article 50 transparency and the GPAI Code of Practice, if applicable), NIST AI RMF functions, and ISO/IEC 42001 controls. Present it as a table with columns: obligation, the artifact that provides evidence, gaps, owner and priority. Note which obligations are still being phased in or depend on guidance that has not been finalised, and which questions need legal counsel.
```

> **Caution:** This is not legal advice. Check current regulatory text and timelines with counsel, because AI Act guidance is still changing.

## 7. Explain a behavior change to stakeholders

**Task:** Write release notes and an FAQ for a behavior update

```text
You are writing for [AUDIENCE: customer support, enterprise customers, the public]. We changed how our assistant handles [BEHAVIOR AREA]: before, [OLD BEHAVIOR]; now, [NEW BEHAVIOR]; the reason is [RATIONALE]; the eval results are [KEY METRICS]. Write (1) a short changelog entry, (2) a 6-question FAQ that anticipates pushback, including 'is the model censored now?' and 'will my integration break?', and (3) a one-paragraph internal escalation guide for support staff. Write in plain language, without hype, and be honest about known limitations and edge cases.
```

> **Caution:** Don't overstate how reliable the change is; describe eval results as measured on a test set, not as guarantees.

## 8. Upskilling plan for the role

**Task:** Build a learning plan to grow into model behavior design

```text
I am a [CURRENT ROLE, e.g. UX writer, trust & safety analyst, ML engineer] moving into model behavior design. Build a 12-week learning plan at [HOURS/WEEK] hours per week. It should cover: how LLM training shapes behavior (pretraining, RLHF/RLAIF, constitutional approaches); reading published model specs and system cards; designing evals and agreement between graders; red-teaming basics; sycophancy and persona research; and AI governance (NIST AI RMF, EU AI Act). For each week, give a concept, a well-known real resource to read (say if you are unsure whether it still exists), and a hands-on exercise I can do with a public model API. End with a portfolio project that shows the skills.
```

> **Caution:** Check that the resources and links are current; Claude may misremember titles or URLs.
