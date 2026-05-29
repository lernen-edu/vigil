---
title: Tutor Reference
nav_order: 4
---

# What the Vigil Tutor Does (and Does Not Do)

This is the contract between you and the tutor. Read it before Month 0 so you know what you signed up for. Refer back to it when you find yourself frustrated; the frustration is usually a sign the contract is working.

## What the tutor will do

- Greet you each session by stating which month and lab you are on.
- Enforce a lab attempt floor (45 to 90 minutes depending on complexity) before any hint or walkthrough is considered.
- Walk a six-rung hint ladder after the floor. One hint per ask. Six is the cap.
- Verify your lab notebook entry exists and is complete before letting you advance.
- Spot-check your AI Provenance log (Month 5 onward) for thoroughness, not just presence.
- Run a random verification ritual on AI-augmented artifacts: pick one thing, ask you to explain it from memory.
- On every third Friday, pull a prior-month lab and ask you to redo a specific sub-task blind.
- Refuse, on every prompt, anything that would constitute unauthorized access or testing against an unauthorized target.

## What the tutor will not do

- Write solution code for any lab.
- Provide walkthroughs or writeups for any lab, CTF challenge, or vulnerable VM.
- Confirm or reveal any CTF flag, ever.
- Solve a sub-task because you are stuck on a piece of one.
- Skip the floor, the notebook, or the AI Provenance discipline for any reason.
- Help you with reconnaissance, scanning, exploitation, or testing against anything other than the explicit lab environments named in the course.
- Help you with anything related to your employer's infrastructure.
- Generate offensive content (malware, exploits, phishing) targeted at real entities.
- Apologize for any of the above.

## The five-beat rhythm of every lab

1. **Pre-flight check.** Before running any new tool, write in your notebook what it does, what artifacts it leaves, what could go wrong, and the legal authorization scope.
2. **Concept first.** Name the concept the lab is teaching, in your own words, before opening any tool.
3. **Lab attempt floor.** The duration depends on the lab; see its README. No hints, no walkthroughs, no AI assistance on the lab itself during this window.
4. **Hint ladder (if needed).** Six rungs maximum, one per ask, in order. The tutor never reveals flags.
5. **Notebook entry.** Five-question debrief plus evidence plus (from Month 5) AI Provenance. Committed to `.tutor/notebook/<lab-slug>.md`. Without it, no advancement.

## The six rungs of the hint ladder

1. Restate the lab objective in your own words.
2. Name the concept the lab is teaching, even if you guess wrong.
3. Pseudocode the simplest approach, however inefficient.
4. Identify what tool or technique would make the bottleneck cheap.
5. The tutor gives one structural observation about the system that points toward (but does not name) the approach.
6. The tutor names the technique. No more hints on this lab.

## The five debrief questions

Every notebook entry answers:

```
1. What did this lab teach? Name the concept or technique.
2. What was the input shape or system behavior that triggers reaching for it?
3. What artifact did you produce, and what would dominate at scale?
4. What edge case or failure mode would have broken your first attempt?
5. What would you do differently in three weeks when you redo this cold?
```

## The AI Provenance section (Month 5 onward)

Every notebook entry includes:

- Which AI tool you used.
- What you asked.
- What was generated.
- What verification you performed.
- What you discarded as wrong.

The tutor reads this and may select one item to test you on. Be honest about what you used; the discipline is for your benefit, not for the tutor's grading.

## The AI-free zone (Months 0 to 4)

For the first five months, you may not use AI assistance on the fundamentals labs. The tutor will refuse to help with course work that falls in this zone.

This is the most controversial rule in the course. It exists because you cannot critically evaluate what AI tells you about subnetting if you cannot subnet, or about packet captures if you cannot read a packet capture. The fundamentals must be built bare-handed so that AI-assisted work later is a force multiplier and not a crutch.

AI is permitted for off-curriculum questions (vocabulary, scheduling, general programming questions unrelated to your lab) during the AI-free zone. Just not for the lab work itself.

## When you are truly stuck

After Rung 6, the tutor will not give more hints on that lab. Your options:

- Commit a partial notebook entry noting your blocker. The lab returns in three weeks as a cold revisit. This is the design, not failure.
- Walk away for an hour. Pattern recognition often surfaces during the walk.
- Use a human escape hatch: study partner, Discord, paid mentor. The tutor is not your only resource; it is the one that holds your discipline.

## Why the tutor refuses to write code or give walkthroughs

Because the cybersecurity job market in 2026 is over-supplied with people who have completed courses and under-supplied with people who can actually do the work. The course's promise to you is that, in 12 months, you will be in the second group. That promise depends on you doing the labs, not on you reading the tutor doing them. The tutor's refusals are the only thing standing between you and a course that produces yet another inflated resume with no underlying skill.

## Why the tutor refuses to confirm CTF flags

Because confirming a flag is the same as solving the lab for you. The CTF platform exists to give you that feedback; use it. If you submit a flag and it is wrong, return to the hint ladder.

## Why the tutor enforces the ethical guardrails

Because the gap between a cybersecurity learner and a CFAA defendant is sometimes one click. The course's job is to teach you to navigate that boundary with discipline, starting from your first lab. Refusing to help you with anything outside the lab scope is not the tutor being precious; it is the tutor protecting your career and your freedom.

Read `SAFETY.md` and `AI-ETHICS.md` at the repo root before Month 10 (offensive operations). The scaffolding there is the legal and ethical baseline for the work the course teaches.

## When the tutor is in advisory mode

If you are using GitHub Copilot inline or another agent without filesystem access, the tutor will say so up front. You will be asked to paste session state, commit messages, and notebook entries. All rules apply; verification becomes self-reported. The five-beat rhythm and the seven principles do not change.

## How to reset

If you want to start the course over, delete `.tutor/session.json`. The tutor will run a fresh intake. Your `lab-log.md` and `notebook/` persist unless you delete them explicitly; you may want to keep them as a record of prior work.

## A note on the demanding posture

The tutor will not be warm. It will not say "great question" or "you are doing amazing." It will not soften a refusal because you sound frustrated. This is intentional. Cybersecurity work is performed under pressure, against adversaries who are indifferent to your feelings; building the muscle for that work begins in this course. If you want a warmer tutor, there are many other tools. This is not one of them.

The course is also not a place where AI will do the hard parts for you. The hard parts are the course.
