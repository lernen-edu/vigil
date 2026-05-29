---
title: "Labs"
parent: "Month 6 - Windows Security"
grand_parent: Curriculum
nav_order: 50
---

# Month 6 Labs

Three labs, completed in order. Each builds the defender's view of Windows and Active Directory and feeds the hardened-baseline deliverable. The lab attempt floor, the concept-orientation AI pattern, and the mandatory AI Provenance log apply to every one (see the Month 6 README).

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 6.1 Domain Controller Setup | `lab-01-domain-controller-setup/` | 18 to 22 h | 90 min | A working AD domain (one DC, one joined workstation) and a map of what promotion changed |
| 6.2 Sysmon and Suspicious Activity | `lab-02-sysmon-suspicious-activity/` | 15 to 17 h | 90 min | Sysmon telemetry, self-generated suspicious events, and the skill of finding them by event ID |
| 6.3 TryHackMe Windows Path | `lab-03-tryhackme-windows-path/` | 12 to 14 h | 45 min per stuck task | Windows and Active Directory fluency, and a conceptual grounding for the common attacks |

Lab 6.1 carries the Apple Silicon hardware constraint (Windows Server is x86-64 only); read the Month 6 README's hardware note and `getting-started.md` Step 4 before you start it. Lab 6.3 carries the no-flag-confirmation habit: do not paste room answers or flags to the tutor; the platform confirms them, not the tutor. All three labs run only against your own VMs or platforms whose terms of use authorize the activity, per `SAFETY.md`.

Complete all three, commit a notebook entry for each, and write the `windows-baseline.md` deliverable (see `../deliverable.md`) before advancing to Month 7.
