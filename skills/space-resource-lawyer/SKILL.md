---
name: space-resource-lawyer
description: "Prompt playbook for a space resource lawyer. Use when a space resource lawyer wants help with work tasks such as: jurisdiction comparison for a resource mission; article II non-appropriation risk memo; mission authorization gap analysis; offtake and resource sale contract clauses; policy and treaty development tracker; investor due diligence on resource rights; plain-language explainer for non-lawyers; upskilling study plan."
---

# Space resource lawyer prompts

Advises lunar and asteroid mining startups, space agencies, investors and insurers on the right to extract and own resources in space, under the Outer Space Treaty, national laws (US CSLCA 2015, Luxembourg 2017, UAE 2019, Japan 2021), the Artemis Accords and the UN COPUOS rules still being drafted. Claude helps most with comparing jurisdictions, drafting contract and authorization documents, tracking the changing rules, and turning unsettled law into clear risk memos. A licensed lawyer stays responsible for every conclusion.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Jurisdiction comparison for a resource mission

**Task:** Choose where to license and incorporate a space resource venture

```text
You are a space law research assistant. My client, [COMPANY DESCRIPTION], plans to [ACTIVITY, e.g. extract and sell lunar regolith-derived oxygen] around [TIMEFRAME]. Compare the US Commercial Space Launch Competitiveness Act 2015 (51 U.S.C. 51303), Luxembourg's 2017 Law on the Exploration and Use of Space Resources, the UAE's 2019 Federal Law No. 12 and Japan's 2021 Space Resources Act. Make a table with: who qualifies, the licensing authority, what property rights are granted, ongoing supervision duties, liability and insurance requirements, and how each fits Outer Space Treaty Articles II and VI. Then list open questions and anything you are unsure about, and mark which statements need checking against the primary text.
```

> **Caution:** Check every citation against current primary sources; national rules and agency practice change, and this is research, not legal advice.

## 2. Article II non-appropriation risk memo

**Task:** Assess whether a planned activity could be challenged as national appropriation

```text
Act as a senior space law associate. Draft a 2-page internal memo on whether [ACTIVITY, e.g. a 5-year exclusive operating zone around a lunar south pole ice deposit] could be seen as 'national appropriation' under Outer Space Treaty Article II. Cover: the main academic positions, Artemis Accords Section 10 and Section 11 safety zones, the Hague International Space Resources Governance Working Group Building Blocks (2019), the Moon Agreement and which states are parties, and where the UN COPUOS Legal Subcommittee working group on space resources stands now. Use this structure: Question, Short Answer, Analysis, Counterarguments, Mitigations, Open Issues. Say clearly where the law is unsettled rather than guessing.
```

> **Caution:** Experts genuinely disagree here; present it as an assessment of risk, not a settled answer.

## 3. Mission authorization gap analysis

**Task:** Map which US agencies must approve a novel lunar resource mission

```text
You are helping a US space startup's general counsel. Mission: [MISSION PROFILE: launch vehicle, lander, rover, payloads, extraction method, comms, imaging]. Identify every US approval it likely needs: FAA/AST launch and reentry (14 CFR Part 450) and the payload review, FCC spectrum licensing, NOAA commercial remote sensing (if it carries cameras), and ITAR/EAR export controls. Then explain the 'mission authorization' gap for activities like surface mining that no agency currently supervises under OST Article VI, and summarise current legislative or executive proposals, noting their status as of your knowledge cutoff. Output a checklist table (approval, agency, trigger, lead time, notes) plus a list of gaps.
```

> **Caution:** Rules and proposals change quickly; confirm the current status with each agency and recent Federal Register notices.

## 4. Offtake and resource sale contract clauses

**Task:** Draft key clauses for selling extracted space resources

```text
Act as a commercial contracts lawyer who specialises in space. Draft key clauses for an offtake agreement where [SELLER] will deliver [QUANTITY] of [RESOURCE, e.g. water ice or propellant] to [BUYER] at [DELIVERY POINT, e.g. a cislunar propellant depot] by [DATE]. Include: title transfer and when it happens, a warranty of title that relies on [LICENSING JURISDICTION]'s law, delivery and acceptance testing, force majeure for launch failure and space weather, allocation of liability under the 1972 Liability Convention, the insurance required, export control compliance, governing law and arbitration (e.g. PCA Optional Rules for Arbitration of Disputes Relating to Outer Space Activities). Add a drafting note under each clause about its risks.
```

> **Caution:** These are drafting starting points; a qualified lawyer must adapt them to the deal and the governing law.

## 5. Policy and treaty development tracker

**Task:** Summarise new developments for a monthly client briefing

```text
You are a space policy analyst. Below are [NUMBER] source excerpts I collected this month: [PASTE TEXT: COPUOS reports, new Artemis Accords signatories, national bills, agency notices]. Write a client briefing of no more than 600 words with: (1) the 3 developments that matter most to space resource companies and why, (2) a table of the remaining items (date, body, development, relevance from high to low), (3) what to watch next quarter. Use only the excerpts I gave you; if something is ambiguous, or you need context they do not contain, list it under 'Needs verification' rather than filling the gap.
```

> **Caution:** Claude's knowledge has a cutoff; base briefings on current sources you supply.

## 6. Investor due diligence on resource rights

**Task:** Review a startup's legal basis for resource claims before investment

```text
Act as legal due diligence counsel for [INVESTOR] considering a [AMOUNT] investment in [TARGET COMPANY], which says it has the right to [RESOURCE CLAIM AS STATED IN THE PITCH DECK]. Using the materials below, [PASTE: corporate structure, licences held or applied for, mission plans, key contracts], write a red-flag report covering: whether the claimed rights exist under the relevant national law and international law, which approvals are still missing, how exposed the company is to export control and sanctions, liability and insurance, IP for extraction technology, and how the company's claims may be overstated. Rate each item Red/Amber/Green, with reasons and follow-up questions for management.
```

> **Caution:** Diligence findings need sign-off from counsel; don't rely on statements in the target's own materials without checking them.

## 7. Plain-language explainer for non-lawyers

**Task:** Explain space resource ownership to engineers, the board or the public

```text
You are a space lawyer who explains things clearly. Write a [FORMAT: one-page FAQ / 5-minute talk / board briefing] for [AUDIENCE] on 'Can a company own what it mines on the Moon or an asteroid?' Cover: the difference between owning territory and owning extracted resources, what the Outer Space Treaty, national laws and the Artemis Accords say, why some countries disagree (for example the Moon Agreement parties and positions at COPUOS), and what this means for [CLIENT CONTEXT]. Avoid jargon, use one concrete example, and end with 'What's still undecided'. Don't overstate how certain the law is.
```

> **Caution:** Keep public statements consistent with the client's formal legal positions; have the final text reviewed.

## 8. Upskilling study plan

**Task:** Build a study plan to move into space resource law

```text
I'm a [CURRENT ROLE, e.g. mining or energy lawyer with 6 years' experience] and want to become a credible space resource lawyer within [TIMEFRAME]. Make a 12-week study plan covering: the five UN space treaties, national space resource laws, the Artemis Accords, the Hague Building Blocks, US licensing (FAA, FCC, NOAA, ITAR/EAR), liability and insurance, and how dispute resolution works in practice. For each week give learning goals, primary sources to read (real documents only, cited by name, no invented links), one practice exercise, and 3 self-test questions. Also suggest real organisations, courses and moot competitions (e.g. IISL Manfred Lachs Space Law Moot Court) to join. Flag anything you are not sure is still running.
```

> **Caution:** Check that courses, programmes and events are still running before you sign up.
