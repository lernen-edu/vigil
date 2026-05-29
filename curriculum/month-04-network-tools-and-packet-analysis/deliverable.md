---
title: "Deliverable"
parent: "Month 4 - Network Tools and Packet Analysis"
grand_parent: Curriculum
nav_order: 91
---

# Month 4 Deliverable: Five PCAP Analysis Reports

## What you produce

Five packet-capture analysis reports, two to three pages each, each written as if for the SOC analyst coming on for the next shift. They are the artifact of Lab 4.1 and the proof that you can do the central skill of this month: take an unfamiliar capture, read it, and hand a colleague a finding they can act on without re-reading the capture from scratch.

These reports live in your lab notebook. They may sit inside the Lab 4.1 notebook entry, or in a `pcap-reports/` directory linked from it. Either is fine, provided the notebook entry points to all five. Together with the three lab notebook entries, they are what the tutor checks before advancing you to Month 5.

## Why this is the Month 4 deliverable

The job of a SOC analyst, an incident responder, or a network-forensics examiner is not only to see what happened in traffic. It is to communicate it to the next person in the chain. A shift handoff is a real artifact in a real SOC: the analyst going off shift tells the one coming on what is live, what was investigated, and what to watch. A finding nobody can act on is half a finding. This deliverable makes you produce the seeing and the saying, because the saying is what gets you hired and what keeps an incident moving when you are not in the room.

It is also the bridge to Month 5. The third debrief question (what would dominate at scale) lands hard here: five captures by hand is feasible, five hundred is not, and that is the problem Python tooling solves. You write these five by hand so that when you automate in Month 5, you automate something you understand.

## The voice: a shift handoff, not a textbook

Write each report to one specific reader: the analyst starting the shift after yours. That reader has the same skills you do, no more context than you are about to give them, and limited time. That reader shapes every choice:

- **Lead with what matters.** Open with a one-paragraph summary: what happened, to which host, and how worried they should be. The next analyst should be able to read the first paragraph and know whether to keep reading now or after their coffee.
- **Prioritize.** Not every packet is equally interesting. Put the compromise before the noise. If a host was scanned and then beaconed to a command-and-control server, the beacon is the headline and the scan is context.
- **Be concrete.** "Suspicious traffic" tells the next analyst nothing. "Host 10.0.0.5 sent an HTTP POST to evil.example every 60 seconds starting 14:02:11 UTC, payload base64, consistent with C2 check-in" tells them where to look and what to pivot on.
- **Mark your confidence.** You will not be certain about everything. Say so. "Likely credential theft (cleartext POST to a login form over HTTP); not confirmed whether the credentials were valid" is honest and useful. A confident assertion you cannot support is worse than a marked uncertainty.
- **Give pivots.** End with the indicators a colleague can act on: addresses, domains, URLs, user-agents, file names, and hashes, with the times they appeared. These are what the next analyst feeds into the SIEM, the firewall, or the threat-intel lookup.

This is not academic prose and it is not a packet-by-packet transcript. It is operational writing: dense, ordered by importance, and actionable.

## Required structure for each report

Each of the five reports contains, at minimum:

- **Summary (one paragraph).** What happened, the primary host or hosts, and a severity or worry level. Written so the next analyst gets the gist from this paragraph alone.
- **Scope of the capture.** What the capture covers: the time window (from the packet timestamps), the hosts present, and the protocols seen (the Protocol Hierarchy view is your source). One short paragraph or a small table.
- **Timeline.** The significant events in order, each with a packet-derived timestamp. This is the spine of the report. Not every packet; the events that matter.
- **Analysis.** What you concluded and the evidence for each conclusion, referencing specific packets, streams, or Statistics views. This is where you show your work: the filter you used, the stream you followed, the field that gave it away.
- **Indicators of compromise.** A list a colleague can pivot on: IPs, domains, URLs, user-agents, file names, file hashes (computed from carved objects, never by executing them), with first-seen times. Format it so it could be copied into a ticket.
- **Confidence and gaps.** What you are sure of, what you are inferring, and what the capture does not let you determine. Naming the gaps is a senior move; it tells the next analyst where to dig.

## Acceptance criteria

- **Five reports**, each two to three pages, each on a different capture chosen for variety (not five of the same traffic shape).
- **The shift-handoff voice** throughout: summary-first, prioritized, concrete, with marked confidence and actionable indicators.
- **Every claim is grounded in the capture.** A reader with the same capture could find the packets behind each conclusion. Timestamps are packet-derived, not invented.
- **Indicators are real and pivotable**, drawn from the capture, formatted for a colleague to use.
- **No CTF flags or platform answers** are reproduced. These captures come from analyst-training sources, and the report is a finding, not an answer key.
- **No executed malware.** Any hash in a report was computed from a carved file, never by running it. Say so where relevant.
- **No em dashes**, to match the house style of the course's prose. Use commas, colons, parentheses, or semicolons.
- **No AI assistance.** Month 4 is in the AI-free zone. These reports are written entirely by you, from your own reading of the captures. There is no AI Provenance section this month.

## Verification

The tutor will not write these for you. It verifies by picking one report and one claim in it, then asking you to defend the claim from the capture: "you wrote that this host beaconed every sixty seconds; open the capture and show me the packets that establish the interval." A report grounded in real analysis survives this trivially; a report that hand-waved does not. If a claim cannot be defended from the capture, the report returns for actual analysis.

## How to know it is done

- Five reports committed, each meeting the structure and acceptance criteria above.
- The Lab 4.1 notebook entry committed and linking to all five reports.
- The Lab 4.2 and Lab 4.3 notebook entries committed.
- `.tutor/lab-log.md` shows all three Month 4 labs logged, and the third-Friday cold revisit recorded.
- `.tutor/progress.md` updated to "Month 4 complete; ready for Month 5."

If any report cannot be defended from its capture, the deliverable is not done. The tutor will not advance you to Month 5, where AI unlocks, until the AI-free analysis foundation is solid. Being able to judge AI output later depends on the reading you did by hand here.
