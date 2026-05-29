---
title: "Deliverable"
parent: "Month 6 - Windows Security"
grand_parent: Curriculum
nav_order: 91
---

# Month 6 Deliverable: The Windows Baseline

## What you produce

A `windows-baseline.md` writeup documenting the hardened configuration of your domain controller and your member workstation, with screenshots of the relevant settings, every choice traceable to a primary source. It lives in your lab notebook this month and graduates to your portfolio `writeups/` directory by the end of the course.

This is the artifact a hiring manager reads to decide whether you can be handed a Windows estate. It demonstrates two things at once: that you can harden a Windows environment, and that you can justify each decision from authoritative documentation rather than from a checklist you copied. The second is what separates a junior who pasted a baseline from one who understands it.

## Specification

- **Scope:** both the domain controller (Lab 6.1) and the member workstation (Labs 6.1 and 6.2). Treat them separately where their hardening differs (a domain controller's surface is not a workstation's), and say why it differs.
- **Structure:** for each hardening decision, document four things:
  1. **The setting:** what you configured, named precisely (the policy, the registry value, the service state, the account configuration), with a screenshot showing it in place.
  2. **The justification:** why this setting, traced to a primary source. The source must be a Microsoft Security Baseline, the CIS Benchmark, Microsoft Learn, or another primary reference, cited by name. "Because it is more secure" is not a justification; "the CIS Benchmark for Windows Server recommends this because [the specific threat it mitigates]" is.
  3. **The threat it addresses:** what attack or weakness this closes, in one or two sentences. Where it maps to one of this month's conceptual attacks (pass-the-hash, kerberoasting, golden ticket, lateral movement) or to a persistence surface you saw in Lab 6.2, say so.
  4. **The trade-off:** what this setting costs (functionality, manageability, compatibility), because every hardening choice costs something and a defender who cannot name the cost has not thought it through.
- **Coverage:** at minimum, the baseline addresses account and privilege hardening (including why your daily account is not a domain admin), authentication and logging configuration, service and attack-surface reduction, and the logging and telemetry posture (tie this to the Sysmon work from Lab 6.2). The logging posture must include the built-in auditing you enabled in Lab 6.2 Task 3: Audit Process Creation with the command line included (Event ID 4688 carrying the CommandLine field) and PowerShell Script Block Logging (Event ID 4104), each justified from a primary source and each with its trade-off named (command lines can carry secrets into the log; script-block logging adds volume). This is the host telemetry your Month 9 detections depend on, so the baseline is where you write down that you turned it on and why. You do not need to apply every setting in a full baseline; you need a defensible, coherent subset you understand completely, with the reasoning shown.
- **Screenshots:** every setting claim is backed by a screenshot showing the actual configuration on your machine, not a stock image from documentation. The screenshots are evidence you did the work, the same way command output is evidence elsewhere in the course.
- **Length:** as long as the settings you chose require, and no longer. A focused baseline of a dozen well-justified settings beats forty copied ones. Quality of justification over quantity of settings.
- **Constraint:** no em dashes, to match the house style; use commas, colons, parentheses, or semicolons. Define any acronym the first time it appears (SID, GPO, SPN, and the rest), the same discipline as the Month 1 writeup.

## The AI Provenance requirement

Because this is an AI-augmented month, the baseline carries an **AI Provenance** section, the same format as your notebook entries. It documents where AI helped you orient to a term or artifact and where you verified that orientation against Microsoft documentation. Critically, it must be honest about the line this month draws: AI was used to **explain** vocabulary, not to **decide** configuration. If your provenance log shows AI making security decisions for you, the deliverable fails on its own terms, because the entire premise is that the decisions are yours, sourced from primary baselines. Document the terms AI clarified, the Microsoft or CIS source you confirmed them against, and anything you discarded as wrong.

## Acceptance criteria

- `windows-baseline.md` covers both the domain controller and the member workstation, with their differences called out and explained.
- Every hardening decision has all four parts: the setting (with screenshot), the justification (with a named primary source), the threat it addresses, and the trade-off.
- Every justification traces to a primary source (Microsoft Security Baseline, CIS Benchmark, Microsoft Learn, or equivalent). No blog or AI citation stands in for a primary source.
- The baseline ties at least one decision to the Lab 6.2 telemetry work (your logging posture) and at least one to a conceptual attack from this month.
- The logging posture documents process-creation command-line auditing (4688 with CommandLine) and PowerShell script-block logging (4104) as enabled, each with a primary source and a named trade-off, so the host telemetry Month 9 relies on is present and justified.
- An AI Provenance section is present, honest about the orientation-not-decisions line, with verification against Microsoft documentation.
- No flags, no room answers, and no reminder to paste anything to the tutor anywhere in the document; this is a configuration writeup, not a CTF submission.
- No em dashes; acronyms defined on first use.

## Verification

The tutor will not write this for you, and it will not tell you which settings to choose; that is the configuration-decision line this month holds. It verifies the deliverable two ways. First, it confirms the structure: every setting has its justification, threat, trade-off, and screenshot, and every justification cites a primary source. Second, it runs the verification ritual: it picks one setting at random and asks you to explain, from memory with your AI session and the documentation closed, what the setting does, what threat it addresses, and what it costs. If you chose and justified the setting yourself from the baselines, this is straightforward. If you copied it, it is not, which is the design.

## Why this is the Month 6 deliverable

Hardening is the defender's core craft, and the ability to justify a configuration from authoritative sources is what a security team trusts. Anyone can apply a baseline; the practitioner can tell you why each line is there, what it stops, and what it breaks. This deliverable is where you prove that on Windows, the platform most of your future estate runs on. It also rehearses the documentation-grounded discipline that Month 8's crypto work and the Month 12 capstone reports demand: decisions traced to primary sources, AI used to orient and never to decide, every claim defensible cold.

## How to know it is done

- `windows-baseline.md` committed, covering the domain controller and the member workstation, with screenshots and per-setting justification traced to primary sources.
- The three lab notebook entries committed, each with a complete AI Provenance section.
- `.tutor/lab-log.md` shows all three Month 6 labs logged.
- The cold-revisit week's sub-tasks completed and logged.
- `.tutor/progress.md` updated to "Month 6 complete; ready for Month 7."

If any setting cannot be traced to a primary source, or any screenshot is missing, the month is not done. The justification is the deliverable; the settings are just its subject.
