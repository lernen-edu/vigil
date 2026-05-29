---
title: "CTF and Training Platform Set"
parent: "Month 8 - Cryptography and PKI"
grand_parent: Curriculum
nav_order: 60
---

# Month 8 CTF / Training Platform Set

This month's hands-on cryptography practice relies on one external training platform. This file lists which platform and which challenges are used, why they were chosen, and the scope note that governs all of it.

## The scope note, first and non-negotiable

The platform listed below is a legal target for your practice **because its own terms of use authorize you to solve the challenges it hosts.** That authorization is what makes the activity lawful, and it covers that platform and nothing else.

Per `SAFETY.md`: you may only test, analyze, or attack systems you demonstrably own or are explicitly authorized to use. CryptoHack's challenges are authorized by its terms. Your own machine (Labs 8.2 and 8.3) is authorized because you own it. **Nothing else is a legal target.** The encoding tricks, XOR manipulations, certificate handling, and TLS analysis you learn this month are general skills. Pointing any of them at a website, service, account, network, or machine you do not own is the exact line `SAFETY.md` draws, and crossing it can be a CFAA matter regardless of intent. There is no "just to see if it works" exception. Practice on the authorized platform; build and capture on your own hardware; touch nothing else.

## Platform used

### CryptoHack (Lab 8.1)

**What it is.** A free, public-purpose platform for learning cryptography through self-contained challenges. It is built for exactly this kind of structured practice and its terms authorize solving the challenges it hosts.

**What is used this month.**

- The **"Introduction to CryptoHack"** course (roughly ten lessons), worked end to end. It covers ASCII, hexadecimal, Base64, converting between bytes and large integers, and the XOR starter.
- The **"General"** challenge category, worked substantially (the encoding and XOR sub-sections in particular, which the rest of the month depends on). Clearing the entire category is not required; substantial, honest progress is.

**Why these and not the harder categories.** Month 8 is a practitioner's introduction to cryptography, not a cryptographer's training. The Introduction course and General category build the byte-level fluency (encodings, XOR, bytes-to-integers) that every later concept this month sits on, and they do it at a difficulty a learner with no prior crypto can work through by struggle rather than by looking up math. The harder CryptoHack categories (RSA, Diffie-Hellman, Elliptic Curves, Lattices, Isogenies) are excellent and are exactly where a learner who enjoys this month should go next, but they assume mathematics this course does not teach and would turn a 14-to-16-hour lab into a multi-month detour. They are noted as optional stretch work, not required.

**The no-flag and no-writeup rules for this platform.**

- The tutor never confirms a CryptoHack flag, at any hint rung. CryptoHack itself tells you whether a flag is correct when you submit it; that is the only authority. Do not paste a flag to the tutor.
- CryptoHack's FAQ asks solvers not to publish solutions or writeups outside the platform, with a narrow exception for "Starter" challenges and challenges worth 25 points or less. Honor that policy. Your notebook documents your understanding and approach, not the flags; anything you might post publicly is limited to the starter-tier challenges the platform explicitly permits discussing.

**AI restriction on this platform.** Per the month's restricted AI pattern: AI may explain a crypto concept in plain language, but may not solve a CryptoHack challenge, hint toward one, do the math, or confirm a flag, and no challenge data is ever pasted into an AI tool. See Lab 8.1's "AI guidance for this lab" section.

## Platforms deliberately not used this month

- **No HackTheBox, TryHackMe, VulnHub, or picoCTF crypto tracks this month.** They are fine platforms (and are used elsewhere in the course), but CryptoHack's Introduction and General sections are the cleanest, most focused match for this month's byte-level and encoding objectives. Adding a second platform would dilute the practice without adding to the learning at this stage.
- **No real-world or "found" targets, ever.** There is no scenario this month in which a system you do not own becomes a practice target. If a challenge or write-up you find online suggests pointing a technique at a live external service, that is out of scope and against `SAFETY.md`; do not follow it.

## What about Labs 8.2 and 8.3?

Neither uses an external CTF platform. Lab 8.2 (Build Your Own CA) runs entirely on your own machine; its authorization basis is ownership, and its repository is private because it holds key material. Lab 8.3 (TLS Handshake Annotation) captures your own traffic on your own machine; its authorization basis is also ownership. The scope note above still governs both: own systems only, nothing else.
