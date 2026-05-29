---
title: "Reading"
parent: "Month 10 - Offensive Operations (Red Team Intro)"
grand_parent: Curriculum
nav_order: 90
---

# Month 10 Reading

Primary sources first, as always, and this month with a sharper edge: the per-box walkthrough is the anti-source. Reading a walkthrough of a box you are working, or intend to write up, leaves the curriculum and makes the writeup no longer your own work. The reading below is methodology and tooling documentation, never solutions.

## Required, before any lab

- _required_ `SAFETY.md` at the repo root. Re-read it end to end. This is the most scope-sensitive month in the course; the guardrails are absolute. Your legal targets are HackTheBox machines over the HTB VPN, TryHackMe rooms you deploy, and VulnHub VMs you downloaded. Nothing else.
- _required_ `AI-ETHICS.md` at the repo root. The recon-synthesis pattern is the narrowest in the course, and the hard guardrails (no AI-generated exploits against systems you do not own, no jailbreaking, no pasting sensitive data) come from here.

## The methodology and reporting backbone

These are the standards a professional engagement and report are built on. Read them as the structure your work and your deliverable follow.

- _standard_ NIST SP 800-115, the Technical Guide to Information Security Testing and Assessment (primary source for the phases of an assessment: planning, discovery, attack, reporting).
- _standard_ The Penetration Testing Execution Standard (PTES), for the full engagement structure and the report format the deliverable mirrors.
- _standard_ The OWASP Web Security Testing Guide, for the web exploitation methodology used in Labs 10.2 and 10.3.
- _reference_ MITRE ATT&CK, the tactic-and-technique catalog. Use it to name the techniques you use by their ATT&CK identifiers in your reports and in your detection reconciliations.
- _reference_ The CVSS specification (the version current at time of work), as a basis for a defensible, consistent severity scheme in your reports. Cite which version you used.

## Tooling (official documentation only)

Read the docs for the tools you run; do not rely on a blog's summary of a tool, and never run a tool you cannot explain.

- _docs_ The passive-recon and OSINT toolkit: `whois`, `dnsrecon` and `dnsenum` (DNS records and host enumeration), `amass` and `subfinder` (subdomain enumeration from public sources), `theHarvester` (emails, host names, and names from public search data), and `Shodan` (a search engine for internet-exposed services). Read each tool's own documentation. The scope caveat is absolute: an OSINT target must still be one you own or are explicitly authorized to research, because public does not mean permitted.
- _docs_ `man nmap`, in full for host discovery, service and version detection, and timing templates; reinforcing Month 4.
- _docs_ The `enum4linux-ng` project documentation (the maintained successor to the older `enum4linux`; prefer it).
- _docs_ The `NetExec` project documentation (the maintained successor to CrackMapExec; for SMB and Active Directory enumeration).
- _docs_ The `ffuf` and `feroxbuster` project documentation (content discovery; choose one as your default and know the other).
- _docs_ The official Metasploit Framework documentation (module types, payloads, sessions, and the limits that tell you when to go manual).
- _docs_ The `linpeas`, `winpeas`, and `pspy` project documentation (privilege-escalation enumeration aids; read what they check and note how loud they are).
- _reference_ GTFOBins (Unix binaries with privileged uses; reinforcing Month 2) and LOLBAS (the Windows living-off-the-land equivalent). Reference catalogs you read, not scripts you run blindly.

## The HackTheBox VPN connection documentation

- _docs_ The official HackTheBox VPN connection guide, for Lab 10.1 Task 1. Read how the tunnel places you on a network with the target, so your pre-flight check is grounded in what is actually happening.

## A note on sources

The single most important sourcing discipline this month: when you are stuck on a box, the legitimate sources are the man page, the official tool docs, the methodology standards above, and your own enumeration. The illegitimate source is a walkthrough of the box. The floor exists precisely so that you reach for the former. If you find yourself searching for "<box name> writeup," stop; that is the moment the curriculum is asking you to enumerate more, not to read the answer. And for any box you intend to publish, reading a walkthrough makes the report no longer yours.

A second discipline, carried from Month 5: when AI summarizes your recon, it will confidently cite a service or a finding that is not in your output. The reading above is your defense; the verification ritual is the test of whether you used it. Verify every AI claim against your own raw data.
