---
title: Curriculum
nav_order: 3
has_children: true
---

# Vigil: The 12-Month Curriculum

This document is the master index and the single source of truth for per-month content. Each month directory's `README.md` is built by expanding the relevant section below into the same shape as `month-01-it-foundations/README.md`.

A working learner, putting in 10 to 15 hours per week, completes this course in 12 months. Faster pacing (full-time) collapses it to 6. Slower pacing (5 to 8 hours per week) stretches it to 18. The content is the same; only the calendar changes. Python is the default working language; commit to one and stay.

## The seven pedagogical principles

The tutor enforces these. See `.tutor/tutor-core.md` and `tutor-reference.md`.

1. **Concept first, command second.** No tool runs until you can write down what it does at a packet, syscall, or filesystem level.
2. **The lab attempt floor.** 45 to 90 minutes of unaided work before any hint or walkthrough.
3. **Hints, not flags.** Six-rung ladder, one per ask. CTF flags are never confirmed by the tutor.
4. **The lab notebook is the gate.** No notebook entry, no advancement.
5. **Spaced revisits every three weeks.** The tutor pulls prior labs and asks you to redo subtasks cold.
6. **AI is an apprentice's tool.** AI-free zone Months 0 to 4. AI augmentation patterns unlock progressively from Month 5.
7. **You defend what you submit.** AI-augmented work is subject to random verification.

## Weekly cadence

Each month assumes 10 to 15 hours per week. A typical week:

- **Monday (2 hours).** Concept introduction. Read this month's `reading.md`. Begin the first lab of the week.
- **Tuesday through Thursday (2 to 3 hours each).** One to two labs. Pre-flight checks, floor enforcement, notebook entries committed.
- **Friday (2 hours).** Continue or complete a lab. Cold revisit on the third Friday of each month.
- **Saturday or Sunday (optional, 2 hours).** Stretch lab, CTF challenge, or rest. Missed cold revisits are made up before starting the next month.

## The 12 months at a glance

| Month | Pattern Family | Canonical Deliverable | Time Budget |
| ----- | -------------- | --------------------- | ----------- |
| 0     | Setup and home lab | Working VM stack | 8 hours |
| 1     | IT Foundations and Hardware | "What happens at boot" writeup | 40 hours |
| 2     | Linux CLI Mastery (and Regex) | Five shell scripts + cheat sheet | 50 hours |
| 3     | Networking Fundamentals | Home lab network diagram | 50 hours |
| 4     | Network Tools and Packet Analysis | Five PCAP analyses | 45 hours |
| 5     | Python for Security (and AI augmentation) | Four security tools (public repo) | 55 hours |
| 6     | Windows Security | Hardened domain controller writeup | 50 hours |
| 7     | Web Application Security (and SQL) | Web security portfolio + custom vuln app | 55 hours |
| 8     | Cryptography and PKI | Annotated TLS 1.3 handshake | 45 hours |
| 9     | Defensive Operations (Blue Team) | IR report on one investigated case | 55 hours |
| 10    | Offensive Operations (Red Team) | Three pentest writeups | 74 hours |
| 11    | Cloud and AI System Security | Cloud misconfig writeup + AI security review | 53 hours |
| 12    | Capstone | Pentest report + IR report + public artifact + mock screen + portfolio package | 80 hours |

## Per-month content specifications

### Month 0: Setup and Home Lab Foundations

**Focus.** Eliminate every excuse the next 12 months could offer.

**Tasks.**
- Pick the working programming language (Python recommended; Bash will be mandatory regardless).
- Install Homebrew, iTerm2 or Ghostty, dotfiles repo, Git, GitHub, a password manager, `python3` (confirm `python3 --version`), and a text editor (`nano` or VS Code).
- Start the self-paced, AI-free Python primer (variables, control flow, functions, data structures, file I/O), to be finished by the end of Month 4 before Month 5.
- Install UTM (free, native on Apple Silicon) or VirtualBox.
- Provision three VMs: Kali Linux, Ubuntu Server, and Windows (Windows 11 ARM64 evaluation for general work; Windows Server 2022 for the Month 6 domain-controller lab, with the Apple Silicon x86-64 caveat in `getting-started.md`). Snapshot each. For Ubuntu Server, enable OpenSSH and confirm you can log in at the console and `scp` a file in.
- Install the chosen AI coding tool (Claude Code, Codex CLI, Gemini CLI, OpenCode, or Pi Coding Agent).
- Install Ollama and pull one small local model (needed for the Month 11 AI-security labs and for offline AI work).
- Verify the Vigil tutor activates in the chosen tool.
- Sign up for free CTF platforms: picoCTF, TryHackMe, HackTheBox (free tier).
- Read `SAFETY.md` and `AI-ETHICS.md` end to end.

**Deliverable.** A `home-lab/` directory in your `my-vigil-work` repository documenting host configuration, VM inventory, and a working snapshot of all three VMs. First commit to the lab notebook (a `month-00.md` entry under `.tutor/notebook/` describing setup decisions and any friction encountered).

**No labs.** This month is configuration.

### Month 1: IT Foundations and Hardware

**Focus.** The bedrock the rest of the course presupposes.

**Core concepts.** Computer architecture (CPU, RAM, storage, buses), BIOS/UEFI and boot processes, filesystems, the kernel-userspace divide, basics of CPU privilege rings, how an interrupt fires, light virtualization theory (Type 1 vs Type 2 hypervisors).

**Labs.**
- Lab 1.1: Hardware Inventory. Enumerate your own Mac's hardware. Write a Bash script that produces a structured inventory.
- Lab 1.2: EFI Shell and Boot. Boot a VM with the EFI shell visible. Document what you see and what each component does.
- Lab 1.3: picoCTF General Skills. Complete 8 to 12 easy challenges in the General Skills track.

**Deliverable.** A `month-01-foundations.md` writeup in the lab notebook explaining what happens between pressing the power button and seeing a login prompt, written for a smart non-engineer.

**AI guidance.** AI-free zone. No AI assistance on any lab in this month.

### Month 2: Linux CLI Mastery and Regex

**Focus.** Non-negotiable. The rest of the course presupposes ownership of the Linux shell.

**Core concepts.** Filesystem layout, permissions, users and groups, processes and signals, package management, text processing (`grep`, `sed`, `awk`, `cut`, `sort`, `uniq`), pipes and redirection, environment variables, systemd basics. Bash scripting: variables, conditionals, loops, functions, exit codes, `set -euo pipefail`, error handling. **Regex fluency**: character classes, anchors, quantifiers, groups, backreferences, lookaheads, the differences between BRE/ERE/PCRE.

**Labs.**
- Lab 2.1: Linux Fundamentals. TryHackMe "Linux Fundamentals 1, 2, 3" rooms.
- Lab 2.2: Five Shell Scripts. Write five scripts that automate real daily friction (system info dump, log tail with grep filters, scheduled backup, fail2ban-style watcher, service health checker).
- Lab 2.3: Regex Drills. 30 progressively difficult regex puzzles (RegexOne, Regex Crossword). Hand-written, no AI assistance.
- Lab 2.4: Log Parsing Pipelines. Write 10 grep/sed/awk pipelines that extract specific patterns from sample log files (Apache, nginx, syslog).
- Lab 2.5: GTFOBins Exploration. Identify five binaries with unintended privileged uses, document why each is dangerous.

**Deliverable.** A `linux-survival.md` cheat sheet written from memory at end of month (no copy-paste from the web), plus the five working shell scripts in a public repo.

**AI guidance.** AI-free zone.

### Month 3: Networking Fundamentals

**Focus.** TCP/IP from the bottom up.

**Core concepts.** Ethernet frames, IP addressing and subnetting until muscle memory, CIDR notation, ARP, ICMP, the three-way handshake, sockets, ports, NAT, routing basics, DNS hierarchy, DHCP lease lifecycle, the OSI model used correctly.

**Labs.**
- Lab 3.1: Subnetting Drills. 50 problems hand-solved. The tutor refuses calculators.
- Lab 3.2: Virtual Network Build. Set up a virtual network in UTM/VirtualBox with two subnets and a router VM. Document the routing table.
- Lab 3.3: Protocol Captures. Wireshark captures of your own DHCP lease, DNS query, and TCP handshake. Annotate one packet per protocol.
- Lab 3.4: TryHackMe Networking. Complete the "Network Fundamentals" path.

**Deliverable.** A network diagram of your home lab, annotated with subnets, routing, DHCP scopes, and DNS resolvers, plus the three Wireshark captures with your annotations.

**AI guidance.** AI-free zone.

### Month 4: Network Tools and Packet Analysis

**Focus.** From understanding protocols to reading traffic.

**Core concepts.** Wireshark in depth (display filters use regex; reinforce from Month 2), tcpdump for command line, nmap (host discovery, port scanning, service detection, NSE basics), Netcat, traceroute mechanics, basic network forensics.

**Labs.**
- Lab 4.1: PCAP Analysis. Analyze five PCAPs from MalwareTrafficAnalysis.net. Identify what is happening in each. Write up findings.
- Lab 4.2: Nmap Exploration. Run nmap against your own lab. Interpret results. Re-run with different timing templates and explain what changed.
- Lab 4.3: Wireshark CTF. TryHackMe "Wireshark CTFs" room.

**Deliverable.** Five PCAP analysis reports in the lab notebook. Two to three pages each. Written as if for a SOC analyst on the next shift.

**AI guidance.** AI-free zone. This is the last month of the AI-free zone.

### Month 5: Python for Security (AI augmentation unlocks)

**Focus.** Python at the level needed to build security tools and automate analysis. **AI assistance unlocks: drafting pattern.**

**Core concepts.** Python standard library (`socket`, `argparse`, `json`, `sqlite3`, `re`, `hashlib`) and `requests`. Reading and parsing logs at scale. JSON. Concurrency basics. The `re` module (regex reinforcement). The `sqlite3` standard library module (implicit SQL exposure). Three weeks of building, one week of cold revisits across Months 1 to 4.

**Prerequisite.** Basic Python, built in the Month 0 self-paced primer worked through Months 1 to 4 (variables, control flow, functions, data structures, file I/O). Month 5 opens with a Week 0 self-check that gates Lab 5.1.

**Labs.**
- Lab 5.1: Pure-Python Port Scanner. No nmap. Compare your output to nmap on a target you own.
- Lab 5.2: Log Parser with SQLite Backend. Ingest Apache or nginx logs into a SQLite database. Produce a structured incident summary.
- Lab 5.3: Password Strength Tester. Length, entropy, dictionary words, HIBP k-anonymity API check.
- Lab 5.4: HTTP Fuzzer (Lab Only). Against your own DVWA install. Honors lab scope rules.

**Deliverable.** Four working tools in a public `security-tools/` repo with READMEs, tests, and a `SAFETY.md` reminding any future user of the legal-use boundary.

**AI guidance.** Drafting pattern: ask AI to draft code; refactor and test yourself. Verification ritual: for each tool, tutor picks one function and asks you to explain it from memory. AI Provenance log required in every notebook entry.

### Month 6: Windows Security

**Focus.** Windows as a security target and platform. **AI augmentation pattern: concept orientation.**

**Core concepts.** NT architecture basics, Windows registry, services, scheduled tasks, Group Policy. Active Directory: domains, forests, OUs, Kerberos. PowerShell as a security tool. Windows logs (Event Viewer, Sysmon). Common Windows attacks at conceptual level (pass-the-hash, kerberoasting, golden ticket, lateral movement).

**Labs.**
- Lab 6.1: Domain Controller Setup. Stand up Windows Server 2022 evaluation VM. Promote to DC. Add member workstation.
- Lab 6.2: Sysmon and Suspicious Activity. Install Sysmon with SwiftOnSecurity config. Generate suspicious activity yourself (PowerShell child of Word, scheduled task creation). Find it in the logs.
- Lab 6.3: TryHackMe Windows Path. Complete Windows Fundamentals plus one Active Directory room.

**Deliverable.** A `windows-baseline.md` describing the hardened configuration of your DC and member workstation, with screenshots of relevant settings.

**AI guidance.** Concept orientation: ask AI to explain unfamiliar Windows artifacts and vocabulary. Verify against Microsoft documentation. Do not consult AI for security configuration decisions.

### Month 7: Web Application Security (and SQL)

**Focus.** The single biggest source of breaches at small and mid-sized companies. **AI augmentation pattern: brainstorming variations.**

**Week 1: SQL through the attack surface.** Local PostgreSQL and MySQL setup. Sample schema (users, login attempts, sessions, audit logs). SELECT, WHERE, JOIN variants, GROUP BY, HAVING, subqueries, prepared statements, parameterization. The fluency required for Week 2.

**Weeks 2 to 4: Web security.** HTTP at the wire level, HTTPS at the handshake level, cookies and sessions, same-origin policy, CORS. OWASP Top 10 with hands-on labs each. Burp Suite Community as daily driver.

**Labs.**
- Lab 7.1: SQL Fluency. The Week 1 SQL drills against the sample schema. Hand-written, no AI.
- Lab 7.2: PortSwigger Apprentice. Complete apprentice-level labs in SQLi, XSS, CSRF, IDOR, SSRF, file upload, and authentication.
- Lab 7.3: OWASP Juice Shop. Document first 20 challenges with reproduction steps.
- Lab 7.4: DVWA Walkthrough. Run Burp against your own DVWA. Document one vulnerability of each OWASP Top 10 category.
- Lab 7.5: Custom Vulnerable App. Build a small Flask or Express app with two known flaws documented in its README. Remove from public hosting after lab is done.

**Deliverable.** A `web-security-portfolio.md` documenting completed labs with screenshots, plus the custom vulnerable app's repo.

**AI guidance.** Brainstorming variations: after you craft an SQLi or XSS payload, ask AI for variations to test. AI does not identify vulnerabilities; you do. AI does not write your custom vulnerable app.

### Month 8: Cryptography and PKI

**Focus.** Crypto at the practitioner level. **AI guidance: heavily restricted.**

**Core concepts.** Symmetric vs asymmetric, hashing, HMACs, digital signatures. PKI: CAs, chains of trust, X.509 fields, revocation. TLS 1.2 vs 1.3 handshake in detail. Common crypto failures (ECB, IV reuse, padding oracles, weak RNGs).

**Labs.**
- Lab 8.1: CryptoHack Introduction and General sections. The tutor refuses to give solutions or confirm flags.
- Lab 8.2: Build Your Own CA. Generate a CA, issue a server cert, set up HTTPS locally. Deliberately misconfigure it three ways and observe browser response.
- Lab 8.3: TLS Handshake Annotation. Capture a TLS 1.3 handshake in Wireshark. Annotate every message.

**Deliverable.** A `tls-handshake-annotated.md` walkthrough of a real captured handshake, plus the working CA and certs in a private repo.

**AI guidance.** Restricted. AI permitted only for explaining crypto concepts in plain language. AI not permitted for CryptoHack solutions or for crypto math. Crypto is the domain where AI hallucinates most confidently; verify everything against authoritative sources (RFC, NIST publications).

### Month 9: Defensive Operations (Blue Team)

**Focus.** What a SOC analyst or detection engineer actually does. **AI augmentation pattern: detection rule drafting.**

**Core concepts.** SIEM architecture. Log sources that matter and the ones that do not. Building detections (not just consuming alerts). IDS/IPS basics (Snort/Suricata). Incident response (NIST 800-61 phases). MITRE ATT&CK as navigation tool. **SIEM query languages as SQL dialects**: Splunk SPL, Microsoft KQL.

**Labs.**
- Lab 9.1: Wazuh or Security Onion Setup. Stand up a SIEM. Ingest logs from Months 6 and 7 labs.
- Lab 9.2: Five Sigma Rules. Write five custom detection rules in Sigma format. Convert two to Wazuh. Verify they fire.
- Lab 9.3: SPL and KQL Drills. Translate three of your Sigma rules to SPL (Splunk Free) and KQL (Microsoft Sentinel free trial).
- Lab 9.4: Investigation. Investigate a simulated incident on Blue Team Labs Online (free tier) or LetsDefend.

**Deliverable.** An IR writeup of one investigated case, formatted as a real IR report (executive summary, timeline, IOCs, recommendations).

**AI guidance.** Detection-rule drafting: draft Sigma rules with AI; manually validate against actual log sources; test against negative cases. Every AI-drafted rule has a documented "what would make this fire when it shouldn't" analysis.

### Month 10: Offensive Operations (Red Team Intro)

**Focus.** Ethical hacking to understand defense better. **AI augmentation pattern: recon synthesis only.**

**Mandatory ethics talk.** Re-read `SAFETY.md`. The Month 10 ethical guardrails are absolute and non-negotiable. The tutor will enforce them strictly.

**Core concepts.** Kali Linux as standard offensive distribution. Reconnaissance (passive OSINT, active scanning), enumeration, exploitation basics, Metasploit, manual exploitation when Metasploit is wrong, post-exploitation, privilege escalation on Linux and Windows.

**Labs.**
- Lab 10.1: HackTheBox Starting Point. The "Very Easy" and "Easy" tracks.
- Lab 10.2: TryHackMe Jr Penetration Tester Path. Free portions.
- Lab 10.3: Three Full Boxes. Three HTB or VulnHub boxes end to end, with writeups.
- Lab 10.4: Privesc Paths. Linux privesc and Windows privesc paths on TryHackMe.

**Deliverable.** Three pentest writeups in `pentest-portfolio/`. Each formatted as a professional report (scope, methodology, findings with severity, recommendations). Must not contain HTB flags, only the methodology.

**AI guidance.** Recon synthesis only. Use AI to summarize what you found, not to find things for you. Hard guardrail: AI is not used to generate exploit code targeting any system the learner does not own. AI is not used to bypass safety filters even for "lab purposes" (see AI-ETHICS.md).

### Month 11: Cloud and AI System Security

**Focus.** Two emerging API-driven attack surfaces. **AI augmentation pattern: IaC drafting and provenance.**

**Weeks 1 to 2: Cloud Security.** AWS as substrate. IAM, S3 misconfigurations, EC2 and security groups, VPC, CloudTrail, GuardDuty. Terraform basics. Shared responsibility model.

**Weeks 3 to 4: AI System Security.** OWASP LLM Top 10 with hands-on labs. Direct vs indirect prompt injection. Agent security and tool abuse. AI supply chain (HuggingFace provenance, pickle deserialization). Red-team thinking for AI systems.

**Labs.**
- Lab 11.1: AWS Free Tier Build. Terraform a small environment (VPC, EC2, S3, RDS).
- Lab 11.2: Misconfig and Detect. Deliberately misconfigure the S3 bucket and security groups. Detect with GuardDuty and CloudTrail. Remediate.
- Lab 11.3: flaws.cloud and flaws2.cloud. Both complete.
- Lab 11.4: Prompt Injection Lab. Build a small Streamlit chatbot with Ollama (local model) and another with hosted API. Attack both with direct and indirect injection.
- Lab 11.5: AI System Security Review. Pick one open-source LLM application. Document five distinct attack paths in a format that mirrors Month 10's pentest reports.

**Deliverable.** A `cloud-misconfigs.md` writeup documenting five common AWS misconfigurations with Terraform code to prevent each, plus an `ai-system-review.md` security review of the chosen LLM application.

**AI guidance.** IaC drafting: AI drafts Terraform; you verify and harden. Full provenance log discipline applies. AI labs for Weeks 3 to 4 use AI as both tool and target.

### Month 12: Capstone

**Focus.** Synthesis. The capstone is the artifact you show a hiring manager.

**Required tracks (five: A, B, C, E, F).** Capstone D is a mandatory appendix inside A, B, and C, not a separate track. The authoritative spec for every track is `month-12-capstone/deliverable.md` and the per-track files under `month-12-capstone/tracks/`.

**Capstone A: Full pentest report.** A retired HackTheBox box (medium or hard) or a VulnHub VM you have not seen. Full engagement: scoping (with documented authorization), recon, enumeration, exploitation, post-exploitation, lateral movement if applicable, reporting. Professional 15 to 25 page pentest report.

**Capstone B: IR report.** Using your Month 9 SIEM, run a simulated breach scenario (you author the scenario, ideally with a study partner). Investigate as SOC analyst would. Professional 10 to 15 page IR report.

**Capstone C: Public artifact.** At least one published, searchable, public written piece is required (a blog post walking through one earlier lab, or a retired-CTF writeup). Unless the target role is offensive, the required piece is a sanitized public version of the defensive work. A contribution to an open-source security tool, or a polished GitHub repository of the Month 5 and 7 tooling, may be added but does not satisfy the written requirement.

**Capstone D (mandatory subsection of A, B, and C): AI Provenance appendix.** Every capstone deliverable includes an "AI Provenance" appendix in the same format used throughout the course. This is the AI fluency demonstration employers screen for.

**Capstone E: Timed mock technical screen.** One 45-minute timed mock screen the tutor conducts against your own artifacts (5 technical, 5 behavioral, AI closed), followed by a written self-assessment. A second screen run by a human (a study partner or mentor) is strongly recommended where one is reachable.

**Capstone F: Portfolio package and target role.** A named target role, a one-to-two-page role-targeted resume, a single public portfolio-index page with a thesis, and a public-profile pass that links your public artifacts.

**Final deliverable.** A `RETROSPECTIVE.md` reflecting on the 12 months: which patterns the learner found weak, the strongest patterns, a named target role, three problems the learner expects to see in real interviews and their playbook for each, an honest read of the local job market, and a 6-month maintenance plan.

**AI guidance.** Full augmentation permitted, full provenance required. The capstone is where you demonstrate the AI fluency built over the course.

**Time budget.** 80 hours across the month. Do not crunch.

## Source

The topic selection is adapted from widely-used public cybersecurity career roadmaps. The pedagogy is original to Vigil and builds on the patterns established in Lernen, Agentwright, and Muster.
