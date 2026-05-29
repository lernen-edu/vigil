---
title: "CTF and Training Platforms"
parent: "Month 11 - Cloud and AI System Security"
grand_parent: Curriculum
nav_order: 60
---

# Month 11 CTF and Training Platform Set

This month relies on external, free, intentionally vulnerable training platforms for the cloud half. This file lists which platforms are used, which labs use them, and why, and it states the scope basis. Read it before Lab 3.

## The scope basis (read this first)

The platforms below authorize the activity through their own terms of use. That authorization is what makes them legal targets, exactly as VulnHub VMs and retired HackTheBox boxes were legal targets in Month 10. The authorization extends to these specific platforms and to nothing else.

While working these platforms you will learn techniques (enumerating an S3 bucket, assuming an IAM role, reading the EC2 instance metadata service) that are criminal against any AWS account you are not authorized to test. Do not aim a single command at any AWS resource that is not one of these platforms or your own account. `SAFETY.md` governs this month in full. The skill is the technique plus the discipline of only ever pointing it at an authorized target.

## The platforms

### flaws.cloud (Lab 11.3)

- **What it is:** a free, browser-and-CLI-based AWS security training game, built by a cloud-security practitioner specifically so that people can learn to find and exploit AWS misconfigurations safely. It is intentionally vulnerable.
- **Why it is used:** it is the canonical free, hands-on introduction to AWS misconfiguration exploitation, walking through a progression of S3 and IAM mistakes. After building correct infrastructure in Lab 1 and detecting misconfigurations in Lab 2, this game lets you experience the same mistakes from the attacker's side, which is what makes the defender's controls concrete.
- **Scope:** authorized by the game's own terms of use. The game provides in-game hints as part of its design; those hints are part of the intended experience and are not the "walkthroughs" the floor forbids. External, third-party walkthroughs of the levels are off-limits during the floor, the same as any CTF.
- **How it feeds the deliverable:** each level's underlying misconfiguration maps to an AWS control you document in `cloud-misconfigs.md`. Lab 3 asks you to build that mapping explicitly.

### flaws2.cloud (Lab 11.3)

- **What it is:** a free, intentionally vulnerable AWS security training game by the same author, with an attacker track and a defender track. It goes deeper than flaws.cloud into IAM roles, the instance metadata service, and privilege movement.
- **Why it is used:** the attacker track extends the exploitation skills from flaws.cloud; the defender track asks you to reason about how you would have stopped each attack, which connects directly to the preventive controls in your deliverable. The defender perspective is the bridge between this month's offensive and defensive halves.
- **Scope:** authorized by the game's own terms of use. Same hint discipline as above.
- **How it feeds the deliverable:** the defender track is, in effect, a guided draft of part of `cloud-misconfigs.md`; take notes accordingly.

## The CTF rules for this set (same as the rest of the course)

- **The lab attempt floor applies:** 45 minutes per stuck level before you ask the tutor for a hint. The tutor will not negotiate the floor down.
- **Hints come in the six-rung ladder**, one rung per request. The tutor guides; it does not solve, and it does not walk you through any level.
- **The tutor never confirms a flag or a found value.** These games sometimes signal progress with a value or a next subdomain. Do not paste it to the tutor and ask whether it is correct; the tutor does not confirm it, and the game itself tells you whether you have progressed. This is the same absolute rule that applies to picoCTF, TryHackMe, and HackTheBox throughout the course.

## On the AI labs (Labs 11.4 and 11.5)

The AI half of the month does **not** use an external CTF platform. Its targets are systems you build and run yourself: a local model under Ollama, a small application on a hosted API under your own key, and one open-source LLM application you choose and deploy. Those are authorized because they are your own deployments, not because a platform's terms authorize them. See Labs 11.4 and 11.5 for the scope rules and `AI-ETHICS.md` rule 5 for the line between studying these attacks and weaponizing them. Nothing in the AI labs is a license to test any AI system you do not own.

## A reminder

These two games are the only external targets this month, and they are legal because their terms of use say so. Everything else you test this month is infrastructure you own. If you ever find yourself about to point a tool at something that is neither, stop: that is the exact decision `SAFETY.md` exists to govern, and getting it wrong in the cloud is the same federal exposure as getting it wrong anywhere.
