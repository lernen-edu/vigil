---
title: "CTF and Training Platform Set"
parent: "Month 10 - Offensive Operations (Red Team Intro)"
grand_parent: Curriculum
nav_order: 10
---

# Month 10 CTF and Training Platform Set

This month's labs run on external offensive-security training platforms. This file lists exactly which platforms and tracks are used, why each was chosen, and the scope rule that governs all of them. Read it before Lab 10.1.

## The scope note, first, because it governs everything here

Every platform listed below is a legal target **only because its own terms of use authorize the activity it hosts**, and only within the boundary those terms define. The authorization is platform-specific and target-specific:

- HackTheBox authorizes you to attack the machines on HackTheBox infrastructure, reached through the HackTheBox VPN. It does not authorize you to attack anything else you can route to while the VPN is up.
- TryHackMe authorizes you to attack the deployed room you are working in. The room is the target; the platform is not.
- VulnHub distributes virtual machines you download and run on your own hardware. The VM is yours; your authorization comes from owning the metal it runs on.
- The **Active Directory domain you built in Month 6** is a legal target for the Lab 10.2 AD work for the same reason a VulnHub VM is: you own the hardware it runs on, and you run it on an isolated network you control. It is not a platform; it is owned lab infrastructure, the cleanest authorization basis there is.

Nothing beyond these (the three platforms and your own lab infrastructure) is a legal target by virtue of you being a student in this course. Not a website you happen to use, not your employer, not your home router, not a neighbor's network, and not any Active Directory domain you do not own. The complete and final word on this is `SAFETY.md` at the repo root; this file does not override it, narrow it, or add exceptions to it. If anything here seems to conflict with `SAFETY.md`, `SAFETY.md` wins.

A scope rule that becomes practical this month: while connected to a platform VPN, **confine your tooling to the target's address.** A scan that escapes the intended host (a wrong subnet mask, a range that includes the gateway) can touch infrastructure you are not authorized to test. Set your target precisely, every time, and confirm it before you run anything. If you discover something out of scope, follow the decision tree in `SAFETY.md`.

## Platforms used this month

### HackTheBox (free tier and VPN)

- **Used in:** Lab 10.1 (Starting Point), Lab 10.3 (retired boxes for two of the three reports).
- **What it is:** A platform hosting intentionally vulnerable machines reachable over an OpenVPN connection. The free tier gives access to the Starting Point track and to retired machines.
- **Why it is used:** HTB's Starting Point is the best on-rails introduction to the full engagement workflow against realistic targets, and its retired-machine library is the standard source for portfolio writeups. HTB's terms of use explicitly authorize attacking the hosted machines, which is precisely the written authorization `SAFETY.md` requires.
- **Scope specifics:** Only machines on HTB infrastructure, only over the HTB VPN. **Writeups of HTB machines are permitted only after the machine is retired.** Active machines are under HTB's content rules; do not publish methodology for an active box. This restriction shapes which boxes you can use for the deliverable: pick retired boxes if the writeup will be public.

### TryHackMe (free rooms)

- **Used in:** Lab 10.2 (Jr Penetration Tester path, free portions), Lab 10.4 (Linux and Windows privilege-escalation rooms).
- **What it is:** A guided platform of "rooms," each a deployable vulnerable environment paired with structured learning material. A free account gives access to a large set of rooms, including much of the Jr Penetration Tester path and the core privilege-escalation rooms.
- **Why it is used:** TryHackMe's structure (concept material, then a deployable target to practice on) fits the course's "concept first, command second" principle better than any other platform. The Jr Penetration Tester path covers recon, enumeration, web exploitation, Metasploit fundamentals, and **Active Directory** in the order this month needs them. Its AD rooms are a good second target for kerberoasting, pass-the-hash, and lateral movement **if they are in the free tier when you reach them**; some TryHackMe AD content is subscription-only. The Lab 10.2 Active Directory work therefore treats the learner's own Month 6 domain as the required, always-available target and a free TryHackMe AD room as an optional second run, so the task does not depend on a paywall.
- **Scope specifics:** The target is the deployed room. Attack the room's machine, nothing else. Some rooms in the Jr Penetration Tester path (including some AD rooms) require a subscription; the labs use the free portions and name where a room may be paywalled so you can substitute or fall back to your own Month 6 domain for the AD work. Never leave the platform for an unauthorized target to fill a paywalled gap.

### VulnHub (downloaded VMs)

- **Used in:** Lab 10.3 (one of the three boxes, recommended for the report you intend to make public).
- **What it is:** A catalog of community-built vulnerable virtual machine images you download and import into your own hypervisor (UTM or VirtualBox from Month 0).
- **Why it is used:** A VulnHub VM is the cleanest authorization story in the course: you downloaded it, it runs on your hardware, on a network you control. It also carries **no writeup restriction**, unlike an active HTB box, so it is the safest source for a public portfolio report. Running it on a host-only or NAT network keeps it isolated from anything you do not intend to touch.
- **Scope specifics:** Run the VM on an isolated host-only or NAT network. The VM is the target; your own host and your other VMs are not. Pick a VM rated beginner or intermediate; the goal is a complete, well-documented engagement, not the hardest box you can find.

## Platforms deliberately not used

- **Live bug-bounty programs.** Out of scope for this course, for the reasons `SAFETY.md` gives: the scoping is narrow, the legal review depends on the specific program's terms, and the risk of accidentally testing out of scope is high. Bug bounties are not a Month 10 target and are not a capstone target.
- **Any internet host not on the platforms above.** Restated because it is the most common way a learner gets into trouble: the public internet is not a practice range.

## How this set maps to the deliverable

The three reports in `pentest-portfolio/` come primarily from Lab 10.3. The recommended composition is at least one retired HTB box and at least one VulnHub VM, so that the report you make public rests on a target with no writeup restriction. The deliverable spec (`../deliverable.md`) gives the full requirement; this file's job is only to tell you which platforms are authorized and why.

## A reminder the tutor will enforce

The tutor never confirms a flag, on any of these platforms, at any point. Submit flags on the platform itself. Your notebook and your reports record methodology, not flags. If you are stuck and your flag is not accepted, that is a hint-ladder conversation about your method, not a request for the tutor to check your answer.
