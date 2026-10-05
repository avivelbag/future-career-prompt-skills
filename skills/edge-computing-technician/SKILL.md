---
name: edge-computing-technician
description: "Prompt playbook for an edge computing technician. Use when an edge computing technician wants help with work tasks such as: remote node fault triage; site install runbook; fleet firmware rollout plan; oT security hardening checklist; incident report for site outage; explain an outage to a site owner; capacity and thermal sizing; upskilling study plan."
---

# Edge computing technician prompts

Edge computing technicians install, harden and maintain the small compute nodes that run outside central data centers: telco MEC sites, retail and factory servers, cell-tower micro data centers and rugged gateways (AWS Outposts, Azure Stack Edge, NVIDIA Jetson, K3s/KubeEdge clusters). Claude helps most with triaging logs and telemetry from remote sites, writing site runbooks and change records, planning fleet rollouts, and mapping work to standards such as IEC 62443, NIST SP 800-82 and ASHRAE thermal guidelines.

## How to use

Find the task below that matches the request. Treat its prompt as the brief: ask the user for any [BRACKETED] details that aren't already in the conversation, then do the work it describes. Respect each caution. This is an emerging role, so check standards, regulations and products named here against current sources. Professional judgment, sign-off and anything regulated stays with the user.

## 1. Remote node fault triage

**Task:** Diagnose a misbehaving edge node from logs before rolling a truck

```text
You are a senior edge infrastructure engineer helping me triage a remote site. Node: [HARDWARE MODEL, e.g. Dell XR4000 / Jetson Orin / Azure Stack Edge], running [OS + ORCHESTRATOR, e.g. Ubuntu 22.04 + K3s 1.29]. Location: [SITE TYPE, e.g. cell tower cabinet, store back room]. Symptoms: [SYMPTOMS + WHEN STARTED]. Logs/telemetry pasted below: [DMESG / JOURNALCTL / KUBECTL DESCRIBE / IPMI SEL / TEMPS]. Give me: (1) a ranked list of likely root causes with the evidence for each, (2) the next remote commands to run to confirm or rule out each one, ordered from least to most disruptive, (3) whether a site visit is needed and what parts or tools to bring. Flag anything that looks like a security incident rather than a fault.
```

> **Caution:** Check every command before running it on production nodes; prefer read-only diagnostics first and follow your change-control process.

## 2. Site install runbook

**Task:** Write a step-by-step install and commissioning runbook for a new edge site

```text
Act as an edge deployment lead writing a field runbook for technicians. Site: [SITE TYPE + ADDRESS CLASS, e.g. rural tower shelter]. Equipment: [RACK/ENCLOSURE, SERVERS, SWITCH, UPS, CELLULAR/FIBER BACKHAUL]. Power and cooling available: [CIRCUITS, AMPS, HVAC OR FAN-ONLY, AMBIENT RANGE]. Target platform: [e.g. K3s cluster managed by Rancher / AWS Outposts server / Google Distributed Cloud Edge]. Write the runbook as numbered steps grouped into pre-visit checks, physical install, power-on and BIOS/BMC hardening, network bring-up, zero-touch provisioning, acceptance tests, and handoff. For each step include the pass/fail check and the photo or reading to record. Note where ASHRAE TC 9.9 thermal ranges, local electrical code, or the vendor's install guide govern, and leave [VENDOR SPEC] placeholders where you are not certain of figures.
```

> **Caution:** Electrical work must be done by qualified, licensed personnel per local code (e.g. NEC/NFPA 70 in the US); verify all figures against vendor documentation.

## 3. Fleet firmware rollout plan

**Task:** Plan a staged firmware/OS update across hundreds of edge nodes

```text
You are an SRE planning a staged update across an edge fleet. Fleet: [NUMBER] nodes across [NUMBER] sites, hardware mix [MODELS], connectivity [e.g. LTE with 50 GB/month caps at 30% of sites]. Update: [BIOS/BMC/OS/K8S VERSION FROM -> TO], reason: [CVE / FEATURE]. Constraints: [MAINTENANCE WINDOWS, SITES WITH NO ON-SITE STAFF, SLA]. Produce a rollout plan as a table of waves (canary, early, broad) with site selection criteria, success metrics and automatic halt conditions, plus a rollback procedure for a node that fails to boot remotely (A/B partitions, out-of-band BMC access, or truck roll). Cite NIST SP 800-193 firmware resilience principles where relevant and list open risks I should resolve before wave 1.
```

> **Caution:** Test on identical hardware in a lab first; a bricked remote node may mean an expensive site visit.

## 4. OT security hardening checklist

**Task:** Map an industrial edge gateway's configuration to IEC 62443 and NIST SP 800-82

```text
Act as an OT security specialist. I'm hardening an edge gateway at a [FACTORY / WATER UTILITY / SUBSTATION] that bridges [PLC/SCADA PROTOCOLS, e.g. Modbus TCP, OPC UA] to [CLOUD/IT DESTINATION]. Current config summary: [FIREWALL RULES, USER ACCOUNTS, REMOTE ACCESS METHOD, PATCH STATUS, LOGGING]. Target security level: [IEC 62443 SL1-SL4 or unknown]. Produce a checklist table with columns: control, current state, gap, recommended fix, IEC 62443-3-3 requirement or NIST SP 800-82 Rev. 3 section it maps to, and effort. Then list the top 5 fixes by risk reduction. Say clearly where you are unsure of a clause number so I can check the standard.
```

> **Caution:** Clause references must be verified against the licensed standard; never change OT network config without the plant owner's approval and a safety review.

## 5. Incident report for site outage

**Task:** Turn raw notes from an edge outage into a blameless post-incident report

```text
You are helping me write a blameless post-incident review. Incident: [SHORT DESCRIPTION] at [SITE(S)], from [START] to [END]. Business impact: [e.g. 40 stores lost POS offline-mode sync, video analytics down]. My raw timeline and notes: [PASTE NOTES, CHAT LOGS, ALERTS]. Write the report with sections: summary, impact, timeline (UTC), detection, root cause and contributing factors, what went well, what went poorly, and action items (owner placeholder, due date placeholder, priority). Keep it factual and non-blaming, and list any gaps in my notes I should fill before publishing. If the incident may involve a breach of personal data or an essential service, note that NIS2, GDPR or sector rules may impose reporting deadlines I should confirm with legal.
```

> **Caution:** Legal and regulatory reporting decisions belong to your security/legal team, not this draft.

## 6. Explain an outage to a site owner

**Task:** Write a plain-language update for a non-technical customer or landlord

```text
Act as a field service lead writing to a non-technical stakeholder. Recipient: [ROLE, e.g. store manager, tower landlord, hospital facilities manager]. What happened: [TECHNICAL SUMMARY]. What we need from them: [e.g. access on DATE, power shutdown approval, moving boxes away from the cabinet vents]. Current status and ETA: [STATUS]. Write a short email (under 200 words) in plain language with no jargon, a clear ask with a deadline, and a contact line. Then give me a two-sentence version for a text message. Do not promise a fix time I haven't given you.
```

## 7. Capacity and thermal sizing

**Task:** Check whether a planned AI inference workload fits an edge site's power and cooling

```text
You are an edge infrastructure planner. A team wants to deploy [WORKLOAD, e.g. 8 camera streams of object detection] on [HARDWARE, e.g. 2x servers with NVIDIA L4 GPUs] at a site with [AVAILABLE POWER IN W/A AND VOLTAGE], [UPS CAPACITY AND RUNTIME], [COOLING: HVAC TONNAGE OR SEALED ENCLOSURE WITH HEAT EXCHANGER], and ambient [MIN-MAX TEMP]. Using the vendor TDP figures I provide here: [FIGURES], estimate peak and typical power draw, heat load in BTU/hr, UPS runtime at load, and headroom. Present a short table plus a go/no-go recommendation with the assumptions you made. Flag any figure you had to assume and what measurement on site would confirm it.
```

> **Caution:** Estimates are not a substitute for measured load and a qualified electrical/HVAC assessment.

## 8. Upskilling study plan

**Task:** Build a learning plan to move from IT field tech to edge/Kubernetes technician

```text
Act as a career mentor for infrastructure technicians. My background: [CURRENT ROLE, YEARS, SKILLS, e.g. CompTIA A+, rack and stack, basic Linux]. Goal role: edge computing technician working with [PLATFORMS, e.g. K3s, Azure Arc, Jetson, 5G private networks]. Time available: [HOURS/WEEK] for [MONTHS]. Build a week-by-week plan covering Linux, networking, containers and Kubernetes, out-of-band management (Redfish/IPMI), OT security basics, and a home-lab project using cheap hardware (e.g. Raspberry Pi or used mini PCs). Suggest real certifications worth considering (e.g. CKA, Linux Foundation, CompTIA Network+/Security+, ISA/IEC 62443 certificates) with honest notes on which employers actually ask for. Format as a table plus a short list of hands-on milestones.
```

> **Caution:** Check current certification names, prices and exam objectives on the issuing body's site; they change often.
