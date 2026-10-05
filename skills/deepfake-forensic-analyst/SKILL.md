---
name: deepfake-forensic-analyst
description: "Prompt playbook for a deepfake forensic analyst. Use when a deepfake forensic analyst wants help with work tasks such as: case intake and examination plan; interpret metadata and container output; reconcile conflicting detector scores; draft the expert report; prepare for cross-examination; explain findings to non-experts; regulatory and provenance landscape check; upskilling plan on new generators."
---

# Deepfake forensic analyst prompts

Examines images, video and audio to determine whether they are authentic, edited or AI-generated, for courts, newsrooms, insurers, platforms, banks and trust-and-safety teams, under evidence standards like ISO/IEC 27037, SWGDE guidance and C2PA provenance. Claude helps most with structuring examinations, interpreting tool and metadata output, drafting defensible reports and explaining uncertainty to non-experts; it cannot itself certify authenticity.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Case intake and examination plan

**Task:** Turn a new authenticity request into a scoped, documented examination plan

```text
You are assisting a digital media forensic examiner. A [CLIENT TYPE: court / newsroom / insurer / platform] has submitted [MEDIA TYPE AND FORMAT, e.g. 42-second MP4 voice-and-video clip] claimed to show [CLAIM]. Known provenance: [HOW IT WAS OBTAINED, CHAIN OF CUSTODY SO FAR]. Draft an examination plan as a numbered checklist covering: evidence preservation and hashing (per ISO/IEC 27037 and SWGDE practice), the questions the examination can and cannot answer, metadata and container analysis, C2PA/Content Credentials check, signal-level and semantic analyses, detector tools to run, and what reference or comparison material to request. Flag any request that is out of scope or likely to yield an inconclusive result.
```

> **Caution:** Work only on copies; never upload original evidence or sensitive personal media to a third-party service without client authorization.

## 2. Interpret metadata and container output

**Task:** Make sense of ExifTool, ffprobe or MediaInfo output for signs of editing or regeneration

```text
Act as a second reviewer for a media forensic examiner. Below is [ExifTool / ffprobe / MediaInfo] output for a file the submitter says came directly from [CLAIMED DEVICE AND APP, e.g. iPhone 15 camera app]. [PASTE OUTPUT]. Compare it against what that device and app would normally produce. Return a table with columns: field, observed value, expected value, consistent / inconsistent / unknown, and possible innocent explanations (e.g. platform re-encoding, messaging-app stripping). End with which observations are worth corroborating and which carry little weight on their own. Say plainly where you are unsure what the device normally writes.
```

> **Caution:** Metadata is easy to forge or strip; treat it as one line of evidence, never a conclusion.

## 3. Reconcile conflicting detector scores

**Task:** Analyze disagreements between deepfake detection tools

```text
I ran [FILE DESCRIPTION] through several detectors: [TOOL 1: score/label], [TOOL 2: score/label], [TOOL 3: score/label] (e.g. Reality Defender, Hive, a lab-trained model). Also observed: [MANUAL FINDINGS, e.g. lip-sync drift at 0:12, compression level]. Explain likely reasons the tools disagree: training-data coverage of the generator family, recompression, resolution, face size, audio-only vs video models, and calibration of their scores. Produce: (1) a ranked list of hypotheses, (2) additional tests that would discriminate between them, (3) suggested wording for how much weight the detector results deserve in the report. Do not convert scores into a single probability.
```

> **Caution:** Detector scores are not calibrated probabilities and have known false positives on compressed or low-quality authentic media.

## 4. Draft the expert report

**Task:** Write a structured, defensible forensic report from case notes

```text
You are helping a forensic examiner write an expert report for [AUDIENCE: court / client / internal]. Using my notes below, draft sections: scope and questions asked, items examined (with hashes), methods and tools with versions, observations, analysis, limitations, conclusion on a stated scale [e.g. ENFSI-style verbal scale or 'consistent with / inconclusive / inconsistent with'], and appendix list. Keep observations separate from interpretation. Flag any conclusion in my notes that goes further than the observations support. Notes: [PASTE CASE NOTES].
```

> **Caution:** The examiner signs and is accountable for every conclusion; check the report against applicable rules such as FRE 702 or local equivalents before filing.

## 5. Prepare for cross-examination

**Task:** Anticipate challenges to methods and conclusions before testimony

```text
Play opposing counsel in a [JURISDICTION] proceeding where I will testify that [MEDIA ITEM] is [MY CONCLUSION]. My methods: [SUMMARY OF METHODS AND TOOLS]. Generate 15 tough cross-examination questions targeting reliability (known error rates, peer review, validation of the tools on this generator type, chain of custody, examiner bias, lab accreditation such as ISO/IEC 17025). For each, give a concise, honest model answer and note where I should concede a limitation. Then list three weak points I should address in the report itself before testifying. Flag where admissibility standards for AI-based tools are still unsettled in this jurisdiction.
```

> **Caution:** Not legal advice; coordinate with retaining counsel on admissibility and disclosure obligations.

## 6. Explain findings to non-experts

**Task:** Communicate an authenticity finding to journalists, executives or a victim

```text
Rewrite the technical conclusion below for [AUDIENCE: newsroom editors / bank fraud team / a person depicted in the media] in under 250 words. Technical conclusion: [PASTE]. Requirements: say what was found and how confident we are without numbers that imply false precision; explain the difference between 'no evidence of manipulation found' and 'proven authentic'; state what could change the conclusion; and include one sentence on next steps. Tone: [NEUTRAL / SUPPORTIVE]. Avoid jargon such as GAN, ELA or PRNU unless briefly explained.
```

> **Caution:** For victims of non-consensual intimate deepfakes, prioritize their privacy and point to takedown routes such as those under the US TAKE IT DOWN Act or platform reporting tools.

## 7. Regulatory and provenance landscape check

**Task:** Map which rules and standards affect a client's synthetic-media workflow

```text
My client is a [ORG TYPE, e.g. EU-facing news publisher / US bank using voice authentication] operating in [JURISDICTIONS]. Summarize the rules and standards relevant to detecting, labeling and responding to synthetic media for them, such as EU AI Act Article 50 transparency duties, the EU Digital Services Act, the US TAKE IT DOWN Act, state deepfake election and likeness laws, NIST AI 100-4 on synthetic content, and C2PA Content Credentials. Output a table: instrument, what it requires or recommends, applies to client yes/no/unclear, effective date, action for us. Mark anything you are unsure is current as of [DATE] and list what I should verify against primary sources.
```

> **Caution:** Laws in this area change quickly; verify every item against the official text before advising a client.

## 8. Upskilling plan on new generators

**Task:** Build a study and validation plan when a new generation model appears

```text
A new [IMAGE / VIDEO / VOICE] generation model, [MODEL NAME OR DESCRIPTION], is being used in cases I see. I am a forensic examiner comfortable with [CURRENT SKILLS, e.g. compression analysis, Amped Authenticate, Python]. Create a 4-week plan to understand its likely artifacts and validate my workflow against it: key papers or benchmark efforts to read (e.g. NIST GenAI evaluations, DFRWS and IEEE WIFS work), how to build a lawfully sourced test set of authentic and generated samples, metrics to record (false positive and negative rates by compression level), and how to document the validation for court. Flag where published research does not yet exist.
```

> **Caution:** Generate test samples only with consenting subjects or your own likeness, and follow the generator's terms of use.
