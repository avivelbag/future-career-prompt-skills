---
name: smart-contract-auditor
description: "Prompt playbook for a smart contract auditor. Use when a smart contract auditor wants help with work tasks such as: audit scoping and threat model; triage static analysis output; invariant and fuzz test design; write a finding report entry; fix review and diff audit; executive summary for non-technical stakeholders; responsible disclosure of a live bug; upskilling plan for a new ecosystem."
---

# Smart contract auditor prompts

Smart contract auditors review blockchain code (mostly Solidity, Vyper, Rust and Move) for vulnerabilities before deployment and upgrades. They work at audit firms such as Trail of Bits, OpenZeppelin and Spearbit, on contest platforms such as Code4rena, Sherlock and Cantina, or inside protocols, and the role is growing as tokenized assets come under rules like the EU's MiCA. Claude helps most with scoping, threat modeling, invariant and fuzz test design, triaging static-analysis output, and writing clear findings and disclosures. The auditor still owns every severity call and the sign-off.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Audit scoping and threat model

**Task:** Turn a new engagement's codebase into a scoped threat model before line-by-line review

```text
Act as a senior smart contract auditor starting an engagement. The protocol is [PROTOCOL TYPE, e.g. lending market / AMM / bridge], deployed on [CHAIN(S)], with these contracts in scope: [LIST WITH nSLOC]. External dependencies: [ORACLES, TOKENS, LIBRARIES]. Privileged roles: [ROLES AND WHAT THEY CAN DO]. Produce: 1) a trust-boundary map in prose, 2) a table of assets at risk, attacker types and entry points, 3) the 10 highest-priority attack hypotheses (e.g. oracle manipulation, reentrancy, rounding, access control, upgrade storage collisions), each with the files to check first, 4) questions to send the client before review starts. Mark any assumption you are making.
```

> **Caution:** This model only gives you hypotheses to test. It doesn't replace manual review of every in-scope line.

## 2. Triage static analysis output

**Task:** Separate true positives from noise in Slither/Aderyn results

```text
I ran [Slither / Aderyn / Semgrep rules] on [REPO OR COMMIT]. The output is below, along with the relevant code excerpts. For each finding, classify it as likely true positive, likely false positive, or needs manual check. Give a one-line reason that refers to the actual code path, and map it to an OWASP Smart Contract Top 10 or SWC category where one fits. Group duplicates. End with a short list of detector gaps: classes of bug these tools typically miss for a [PROTOCOL TYPE] that I should hunt for manually. Output as a table plus that list. Say when you can't tell without seeing more code.

[PASTE TOOL OUTPUT]
[PASTE CODE EXCERPTS]
```

> **Caution:** Confirm every classification yourself. Don't dismiss a finding just because the model called it a false positive.

## 3. Invariant and fuzz test design

**Task:** Write property and invariant tests to prove or disprove a suspected bug

```text
You are helping me write tests for an audit. The contract is [CONTRACT NAME], its purpose is [SHORT DESCRIPTION], and the key state variables are [LIST]. My suspicion: [DESCRIBE SUSPECTED ISSUE]. Write: 1) the protocol invariants in plain English, e.g. 'sum of user balances <= totalAssets', 2) a Foundry invariant test suite with a handler contract that bounds inputs realistically, 3) an equivalent Echidna or Medusa property if it adds value, 4) a minimal Foundry proof-of-concept unit test for the suspected issue against a local fork or mock, never mainnet state transactions. Explain what a failing run would show and how to shrink it.
```

> **Caution:** Run PoCs only in local or forked test environments. Never send exploit transactions to live contracts.

## 4. Write a finding report entry

**Task:** Turn raw notes into a client-ready vulnerability write-up

```text
Draft an audit finding from my notes, written in the style of a professional audit report (e.g. Trail of Bits, Spearbit). Sections: Title; Severity with Impact and Likelihood justified separately using [CLIENT'S / PLATFORM'S SEVERITY MATRIX, e.g. Code4rena, Sherlock or Immunefi classification]; Affected code (file:line); Description; Exploit scenario as numbered steps with a concrete attacker; Proof of concept reference; Recommendation with a code diff; Notes on fix verification. Keep it precise and free of hype. If my notes don't support the severity I proposed, say so.

Notes: [PASTE NOTES, CODE SNIPPET, POC RESULT]
```

> **Caution:** You decide the final severity. Clients and contest judges will challenge inflated severities.

## 5. Fix review and diff audit

**Task:** Verify remediation commits don't fix one bug and introduce another

```text
Act as an auditor doing fix review. The original finding is [PASTE FINDING], and the remediation diff between [OLD COMMIT] and [NEW COMMIT] is below. Assess: 1) does the fix fully address the root cause or only the specific PoC path, 2) any new issues introduced, e.g. changed storage layout in an upgradeable proxy, broken invariants, new external calls, gas griefing, 3) code paths elsewhere with the same pattern that also need fixing, 4) which tests should be added. Output a status (Fixed / Partially fixed / Not fixed / New issue) with reasoning, plus a short list of follow-up questions for the developers.

[PASTE DIFF]
```

> **Caution:** Re-run the full test and fuzz suite on the final commit. Your sign-off should cover the deployed bytecode, not only the diff.

## 6. Executive summary for non-technical stakeholders

**Task:** Explain audit results to founders, investors, governance voters or compliance teams

```text
Write an executive summary of the audit of [PROTOCOL NAME] at commit [HASH] for [AUDIENCE, e.g. DAO token holders / board / compliance team]. Inputs: findings by severity [COUNTS AND ONE-LINE DESCRIPTIONS], fix status [STATUS], scope and exclusions [SCOPE]. Cover: what was reviewed and what wasn't (off-chain components, oracles, admin key management, economic design), the main risk themes in plain language, residual risks and centralization assumptions, and what an audit does not guarantee. Under 400 words, no jargon without a gloss. Avoid any phrasing that could be read as 'certified secure' or as investment advice.
```

> **Caution:** Audits are often misquoted in marketing. Keep the scope limits and disclaimers explicit.

## 7. Responsible disclosure of a live bug

**Task:** Plan disclosure when a vulnerability affects already-deployed contracts

```text
I found what appears to be a [SEVERITY] vulnerability in live contracts of [PROTOCOL] on [CHAIN], with roughly [TVL AT RISK] at risk. The protocol [HAS / DOES NOT HAVE] a bug bounty on [PLATFORM, e.g. Immunefi] and [HAS / HAS NOT] adopted the SEAL Safe Harbor agreement. Help me plan responsible disclosure: who to contact first and through which private channels (security contact, bounty platform, SEAL 911), what minimal information to share at first, a draft initial message, and the steps to take if I get no response within [TIMEFRAME]. Flag legal uncertainties for my jurisdiction [JURISDICTION] that I should take to a lawyer. Don't describe exploit execution steps.
```

> **Caution:** Never exploit or whitehat-rescue funds yourself without explicit safe-harbor coverage and legal advice. Keep exploit details private until the bug is fixed.

## 8. Upskilling plan for a new ecosystem

**Task:** Ramp up on a new language or chain and on emerging compliance expectations

```text
I'm an auditor experienced in [CURRENT STACK, e.g. Solidity/EVM] and need to audit [NEW STACK, e.g. Move on Sui/Aptos, Rust on Solana, ZK circuits in Circom/Noir] within [WEEKS]. Build a study plan: the key execution-model differences and the bug classes unique to the new stack (e.g. account validation on Solana, under-constrained circuits in ZK); public past audit reports and post-mortems to study; tooling to learn (fuzzers, formal tools such as Certora or Halmos where applicable); and a hands-on exercise each week. Add a short section on how regulation such as EU MiCA, the EU Data Act's smart contract provisions and standards like EEA EthTrust Security Levels may shape audit expectations, and flag where these are still unsettled.
```

> **Caution:** Tooling and regulation change fast. Check that the resources and rules cited are still current.
