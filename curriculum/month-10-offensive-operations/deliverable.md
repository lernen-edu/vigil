---
title: "Deliverable"
parent: "Month 10 - Offensive Operations (Red Team Intro)"
grand_parent: Curriculum
nav_order: 91
---

# Month 10 Deliverable: The pentest-portfolio Reports

## What you produce

A `pentest-portfolio/` directory containing **three penetration-test reports**, each documenting one box you took end to end in Lab 10.3, each formatted as a professional engagement report. These are the artifact a hiring manager reads to decide whether you can both think like an attacker and communicate like a consultant. They are produced primarily in Lab 10.3. This file specifies what they must contain.

The reports contain **methodology only and no flags**. A flag is a token a CTF platform uses to confirm you solved a box; it has no place in a professional report and no place in your portfolio. The report demonstrates how you found and exploited each finding, not that you grabbed a string.

## The scope and authorization rule for the targets

Every report's target must be a legal target under `SAFETY.md`: a retired HackTheBox machine, or a VulnHub VM you downloaded and ran on your own hardware. The recommended composition is at least one of each, so the reports you make public rest on a target with no writeup restriction.

The writeup-permission rule is load-bearing for any report you publish:

- **Retired HackTheBox machines:** writeups permitted. Active HTB machines: writeups not permitted; do not publish one.
- **VulnHub VMs:** no writeup restriction.

Each report's Scope section states the authorization basis explicitly: which legal-target category, and (for HTB) confirmation the box is retired. If you cannot state the authorization basis, the report is not done.

## Required structure of each report

Each report is a standalone professional document. Use this structure; it mirrors NIST SP 800-115 and PTES and is the format a real engagement produces.

```
pentest-portfolio/
├── README.md                 # What this portfolio is; the AI disclosure footer
├── report-01-<box>.md
├── report-02-<box>.md
└── report-03-<box>.md
```

Each `report-NN-<box>.md` contains, in order:

1. **Confidentiality and handling notice.** One line at the top of the report stating that it is confidential to the named recipient and intended only for them (for example, "This report is confidential and intended solely for <recipient>. Do not redistribute without authorization."). A real client report always carries one. For a portfolio piece on a lab box, write the line as if the box owner were a paying client; it is the habit that matters, and it signals to a hiring manager that you have seen a real deliverable.
2. **Executive summary.** A short, non-technical paragraph: what was assessed, the headline result (for example, "full compromise was achieved through an unpatched service and a sudo misconfiguration"), and the overall risk posture. A manager reads only this; write it for them.
3. **Scope and authorization.** The target, the **engagement window (the dates you tested, start and end)**, the authorization basis (legal-target category; retired status for HTB), what was in scope (the box), what was explicitly out of scope (everything else), and the rules of engagement you set for yourself. The dates are not decoration: a real report is always bound to a window, because a system's security on the day you tested is not a promise about the day after.
4. **Assumptions and Limitations.** A short section stating the boundaries of the assessment, the way every real client report does. Cover at least: the engagement was time-boxed (say to roughly how many hours), so the testing was not exhaustive; whether you tested credentialed or uncredentialed; what was deliberately not tested (denial-of-service, social engineering, physical access, anything out of scope); and the load-bearing sentence that **the absence of a finding is not proof that no weakness exists**, only that none was found in the time and scope available. This section is what separates a candidate who has read a real report from one who has only written CTF writeups.
5. **Methodology.** The engagement narrated by phase: reconnaissance, enumeration, exploitation, foothold, privilege escalation. Enough detail that a competent reader could reproduce your path. This is where you show tool selection and, for at least one report, a deliberate manual-versus-automated decision with the reasoning. No flags.
6. **Findings.** Each finding as its own subsection: a title, a severity rating with an explicit rationale, the affected component, the evidence (your own methodology, redacted of any flag), and the impact. Severities use one consistent scheme across all three reports (see below).
7. **Recommendations.** For each finding, a specific remediation a defender could act on: not "patch the system" but "upgrade <service> to a version that addresses <weakness>; restrict the sudo rule on <binary> to specific arguments." Tie each recommendation to its finding. A real engagement does not end at report delivery: it normally includes a retest (remediation verification) once fixes are in. You will not exercise a retest in this course, but note that it exists, so you know the engagement lifecycle does not stop when you hand over the document.
8. **AI Provenance appendix.** Required. Same format as your notebook provenance: which AI tool, what you asked, what was generated, how you verified it, what you discarded. Because this month's pattern is recon synthesis only, the appendix should make clear that the findings, the severities, the recommendations, and the prose are your own work, and that AI was used only to summarize recon output you gathered yourself.

## The severity scheme

Pick one defensible severity scheme and apply it identically across all three reports. The simplest defensible approach is impact times exploitability, or a published rubric such as CVSS. Whatever you choose:

- State the scheme once, in each report or in the portfolio README, and apply it consistently.
- For each finding, give the rationale, not just the label. "High: the service is reachable pre-authentication and grants code execution, so exploitability and impact are both high" is a rating you can defend. "High" alone is not.
- Inconsistent severity across the three reports is the most common amateur tell; consistency is part of the deliverable.

## Acceptance criteria

- **Three reports**, each following the structure above, each documenting one box from Lab 10.3.
- **Each report carries** a confidentiality and handling notice and an Assumptions and Limitations section.
- **Each report's Scope section** states the engagement window (dates), the authorization basis, and (for HTB) retired status.
- **No flags** anywhere in any report or its history. If a flag appears, the deliverable fails until it is removed.
- **A consistent severity scheme** applied across all three, with a stated rationale per finding.
- **Recommendations** tied to findings and specific enough to act on.
- **An AI Provenance appendix** in each report, confirming the findings and severities are your own.
- **The public reports are of retired HTB boxes or VulnHub VMs.** A public report of an active HTB box fails the deliverable.
- **A portfolio README** with an AI disclosure footer (AI used for recon synthesis only; findings, analysis, and prose by the author), mirroring the disclosure discipline in `AI-ETHICS.md`.
- **No real credentials, hashes, keys, or out-of-scope content** anywhere in the directory or its history.

## Verification

The tutor confirms each report has all required sections (confidentiality notice, executive summary, scope and authorization with engagement dates, assumptions and limitations, methodology, findings, recommendations, AI Provenance appendix), no flags, a consistent severity scheme, and that the public reports rest on retired HTB boxes or VulnHub VMs. Then it runs the verification ritual: it picks one finding from one report and asks you to explain the severity rating from memory and reproduce the methodology that found it, with your AI session closed. It will also ask you to state the authorization basis for one target. The deliverable is not done until you can defend a finding's severity and trace it to your own work.

The tutor will not confirm any flag at any point, and a report that records one is rejected on sight.

## Why this is the Month 10 deliverable

The penetration-test report is the artifact that gets a pentester hired and the artifact that gets a pentester paid. Anyone can follow a walkthrough to root a box; far fewer can document an engagement so a client understands what was found, how bad it is, and what to do about it. These three reports are the proof you can do the harder half. They also feed directly into the Month 12 capstone, whose Capstone A is a full pentest report of the same professional shape, scaled up. Build the template here so the capstone is an expansion, not a first attempt.

## How to know it is done

- `pentest-portfolio/` holds three reports, each with a confidentiality notice, executive summary, scope and authorization (with engagement dates), assumptions and limitations, methodology, severity-rated findings, recommendations, and an AI Provenance appendix.
- No report contains a flag; public reports are of retired HTB boxes or VulnHub VMs.
- The severity scheme is consistent across all three, with rationale per finding.
- The portfolio README carries the AI disclosure footer.
- The four lab notebook entries are committed, each with a complete AI Provenance section.
- The cold-revisit week's cross-month sub-tasks are completed and logged.
- `.tutor/progress.md` updated to "Month 10 complete; ready for Month 11."
