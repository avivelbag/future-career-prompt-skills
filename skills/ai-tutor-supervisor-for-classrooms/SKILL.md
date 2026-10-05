---
name: ai-tutor-supervisor-for-classrooms
description: "Prompt playbook for an AI tutor supervisor for classrooms. Use when an AI tutor supervisor for classrooms wants help with work tasks such as: daily tutor-session triage; audit a tutor explanation; weekly report to teacher team; parent communication about AI tutoring; vendor and deployment risk review; over-reliance intervention plan; incident write-up; upskilling plan for the role."
---

# AI tutor supervisor for classrooms prompts

A teacher-adjacent role, already appearing in schools piloting tutors like Khanmigo, that watches over AI tutors in classrooms: checking the accuracy and pedagogy of their dialogue, spotting students who are stuck or over-reliant, escalating safeguarding flags, and reporting to teachers, parents and district leaders under FERPA/COPPA and, in the EU, the AI Act's high-risk rules for education. Claude helps most with reviewing transcripts and dashboard data, drafting reports and parent letters, and building evaluation and governance checklists.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Daily tutor-session triage

**Task:** Turn an anonymized export of AI tutor sessions into a prioritized follow-up list for the teacher

```text
You are helping me, an AI tutor supervisor in a [GRADE/SUBJECT] classroom, triage today's AI tutor sessions. Below is an anonymized export from [TUTOR PLATFORM] (student IDs only, no names): [PASTE SESSION SUMMARIES OR METRICS]. Flag: (1) students who seem stuck or are looping on the same misconception, (2) signs of over-reliance, such as asking for answers instead of attempting steps, (3) sessions where the tutor may have given a wrong or misleading explanation, and (4) any content that might be a safeguarding concern. Output a table with columns Student ID | Flag type | Evidence (quote) | Suggested teacher action | Urgency (today/this week). Keep separate what the data shows and what you are inferring.
```

> **Caution:** Only paste de-identified data your district's FERPA/privacy agreement allows; any possible safeguarding concern goes straight to the designated staff member, not into a chatbot review queue.

## 2. Audit a tutor explanation

**Task:** Check whether an AI tutor's explanation was accurate and pedagogically sound

```text
Act as a veteran [SUBJECT] teacher and learning scientist reviewing an AI tutor transcript for a [GRADE] student working on [STANDARD, e.g. CCSS 7.RP.A.2]. Transcript: [PASTE]. Assess: (a) mathematical/factual accuracy, line by line; (b) whether the tutor scaffolded with questions or just gave away the answer; (c) tone and age-appropriateness; (d) the misconception the student likely holds. Output: a verdict (OK / minor issue / needs correction with the student), a list of specific errors with corrected wording, and a 3-sentence script I can use to follow up with the student in person. Say plainly if you are unsure about a point instead of guessing.
```

> **Caution:** Check Claude's corrections against the curriculum materials; one AI reviewing another can still miss errors.

## 3. Weekly report to teacher team

**Task:** Draft a concise weekly summary of AI tutor use and learning signals

```text
Draft a one-page weekly report from me, the AI tutor supervisor, to the [GRADE/DEPARTMENT] teaching team. Data: [PASTE AGGREGATE METRICS: usage minutes, completion rates, mastery checks, flagged sessions, tutor errors found]. Context: [UNIT BEING TAUGHT, ANY CHANGES TO TUTOR SETTINGS]. Structure: 3-bullet headline; what is working; concerns (tutor accuracy, equity of access, over-reliance); students needing teacher attention (by ID only); recommended adjustments for next week; open questions for teachers. Don't treat usage time as proof of learning, and point out where the data can't support a conclusion.
```

## 4. Parent communication about AI tutoring

**Task:** Write a clear, honest letter to families explaining how the AI tutor is used and supervised

```text
Write a letter to families of [GRADE] students at [SCHOOL] explaining our use of [TUTOR PLATFORM]. Cover: what the tutor does and doesn't do, that teachers remain responsible for instruction and grading, how I supervise sessions, what student data is collected and who sees it (based on: [PASTE VENDOR/DISTRICT DATA PRIVACY SUMMARY]), how families can opt out or review their child's data under FERPA, and who to contact with concerns. Reading level: about grade 6; under 400 words; warm, not salesy. Then provide a 5-question FAQ. Mark any claim you couldn't verify from what I gave you as [CONFIRM].
```

> **Caution:** Have district privacy/legal staff check the data-handling statements before sending; don't promise protections the vendor contract doesn't guarantee.

## 5. Vendor and deployment risk review

**Task:** Build a pre-adoption or renewal checklist for an AI tutor product

```text
I'm assessing [TUTOR PRODUCT] for [DISTRICT/SCHOOL, COUNTRY/STATE] for students aged [AGES]. Build a risk and compliance checklist drawing on FERPA, COPPA, [STATE STUDENT PRIVACY LAW, e.g. California SOPIPA], the US Department of Education's 2024 'Designing for Education with Artificial Intelligence' toolkit, the NIST AI RMF, and, if in the EU, the AI Act's Annex III high-risk education uses. Group items under: data privacy and retention, content safety and safeguarding, accuracy and evaluation evidence, bias and accessibility (including ELL and IEP students), human oversight and escalation, and contract terms. For each item give the question to ask the vendor and what a good answer looks like. Flag where rules are unsettled or vary by jurisdiction.
```

> **Caution:** This is a planning aid, not legal advice; final compliance calls belong to district counsel and the data protection officer.

## 6. Over-reliance intervention plan

**Task:** Design a plan for students who use the tutor to get answers rather than to learn

```text
Several students in my [GRADE/SUBJECT] class show over-reliance on the AI tutor: [DESCRIBE PATTERNS, e.g. rapid answer requests, copying outputs, low independent quiz scores vs high tutor completion]. Drawing on research on productive struggle, metacognition and help-seeking, propose a 3-week intervention plan that includes: tutor configuration changes I can request (if [PLATFORM] supports them), classroom routines such as tutor-free attempts first or explain-back checks, a short student reflection prompt, and how to measure whether it worked. Output as a week-by-week table plus a list of the evidence behind each step. Say where the evidence is weak or mixed.
```

## 7. Incident write-up

**Task:** Document an AI tutor incident (harmful, biased or badly wrong output) for escalation

```text
Help me write an incident report about an AI tutor problem. What happened: [DESCRIBE, with de-identified transcript excerpt]. Platform/version: [X]. Date and class context: [X]. Actions already taken: [X]. Produce a report with: summary, timeline, impact on the student(s), suspected cause (only labeled as a hypothesis), immediate containment, notifications made or needed (teacher, administrator, safeguarding lead, parents, vendor), and recommended follow-ups including what evidence to keep. Use neutral, factual language suitable for a district file. End with a checklist of anything missing that I should gather.
```

> **Caution:** If the incident involves possible harm, abuse disclosure or self-harm, follow your school's safeguarding protocol right away; the report comes second.

## 8. Upskilling plan for the role

**Task:** Build a personal learning plan for becoming an effective AI tutor supervisor

```text
I'm a [CURRENT BACKGROUND, e.g. paraeducator / former math teacher / ed-tech coordinator] moving into supervising AI tutors across [NUMBER] classrooms. Build a 12-week learning plan covering: how LLM tutors work and fail (hallucination, sycophancy, prompt injection), evaluating tutoring dialogue quality, learning science basics (retrieval practice, scaffolding, feedback), student data privacy law (FERPA, COPPA, my state's rules), reading learning-analytics dashboards critically, and AI literacy teaching (e.g. the ISTE Standards and the TeachAI toolkit). For each week: goal, 2-3 real resources (say if you're unsure a resource exists or is current), and a hands-on exercise using my own classroom. Finish with how I could show my competence to my principal.
```

> **Caution:** Verify every listed resource; ed-AI guidance changes fast and Claude may cite outdated or nonexistent material.
