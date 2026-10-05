---
name: memory-archivist-for-personal-digital-histories
description: "Prompt playbook for a memory archivist for personal digital histories. Use when a memory archivist for personal digital histories wants help with work tasks such as: collection intake assessment; preservation plan against NDSA Levels; metadata and description drafting; digital estate access memo; consent and sensitive-content review; format migration troubleshooting; life-story narrative from the archive; upskilling plan for an archivist."
---

# Memory archivist for personal digital histories prompts

Memory archivists help individuals, families and estates gather, preserve, describe and pass on scattered personal data (photos, messages, cloud accounts, voice notes, social media) using practices borrowed from professional digital preservation (NDSA Levels, OAIS, BagIt) and digital estate law (RUFADAA, platform legacy-contact tools). AI helps most with triaging huge messy collections, drafting metadata and narratives, planning preservation and access, and explaining consent, privacy and inheritance questions to families, while the archivist keeps responsibility for authenticity, consent and what gets kept or destroyed.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Collection intake assessment

**Task:** Scope a new client's scattered digital life into an intake plan

```text
You are assisting a personal digital archivist doing intake for a new client. Client situation: [LIVING CLIENT / ESTATE / FAMILY]. Known sources: [LIST, e.g. iPhone photos, iCloud, Gmail, Facebook, old hard drives, WhatsApp, CDs]. Approximate volume: [GB/ITEMS]. Client goals: [e.g. family history book, preservation before account closure, sharing with grandchildren]. Produce: 1) a source inventory table (source, likely export method such as Google Takeout or Apple data-and-privacy download, format risks, access credentials needed, urgency), 2) the top 5 risks of loss (dormant-account deletion, failing media, proprietary formats), 3) questions I must ask the client before touching anything, especially about consent from other people in the data. Flag anything that depends on platform policies that may have changed.
```

> **Caution:** Verify current platform export and inactive-account policies directly; they change often.

## 2. Preservation plan against NDSA Levels

**Task:** Design a storage and fixity plan sized to a family budget

```text
Act as a digital preservation consultant. Using the NDSA Levels of Digital Preservation (storage, integrity, control, metadata, content) as the framework, draft a preservation plan for a personal archive of [SIZE] containing [CONTENT TYPES, e.g. HEIC photos, MP4 video, PDFs, SMS exports]. Budget: [AMOUNT/YEAR]. Technical comfort of the long-term custodian: [LOW/MEDIUM/HIGH]. Output: a table showing which NDSA level each area reaches, the concrete setup (e.g. 3 copies, geographic separation, BagIt packaging with checksums, scheduled fixity checks), recommended preservation formats for each content type with tradeoffs, and a one-page annual maintenance checklist the family can follow without me. Note where your recommendation is a judgment call.
```

## 3. Metadata and description drafting

**Task:** Turn messy file names and EXIF data into consistent descriptive records

```text
You are helping me catalog a personal photo and document collection. Below is a sample of file records with names, dates, EXIF/GPS fields and any client notes: [PASTE CSV OR LIST]. Using a simple Dublin Core-based schema (title, date, creator, subject, coverage/place, description, rights, source), propose a description for each item. Rules: never invent names, places or events; mark any inference (e.g. date guessed from camera model or a GPS lookup) with [INFERRED: reason]; list items whose dates look wrong (camera clock defaults, timezone shifts, scanned-date vs. original-date). Return a CSV ready to import into [TOOL, e.g. digiKam, Tropy, spreadsheet], plus a short list of questions for the family to confirm identities.
```

> **Caution:** Do not paste identifiable data of third parties without client consent; confirm all identifications with family members.

## 4. Digital estate access memo

**Task:** Explain legal and platform options for accessing a deceased person's accounts

```text
You are helping a memory archivist write a plain-language memo for an executor. Deceased's jurisdiction: [STATE/COUNTRY]. Accounts involved: [e.g. Apple ID, Google, Facebook, Instagram, email at a small ISP, password manager]. Known arrangements: [e.g. Apple Legacy Contact set, Google Inactive Account Manager, none, will mentions digital assets]. Explain, for each account, the likely route to access or download content (platform legacy tools, memorialization, court order) and how laws such as the US RUFADAA (as adopted in that state) or the relevant national rules bear on it. Output a table plus a step-by-step action list. Clearly separate what you are confident about from what the executor must confirm with a lawyer or the platform.
```

> **Caution:** Not legal advice; laws vary by jurisdiction and platforms update procedures. Never help bypass account security without lawful authority.

## 5. Consent and sensitive-content review

**Task:** Decide what to restrict, redact or exclude before sharing an archive

```text
Act as an ethics and privacy reviewer for a family digital archive about to be shared with [AUDIENCE, e.g. extended family, a local history society, public website]. Collection summary: [DESCRIBE, including types of private messages, medical or financial records, photos of minors, third parties]. Living people affected: [LIST ROLES, not full details]. Produce a review framework: categories of material to restrict, redact, embargo (with suggested time periods) or exclude; who must give consent for each category; how privacy law such as GDPR or [LOCAL LAW] might apply to living third parties; and a draft access-policy paragraph. Flag dilemmas where family wishes may conflict with a third party's privacy and describe options rather than deciding them.
```

> **Caution:** Final keep/restrict decisions belong to the client and archivist; get legal input for public release.

## 6. Format migration troubleshooting

**Task:** Rescue obsolete or unreadable files from old media

```text
You are a digital forensics and preservation technician advising me. I have recovered files from [MEDIA, e.g. 2003 Zip disk, old Palm PDA backup, MiniDV tapes, a Windows XP drive]. File identification results from [DROID/Siegfried/file command]: [PASTE OUTPUT]. Problems: [e.g. unknown extensions, files that won't open, corrupt headers]. For each problem file type, suggest: likely original application, open-source tools to read or convert it (e.g. LibreOffice, ffmpeg, ImageMagick, ExifTool), a target preservation format, and how to verify nothing was lost (checksums of originals, visual comparison, metadata carry-over). Always keep originals untouched; write the plan as an ordered checklist.
```

> **Caution:** Work on disk images or copies, never the only original media.

## 7. Life-story narrative from the archive

**Task:** Draft a biographical narrative or exhibit text grounded in sourced items

```text
You are helping me write a [FORMAT, e.g. 2,000-word family history chapter / captions for an immersive memorial exhibit / timeline for a VR memory space] about [PERSON] based only on these archive items and family interviews: [PASTE ITEM DESCRIPTIONS WITH IDs AND INTERVIEW NOTES]. Requirements: cite the item ID after every factual claim; where sources conflict, show both versions; mark anything you are inferring; do not invent dialogue, feelings or events. Tone: [e.g. warm, plain, celebratory]. After the draft, list gaps in the record that the family could fill with more interviews or documents.
```

> **Caution:** Avoid generating synthetic voices, images or chatbot personas of real people without explicit consent from the person or their estate.

## 8. Upskilling plan for an archivist

**Task:** Build a learning path from photo organizer to professional digital archivist

```text
I am a [CURRENT BACKGROUND, e.g. professional photo organizer / genealogist / IT generalist] moving into personal digital archiving. I have [HOURS/WEEK] for [MONTHS]. Build a learning plan covering: preservation fundamentals (OAIS reference model, NDSA Levels, PREMIS basics, BagIt), file format identification and migration, metadata standards, provenance and authenticity (including C2PA content credentials and spotting AI-generated or altered media), digital estate law basics, privacy and ethics of archiving others' data, and running a client business. For each module give learning goals, free or low-cost resources such as Library of Congress personal digital archiving guidance and Digital Preservation Coalition materials, a hands-on practice exercise, and how I'd show competence. Note any certifications that exist and where the field lacks formal credentials.
```

> **Caution:** Check that resources and certifications are current before paying for any.
