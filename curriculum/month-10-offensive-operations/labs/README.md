---
title: "Labs"
parent: "Month 10 - Offensive Operations (Red Team Intro)"
grand_parent: Curriculum
nav_order: 50
---

# Month 10 Labs

Four labs, completed in order. They move from guided platform tracks to full independent engagements to a focused privilege-escalation drill. Each assumes the tradecraft the previous one built. The lab attempt floor, the recon-synthesis AI pattern, and the mandatory AI Provenance log apply to every one (see the Month 10 README).

Before you start any lab, re-read `SAFETY.md` and the mandatory ethics talk in the Month 10 README. This is the most scope-sensitive month in the course. Your legal targets are HackTheBox machines over the HTB VPN, TryHackMe rooms you deploy, and lab infrastructure you own and run on your own hardware (VulnHub VMs; for the Lab 10.2 credential-bootstrapping and Active Directory work, the Month 6 domain you built; and for the Lab 10.4 pivot, your own VMs on an isolated network you control). Nothing else, under any framing. The platform rationale and scope detail are in `../ctf-set/README.md`.

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 10.1 HackTheBox Starting Point | `lab-01-htb-starting-point/` | 14 to 16 h | 90 min per stuck box | The enumeration reflex, the engagement workflow on rails, and shell handling |
| 10.2 TryHackMe Jr Penetration Tester | `lab-02-tryhackme-jr-pentester/` | 22 to 26 h | 90 min per stuck room | A technique vocabulary (recon, enumeration, web, Metasploit), credential bootstrapping, plus Active Directory attack execution |
| 10.3 Three Full Boxes | `lab-03-three-full-boxes/` | 20 to 24 h | Multi-hour per box | Three professional pentest reports (the deliverable) |
| 10.4 Privilege Escalation Paths | `lab-04-privesc-paths/` | 12 to 14 h | 90 min per stuck challenge | Privilege escalation as a methodology, Linux and Windows, plus a pivot through a foothold |

Every lab carries a hard scope rule baked into its text; re-read each lab's "scope rule, first" section before you run anything. No lab records flags, in notes or in reports; the tutor never confirms a flag. Lab 10.3 produces the month's deliverable, the three reports in `pentest-portfolio/` (see `../deliverable.md`).

Complete all four, commit a notebook entry for each (every one with a complete AI Provenance section), and produce the three-report deliverable before advancing to Month 11.
