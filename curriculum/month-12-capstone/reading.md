---
title: "Reading"
parent: "Month 12 - Capstone"
grand_parent: Curriculum
nav_order: 90
---

# Month 12 Reading

Light by design. By the capstone, your main resource is your own eleven months of notebooks: the PCAPs you annotated, the Sigma rules you wrote, the boxes you rooted, the tools you built. The list below points to the reporting standards and disclosure norms that turn good technical work into a deliverable a hiring manager respects. Read the report-craft material before you write a word of Capstone A or B.

## Report craft (read before writing A or B)

- _guide_ The PTES (Penetration Testing Execution Standard) Reporting section. The canonical structure for a pentest report: executive summary, methodology, findings with severity, remediation. Capstone A follows this shape.
- _standard_ FIRST CVSS specification (current version). You will assign severity to findings; do it with a defensible rubric, not a vibe. Read enough to score a finding and explain the vector string.
- _standard_ NIST SP 800-61, "Computer Security Incident Handling Guide." The incident response lifecycle (preparation, detection and analysis, containment and eradication and recovery, post-incident activity) that Capstone B is structured around. You met this in Month 9; re-read the lifecycle section before writing the report.
- _reference_ Any one professional pentest report template or published sample report (several firms publish sanitized examples). Read it for structure and tone, not to copy; your findings are your own.

## Incident response writing (read before B)

- _reference_ A published incident report or breach writeup in the public domain (vendor post-incident reports and CERT advisories are good models). Read for how a timeline is presented, how IOCs are tabulated, and how recommendations are tied to root cause.
- _docs_ Your own Month 9 IR report and SIEM. The Capstone B investigation runs in the SIEM you built; your Month 9 deliverable is the template you are now leveling up.

## AI disclosure (read before any Capstone D appendix)

- _required_ `AI-ETHICS.md` at the repo root, specifically the "Disclosure in deliverables" section. This is the standard Capstone D must meet. Re-read it; the appendix is the public-facing test of the provenance discipline you have practiced since Month 5.
- _reference_ `tutor-reference.md`, "The AI Provenance section," for the five-element format the appendix reuses.

## Scope and authorization (read before A)

- _required_ `SAFETY.md` at the repo root, specifically "The capstone special case" and "What counts as a legal target." The Capstone A authorization basis is written against this. Re-read it before you choose a target.
- _reference_ The HackTheBox terms on retired-box write-ups, or the VulnHub page for your chosen VM, whichever applies. You will cite the relevant one in your authorization basis.

## Public artifact craft (read before C)

- _reference_ Two or three well-regarded security writeups or blog posts in the style you intend to publish. Read for what makes a writeup useful to a stranger: a clear problem statement, reproducible steps, and an honest account of dead ends.
- _docs_ If your Capstone C is an open-source contribution, the target project's `CONTRIBUTING.md` and its issue tracker. Read the contribution norms before you open a pull request; a contribution that ignores the project's conventions wastes a maintainer's time and reflects poorly on you.

## A note on sources at the capstone

You are past the stage of needing tutorials. The reading here is reference material you consult while writing, not material you study before working. Your eleven months of notebooks are the real syllabus for this month; the capstone is where you prove you internalized them. When you cite a source in a capstone deliverable, cite a primary one (a standard, a CVE record, a vendor advisory, an RFC), never a blog that paraphrases it. By now that habit should be automatic; the capstone is where it shows.
