---
title: "CTF and Training Set"
parent: "Month 4 - Network Tools and Packet Analysis"
grand_parent: Curriculum
nav_order: 92
---

# Month 4 CTF and Training Set

This month's hands-on work relies on external training platforms and public capture sources rather than challenges authored inside this repository. This file lists what is used, why each was chosen, and the scope note that governs all of it.

## The scope note (read first)

These platforms and sources authorize the activity through their terms of use. That authorization is what makes the work legal. Nothing outside them is a legal target.

- MalwareTrafficAnalysis.net publishes captures for the express purpose of analyst training and authorizes you to download and analyze them. You are reading a file on your own machine; there is no scanning and no network interaction with anyone else's systems.
- TryHackMe provides the captures and the environment inside the platform, and its terms authorize you to work the rooms.
- The `nmap` work in Lab 4.2 is not on any of these platforms. It runs only against the VMs on your own host, per `SAFETY.md`. Your own lab is the authorized target there, and nothing else is.

If you ever find yourself about to point a tool at a host that is not one of these authorized sources and is not a system you own, stop. That is the line `SAFETY.md` draws and the tutor enforces. There are no exceptions: not a public site "to see if the filter works," not a friend's box with verbal permission, not a network at a coffee shop. If you cannot name the authorization, you do not have it.

## Lab 4.1: PCAP captures

**Source: MalwareTrafficAnalysis.net (and similar public analyst-training capture libraries).**

- **What it is.** A long-running public library of packet captures containing real malicious traffic (malware delivery chains, command-and-control, exfiltration), published with exercises and write-ups for analyst training.
- **Why this source.** The traffic is genuine, not synthetic, so the patterns you learn to read are the patterns you will see in real work. The captures are varied enough to give you the spread Lab 4.1 asks for (a scan, a download chain, beaconing, suspicious DNS, exfiltration). And the site exists specifically so analysts can practice without needing a live incident, which is exactly the authorization this course requires.
- **How to use it without spoiling the lab.** The site pairs many captures with published write-ups and answer keys. Use the capture and the high-level label (date, malware family hint, "exercise" tag) to pick a spread; do not read the write-up for a capture you are about to analyze. Reading the answer resolves the exercise and destroys the learning. If you are stuck past the 90-minute floor, use the tutor's hint ladder, not the site's answer key.
- **Alternatives if a specific capture is unavailable.** Other public analyst-training capture libraries (the kind that publish sample captures for protocol and forensics practice) are acceptable substitutes, provided their terms authorize download and analysis and they are not captures of someone's real private network. The Wireshark project's own sample-capture wiki is one such source for protocol practice, though it is lighter on malicious traffic than the primary source.

## Lab 4.3: Wireshark CTF challenges

**Platform: TryHackMe, the "Wireshark CTFs" room (with its prerequisite Wireshark rooms).**

- **What it is.** A guided room of capture-the-flag challenges built around finding specific answers inside provided packet captures, using Wireshark display filters, Follow Stream, and the rest of the feature set.
- **Why this platform.** TryHackMe is one of the free CTF platforms set up in Month 0, so there is no new account or cost. The room is scoped to exactly the skills Lab 4.3 drills: hypothesis-driven filtering and stream reconstruction. The captures are provided inside the platform, so there is no scope question; the platform is the authorized environment.
- **Prerequisites inside the platform.** The "Wireshark CTFs" room assumes familiarity with the Wireshark basics and traffic-analysis rooms that precede it on the platform. If the CTF room feels like it is assuming a feature you have not met, work the prerequisite Wireshark rooms first; they are part of the same learning path.
- **The flag rule.** You submit flags on the platform; the platform confirms them. The tutor never confirms a flag, at any hint rung. Do not record flags in your notebook; record the method that found them. This is the same rule that governed picoCTF in Month 1 and governs every CTF in the course.
- **Alternatives if the room is unavailable.** Equivalent free packet-analysis CTF content exists on other authorized platforms (for example, other introductory network-forensics rooms on the same or a comparable training platform, or the network-forensics challenges on a CTF archive whose terms permit practice). Any substitute must be a platform that provides the captures and authorizes the activity through its terms. Do not substitute "find a random capture on the internet and look for secrets in it"; provenance and authorization are the point.

## What is not in scope this month

- No scanning, probing, or any active interaction with systems you do not own. Lab 4.2's `nmap` work is confined to your own VMs.
- No analysis of captures taken from a real private network that is not yours, including a workplace or school network. The authorized captures come from the training sources above or from your own lab.
- No pasting of capture contents, packet bytes, extracted strings, or flags into any AI service. Month 4 is in the AI-free zone, and beyond that, real captures can carry sensitive data; the habit of not feeding them to public services starts here (see `AI-ETHICS.md`).
- No published write-ups of the specific capture or challenge you are working. The hint ladder is the only assistance; it nudges without resolving.
