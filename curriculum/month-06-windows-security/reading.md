---
title: "Reading"
parent: "Month 6 - Windows Security"
grand_parent: Curriculum
nav_order: 90
---

# Month 6 Reading

Microsoft's own documentation is the primary source for this month, and it is also your verification source for every AI orientation question. Read the primary references before any blog or video. The whole point of the concept-orientation pattern is that you confirm AI's explanations against the documentation of record, so know where that documentation lives.

## Core (Windows and Active Directory, Microsoft primary sources)

- _docs_ Microsoft Learn: Active Directory Domain Services overview (what a domain, forest, and domain controller are; the foundation for Lab 6.1).
- _docs_ Microsoft Learn: "Install a new Windows Server forest" / the AD DS deployment guidance (the official promotion walkthrough; read this rather than a third-party tutorial for Lab 6.1 Task 3).
- _docs_ Microsoft Learn: DNS and Active Directory integration (why DNS is a hard dependency and why a domain controller resolves against itself).
- _docs_ Microsoft Learn: forest and domain functional levels (for your Lab 6.1 Task 3 justifications).
- _docs_ Microsoft Learn: Kerberos authentication overview and the ticket-granting service (the client, KDC, and service model; the conceptual ground under kerberoasting and golden-ticket).
- _docs_ Microsoft Learn: the Windows registry structure (hives, keys, values) and the run and service keys persistence abuses.
- _docs_ Microsoft Learn: Windows services and the Service Control Manager; scheduled tasks.

## Core (logging and telemetry)

- _docs_ Microsoft Sysinternals: the Sysmon documentation and its event reference (the authoritative list of event IDs and fields; your verification source for every Sysmon term in Lab 6.2).
- _docs_ Microsoft Learn: the Windows event-logging model (channels, providers, event IDs, structured event data) and the logon-type field with its values.
- _repo_ The SwiftOnSecurity sysmon-config repository and its README (the reference configuration you install in Lab 6.2, and the reasoning behind what it records and filters; read the README, do not just download the XML).

## Core (PowerShell as a security tool)

- _docs_ Microsoft Learn: PowerShell fundamentals and the object pipeline (output is objects, not text; a real departure from Bash).
- _docs_ Microsoft Learn: the PowerShell cmdlets for inspecting processes, services, scheduled tasks, and the event log; and PowerShell's own logging (script block logging, module logging), because the attacker uses PowerShell too.

## Hardening (for the deliverable; primary baselines only)

- _docs_ Microsoft Security Baselines and the Security Compliance Toolkit (Microsoft's own recommended configuration baselines for Windows Server and Windows client; a primary source you cite per setting in `windows-baseline.md`).
- _docs_ CIS Benchmarks for Windows Server and Windows (the other widely used baseline; free to download as PDFs after registration). Use these and the Microsoft baselines to justify each hardening choice; this is where your decisions come from, not from AI.
- _docs_ Microsoft Learn: securing domain controllers and the tiered administration / privileged-account model (why you do not make your daily user a domain admin).

## Attack concepts (conceptual only this month; primary references for what each does and leaves)

- _reference_ MITRE ATT&CK technique pages for pass-the-hash, kerberoasting (and the broader "Steal or Forge Kerberos Tickets"), golden-ticket, scheduled-task persistence, and lateral movement. Use these to orient and to verify; you study these techniques this month, you do not execute them against any target outside an authorized platform.
- _docs_ Microsoft Learn: Service Principal Names (SPNs) and how service tickets are requested (the precondition kerberoasting relies on).

## Interactive (authorized environments)

- _platform_ TryHackMe: the Windows Fundamentals rooms and the introductory Active Directory rooms (for Lab 6.3; the room targets are authorized for the activity by the platform's terms, and only those targets).

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read decision-tree question Q2 (could the output be wrong in a way you would not catch); it is the question that draws this month's line between orienting with AI and deciding with AI.

## A note on sources

When a lab asks you to justify a setting or verify an explanation, the source must be primary: Microsoft Learn, a Microsoft Security Baseline, the Sysmon documentation, a CIS Benchmark, or MITRE ATT&CK. A blog post, a forum answer, or an AI explanation is not a citation. Windows is the domain where AI most confidently invents registry paths, Group Policy names, and event IDs that do not exist; the documentation above is your defense, and the verification ritual is the test of whether you used it.
