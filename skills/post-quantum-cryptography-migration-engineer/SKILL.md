---
name: post-quantum-cryptography-migration-engineer
description: "Prompt playbook for a post-quantum cryptography migration engineer. Use when a post-quantum cryptography migration engineer wants help with work tasks such as: triage a cryptographic inventory; find crypto dependencies in code; plan a hybrid TLS rollout; troubleshoot a PQC interop failure; draft a vendor PQC questionnaire; compliance timeline map; executive briefing on quantum risk; upskilling study plan."
---

# Post-quantum cryptography migration engineer prompts

Engineers who inventory an organization's cryptography and move it to NIST's post-quantum standards (FIPS 203 ML-KEM, FIPS 204 ML-DSA, FIPS 205 SLH-DSA) on deadlines set by NSA CNSA 2.0, NIST IR 8547, OMB M-23-02 and the EU and UK NCSC roadmaps. AI helps most with triaging large crypto inventories, reading code and configs for crypto dependencies, drafting migration plans and vendor questionnaires, and explaining quantum risk to executives.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Triage a cryptographic inventory

**Task:** Turn raw scan output into a prioritized quantum-risk inventory

```text
You are a post-quantum migration engineer. Below is raw cryptographic discovery output from [TOOL, e.g. CBOM scan, TLS scanner, code grep] covering [SYSTEM SCOPE]. Normalize it into a table with columns: asset, protocol/library, algorithm and key size, purpose (key exchange, signature, encryption at rest), quantum-vulnerable (yes/no/partial), data confidentiality lifetime, owner if known. Then rank assets using Mosca's inequality (shelf-life + migration time vs. time to a cryptographically relevant quantum computer), using [ASSUMED CRQC YEAR RANGE] as an explicit assumption. Flag entries where the data is ambiguous instead of guessing. Data: [PASTE SCAN OUTPUT]
```

> **Caution:** Scan output can contain hostnames and internal details; sanitize before pasting and confirm ranking with system owners.

## 2. Find crypto dependencies in code

**Task:** Locate hard-coded classical crypto and assess crypto agility in a codebase

```text
Act as a code reviewer focused on crypto agility. Review this [LANGUAGE] code from [SERVICE NAME], which uses [LIBRARIES, e.g. OpenSSL 3.x, BouncyCastle, Go crypto]. Identify every use of RSA, ECDSA, ECDH, DH, or Ed25519, including indirect ones via certificates, JWTs, or SSH. For each, give file/line, purpose, and whether the algorithm choice is hard-coded or configurable. Suggest refactors that centralize algorithm selection so ML-KEM/ML-DSA (FIPS 203/204) can be swapped in, and note assumptions about key/signature sizes (buffers, DB columns, packet MTUs) that will break with larger PQC artifacts. Output: findings table, then refactor plan. Code: [PASTE CODE]
```

> **Caution:** Do not paste private keys or secrets; have a cryptographer review any change to primitives.

## 3. Plan a hybrid TLS rollout

**Task:** Design a staged rollout of hybrid post-quantum key exchange

```text
I need to enable hybrid post-quantum key exchange (e.g. X25519MLKEM768) for [TRAFFIC TYPE] across [ENVIRONMENT: load balancers, CDNs, service mesh, clients]. Current stack: [VERSIONS OF OPENSSL/BORINGSSL, PROXIES, CLIENT PLATFORMS]. Produce a staged rollout plan: prerequisite version upgrades, canary scope, metrics to watch (handshake failures, ClientHello size/fragmentation, middlebox drops, latency), rollback triggers, and a compatibility matrix for clients that don't support the hybrid group. Mark which IETF documents are RFCs vs. still drafts as of your knowledge, and flag anything I should verify against current vendor docs.
```

> **Caution:** Codepoints and library support change quickly; verify against current IETF and vendor documentation before production.

## 4. Troubleshoot a PQC interop failure

**Task:** Diagnose handshake or signature failures after enabling PQC algorithms

```text
You are helping debug a post-quantum interoperability issue. After enabling [ALGORITHM/GROUP, e.g. ML-KEM-768 hybrid, ML-DSA-65 certs] on [COMPONENT], we see [SYMPTOM: handshake timeouts, alert codes, verification errors] between [CLIENT] and [SERVER]. Versions: [LIBRARY AND OS VERSIONS]. Logs/packet summary: [PASTE]. List the most likely causes ranked by probability (e.g. oversized ClientHello split across packets, middlebox intolerance, OID or codepoint mismatch between draft and final versions, HSM firmware lacking support), the specific test to confirm each, and the fix. Say when the evidence is insufficient to decide.
```

> **Caution:** Redact IPs, certificates' subject details and session data as needed before sharing logs.

## 5. Draft a vendor PQC questionnaire

**Task:** Assess third-party products' post-quantum readiness

```text
Draft a vendor questionnaire assessing post-quantum readiness for suppliers of [PRODUCT CATEGORY, e.g. HSMs, VPNs, PKI, IoT devices] at a [SECTOR] organization subject to [REQUIREMENTS, e.g. CNSA 2.0, FIPS 140-3, EU PQC roadmap, DORA]. Cover: algorithms supported (FIPS 203/204/205 and parameter sets), FIPS 140-3/CMVP validation status, hybrid modes, firmware update path for deployed units, roadmap dates, cryptographic bill of materials (CycloneDX CBOM) availability, and end-of-life of classical-only products. For each question, give the answer that would count as acceptable vs. a red flag. Output as a table I can send.
```

> **Caution:** Vendor roadmaps are not commitments; get dates into contracts where they matter.

## 6. Compliance timeline map

**Task:** Map applicable PQC mandates to internal migration milestones

```text
I'm planning PQC migration for [ORGANIZATION TYPE] operating in [JURISDICTIONS] with [SYSTEM TYPES, e.g. national security systems, payment systems, federal contracts]. Summarize which guidance likely applies (e.g. NSA CNSA 2.0, NIST IR 8547 deprecation/disallowance of quantum-vulnerable algorithms, OMB M-23-02 inventory reporting, EU coordinated PQC roadmap, UK NCSC migration timelines, PCI DSS) and its key dates. Map them onto a milestone plan for our [SYSTEM LIST]. Clearly separate binding requirements from recommendations, note where documents are drafts or may have been updated since your training, and list questions for our legal/compliance team.
```

> **Caution:** Not legal advice; confirm current text of each mandate with compliance counsel.

## 7. Executive briefing on quantum risk

**Task:** Explain harvest-now-decrypt-later risk and the migration budget to leadership

```text
Write a one-page briefing for [AUDIENCE, e.g. CISO and board risk committee] at [ORGANIZATION] explaining why we need funding of [AMOUNT/RESOURCES] for post-quantum migration. Explain 'harvest now, decrypt later' in plain language, using our longest-lived sensitive data ([DATA TYPES AND RETENTION]) as the example. Present the uncertainty about when a cryptographically relevant quantum computer arrives honestly, with no hype or specific predicted dates presented as fact. Include: current exposure summary [PASTE KEY INVENTORY STATS], regulatory deadlines, three-phase plan, and the cost of delay. End with the decision we need from them.
```

> **Caution:** Avoid overstating quantum timelines; credibility with leadership matters for a multi-year program.

## 8. Upskilling study plan

**Task:** Build a learning path on lattice-based crypto and PQC engineering

```text
I'm a [CURRENT ROLE, e.g. PKI engineer, backend developer] with [BACKGROUND IN MATH/CRYPTO] and want to become competent as a post-quantum migration engineer in [TIME AVAILABLE]. Create a week-by-week study plan covering: why Shor's algorithm breaks RSA/ECC, lattice basics behind ML-KEM and ML-DSA, hash-based signatures (SLH-DSA, LMS/XMSS state management), reading FIPS 203/204/205, hands-on labs with OpenSSL 3.5+ and Open Quantum Safe liboqs, side-channel and implementation pitfalls, and crypto-agility architecture. For each week give goals, primary sources, a practical exercise, and a self-check question. Flag topics where the field is still moving.
```

> **Caution:** Use liboqs and experimental builds for learning and testing, not as validated production crypto.
