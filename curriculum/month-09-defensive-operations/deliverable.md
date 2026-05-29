---
title: "Deliverable"
parent: "Month 9 - Defensive Operations (Blue Team)"
grand_parent: Curriculum
nav_order: 91
---

# Month 9 Deliverable: The Incident-Response Report

## What you produce

A professional incident-response report on the single case you investigated in Lab 9.4, formatted the way a real IR report is: a confidentiality notice, an executive summary, an incident overview with stated scope and limitations, a narrative and timeline, a list of indicators of compromise, and recommendations. This is the portfolio artifact the month builds toward, and it is the direct ancestor of the Capstone B report in Month 12. A hiring manager for a SOC or detection role will read it. It should read like the work of someone who could be handed a real incident and trusted to write it up for both the executive who funds the response and the engineer who carries it out.

It lives in your lab notebook (or in a `writeups/` directory in your work repository, with a link from the notebook), as `month-09-ir-report.md`. The incident itself comes from Blue Team Labs Online or LetsDefend. The analysis and the writing are yours.

## Required structure

A real IR report serves two readers at once, and its structure reflects that.

Above everything else, the report opens with a **confidentiality and handling notice**: one line, at the very top, marking the report confidential to its intended recipient (for example, "Confidential. For the recipient and the response team only."). A real incident report always carries one, because it routinely contains indicators, affected systems, and account names that should not circulate freely. On a training-platform investigation this is practice, not a real classification, but its presence is what a hiring manager who has seen real deliverables looks for. This notice is **introduced here in Month 9 and deepened in Capstone B**, which requires the same marking on a longer report.

After that one-line notice, the body must contain, in this order:

1. **Executive summary.** Half a page at most, written for a decision-maker who will read nothing else. What happened, in plain language; when; what the impact was or could have been; what you recommend at the highest level. No jargon a non-technical executive would not know, or jargon defined in one clause. If your favorite non-technical relative cannot follow it, it has failed at its one job (the same test as the Month 1 deliverable).

2. **Incident overview and scope, with stated limitations.** What system or environment the incident occurred in, how it was detected (which alert or observation started the investigation), the time window, and the boundaries of what you investigated. State plainly that the incident was investigated on a training platform (Blue Team Labs Online or LetsDefend). The report is a professional artifact, not a claim of a real-world engagement. Then add a short **scope and limitations** note: what the investigation could and could not establish, given the log sources you actually had, the time window you could see, and the blind spots (a host with no logging, a gap in the captured data, an artifact you could not recover). An investigation that states its own blind spots reads as professional; one that implies it saw everything does not. You practice this limitations habit here in lighter form; Capstone B requires a fuller investigation-bounds section.

3. **Timeline.** A chronological reconstruction of the attack. Each entry has a timestamp, the event, the evidence source (which log or artifact establishes it), and its significance. The timeline is the spine of the report; a reader should be able to follow the attack from initial access to impact through it alone. Include your reasoning where an entry depends on inference, not just raw log lines.

4. **Technical analysis.** The narrative the timeline summarizes: how the attacker gained access, what they did, what they touched, what they took or damaged, and how they tried to persist or move. Map the key behaviors to MITRE ATT&CK tactics and techniques (with technique IDs). This is the section the responding engineer reads.

5. **Indicators of compromise.** A clean, labeled list: hashes, IP addresses, domains, file paths, account names, and any other genuine indicators of this incident, each annotated with what it indicates and where you observed it. Ruthlessly exclude incidental noise; an IOC is an indicator of this compromise, not an inventory of the environment. A responder must be able to act on this list without breaking production.

6. **Recommendations.** Organize them in two tiers, immediate and longer-term, plus two short judgment notes the section must include.

   - **Immediate: containment, eradication, and recovery.** The actions a responder should take now. State a containment-timing call here: at the point the foothold was confirmed, isolate the host now or observe and collect, and name the tradeoff you weighed (stopping the attacker versus preserving volatile evidence versus business disruption).
   - **Evidence preservation, if your call was to observe and collect.** Say in one or two sentences how you would collect so the evidence survives later scrutiny. Capture in **order of volatility** (memory and live network connections first, then disk, then logs, because the most volatile evidence is gone the moment you pull the plug). **Hash every artifact you acquire and record the hash**; this is the `shasum` habit from Month 4 ("hash a carved file; never run it"), now turned toward proving an acquired artifact has not changed. Keep a one-line **chain-of-custody** note per item: what you collected, when, who collected it, and where it is stored. This discipline starts here in Month 9 and is deepened at Capstone B. It is not a forensics course, so a short, correct note is the bar, not a full forensic procedure.
   - **Escalation and notification judgment, in one sentence.** State whether this incident, as scoped, would plausibly trigger a regulatory or contractual notification obligation, and which non-technical stakeholders (legal, communications, leadership) you would escalate to and when. This is a judgment prompt, not legal advice and not a legal analysis. The point is that you have reasoned at least once about the reporting clock that runs in parallel with the technical response.
   - **Longer-term: controls and detections.** The controls and, specifically, the detections that would have caught this incident earlier or prevented it. Tie at least one recommendation to a concrete detection you could write (ideally referencing the Sigma work from Lab 9.2). "A detection for technique Txxxx on this log source would have raised this at initial access" is the strongest kind of recommendation, because it closes the loop between the analyst and the engineer roles you built this month.

7. **AI Provenance appendix.** As in every deliverable from Month 5 onward, in the standard format: which AI tool, what you asked, what was generated, what you verified, what you discarded. For this report the honest provenance is narrow, and you should say so plainly. The investigation and every finding are yours. AI, if used, touched only unfamiliar-vocabulary lookups during the investigation and prose tightening on the draft, and introduced no finding, indicator, or conclusion. See `AI-ETHICS.md` on disclosure.

## Specification

- **Length:** roughly 6 to 12 pages of substance. Long enough to tell the story completely; short enough that every paragraph earns its place. The Capstone B report in Month 12 is longer (10 to 15 pages); this is its training run.
- **Two audiences, one document.** The executive summary serves the decision-maker; the technical analysis and IOCs serve the responder. A report that serves only one has missed the form.
- **Evidence-bound.** Every finding, every timeline entry, every IOC traces to something you actually observed in the investigation. No claim rests on what a walkthrough told you or what AI smoothed in. If you cannot point to the evidence, the claim does not go in the report.
- **No flags, no answer keys.** The platforms gate progress with flags and answers. Those are feedback for you, not content for the report. Do not include platform flags or the platform's expected answers. Document your method and your evidence-based findings. (And, as always, the tutor never confirms a flag; do not paste one to it.)
- **No em dashes,** to match the house style of the course's prose. Use commas, colons, parentheses, or semicolons.

## Acceptance criteria

- The report carries a one-line confidentiality and handling notice at the top, and contains all seven sections in order, with the executive summary readable by a non-technical decision-maker.
- The scope section states the investigation's limitations: the log sources available, the time window, and the blind spots.
- The timeline is chronological, sourced (each entry names its evidence), and complete enough to follow the attack from initial access to impact.
- Key behaviors are mapped to MITRE ATT&CK techniques with IDs.
- The IOC list is clean and labeled, free of incidental noise.
- The recommendations include both immediate actions and longer-term detections, with at least one tied to a concrete detection you could author.
- If the containment call was "observe and collect," the recommendations state how to collect defensibly (order of volatility, hashing acquired artifacts, a one-line chain-of-custody note).
- The recommendations include a one-sentence escalation and notification judgment (whether a reporting obligation plausibly applies, and who you would escalate to).
- The AI Provenance appendix is present and honest about the narrow role AI played.
- Every finding traces to evidence from your own investigation.

## Verification

The tutor confirms the structure, that the executive summary is genuinely non-technical, and that the IOC list is disciplined rather than padded. Then it runs the verification ritual: it picks one finding or one timeline entry and asks you to walk through the evidence that establishes it, from memory, with no AI session and no platform answer key open. This is the interview question "talk me through how you know the attacker did this." If every finding is one you can defend from the evidence, the report stands. If one turns out to be borrowed from a walkthrough or introduced by AI, the report returns until it is yours.

## Why this is the Month 9 deliverable

The IR report is the proof that you can do the alert-consumer half of defensive work and communicate it. Anyone can run a SIEM query. The hire-able skill is reconstructing an incident from evidence under uncertainty and writing it up so that an executive can decide and an engineer can act. It is at once a portfolio piece and the rehearsal for Capstone B. The recommendations section, where your analyst findings turn into detections you would author, is where this month's two roles meet, and it is the section that tells a hiring manager you understand both sides of the glass.

## How to know it is done

- `month-09-ir-report.md` committed, with the confidentiality notice and all seven sections, in the required structure.
- Four lab notebook entries committed, each with a complete AI Provenance section; the Lab 9.2 entry includes a false-positive analysis for every AI-drafted rule.
- The report's findings are all defensible from your own investigation evidence.
- `.tutor/lab-log.md` shows all four Month 9 labs logged.
- `.tutor/progress.md` updated to "Month 9 complete; ready for Month 10."
