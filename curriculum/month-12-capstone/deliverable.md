---
title: "Deliverable"
parent: "Month 12 - Capstone"
grand_parent: Curriculum
nav_order: 91
---

# Month 12 Deliverable: The Capstone Portfolio

## What you produce

Six artifacts. Five are tracks (A, B, C, E, F). The sixth (D) is a mandatory appendix that lives inside each of A, B, and C. A separate `RETROSPECTIVE.md` closes the course. All of it is your portfolio: the documents you put in front of a hiring manager to prove you can do the work, get it looked at, and defend it live, not just talk about it.

```
capstone/
├── capstone-a-pentest-report.pdf      # 15 to 25 pages, with Capstone D appendix
├── capstone-b-ir-report.pdf           # 10 to 15 pages, with Capstone D appendix
├── capstone-c/                        # the public written piece (required) and any optional second artifact
├── capstone-e-self-assessment.md      # written self-assessment after the timed mock screen
├── capstone-f/                        # resume, public portfolio-index page, profile pass
└── RETROSPECTIVE.md                   # reflection on the 12 months, with a named target role
```

Each track has its own full specification under `tracks/`. This document covers what is common across them: the authorization requirement that gates Capstone A, the AI Provenance appendix (Capstone D), the professional-report standard, and the retrospective.

Read this document, then read all five track files, before you start. The capstone rewards planning; learners who pick their targets and scope the tracks up front finish on time, and learners who improvise do not. A, B, and C are the work; F packages it for the role you name; E rehearses defending it live, so F and E come after A, B, and C are drafted.

## The written-authorization requirement (gates Capstone A)

This is the single hardest gate in the course, and it is hard on purpose. `SAFETY.md` states the rule the capstone enforces: **you may only test systems you clearly own or have explicit written permission to test.** Before any work on Capstone A, you produce a written **authorization basis** and commit it to your engagement notes. Before recon. Before a single scan. Before any tool touches the target.

The authorization basis is a short, dated document. It states:

1. **The exact target.** The specific retired HackTheBox box (by name and the date it retired), the specific VulnHub VM (by name, version, and the page you downloaded it from), or the specific environment you built yourself.
2. **The authorization basis.** Why you are legally permitted to test this target. For a retired HTB box: that HackTheBox explicitly authorizes write-ups of retired boxes, with a link to that policy. For a VulnHub VM: that it is a deliberately vulnerable VM published for this purpose, downloaded and run on your own hardware. For a self-built environment: that you own the host and the software.
3. **The scope.** What is in scope (the target VM and only the target VM) and what is explicitly out of scope (the HTB infrastructure itself, other learners' boxes, the VPN gateway, your own host's other services, anything on your home network).
4. **The engagement window, the date, and your name.** The dates during which you will test (the engagement window), the date you wrote the basis, and your name. The engagement window carries into the report's Scope section, because a real report always states when testing happened. This is the document a real engagement opens with. Practice writing it.

The tutor verifies this before it will discuss any work on Capstone A. It checks that the target is a legal target per `SAFETY.md`, that the authorization basis is real and not hand-waved, and that the scope is stated. **No authorization note, no engagement.** This is not bureaucracy; it is the exact discipline that separates a penetration tester from a defendant. The habit of writing scope and authorization before touching a system is one of the most valuable things this course gives you, and the capstone is where you prove you have it.

### Bug bounties are not recommended capstone targets

You may be tempted to use a public bug bounty program as your Capstone A target. A live target sounds more impressive. Do not. `SAFETY.md` says it and this document repeats it: bug bounty scoping is too narrow, the legal review depends entirely on one program's specific and changeable terms, and the risk of accidentally testing something out of scope is high. A single request to an out-of-scope asset can turn authorized research into a legal matter. A retired HTB box or a VulnHub VM gives you an unambiguous basis and an equally professional report. Pick the unambiguous target.

## Capstone D: the AI Provenance appendix (mandatory in A, B, and C)

Every capstone deliverable carries an "AI Provenance" appendix. This is the public-facing version of the AI Provenance section you have written in every notebook entry since Month 5. It follows the same format (`tutor-reference.md`, "The AI Provenance section," and the disclosure section of `AI-ETHICS.md`). It is the single most important demonstration in your portfolio. AI fluency under discipline is the trait the 2026 entry-level market screens for hardest.

The appendix documents, for the whole engagement or investigation:

- **Which AI tools** you used (model and interface for each).
- **What you asked.** The substantive prompts, paraphrased where trivial and verbatim where they mattered. Enough that a reader could reconstruct how you used AI.
- **What was generated.** The artifacts AI produced and their size: "drafted the executive summary, roughly 200 words"; "drafted a Sigma rule, 18 lines"; "suggested four enumeration angles."
- **What verification you performed.** The specific check, never "I checked it." For a report paragraph: "rewrote in my own words and confirmed each claim against my raw nmap output and my notes." For a detection query: "ran against the actual log source and confirmed it returned the three events I expected and no false positives in a clean baseline."
- **What you discarded as wrong, and why.** This is the most valuable part. "AI claimed the box was vulnerable to CVE-XXXX-YYYY based on a banner; the version it cited was not actually affected, so I discarded that lead." The discards prove you were the senior reviewing the junior, not the other way around.

### What Capstone D is not

It is not a disclaimer. It is not "AI was used in the production of this report." It is a substantive, specific account that a skeptical reader treats as evidence you understand your own work. A shallow appendix fails the gate exactly as a shallow notebook provenance section does.

It is also not a place to launder a violation. If the appendix would have to admit that AI generated exploit code against the target, or that you pasted credentials into a public model, then the work itself violated `AI-ETHICS.md` and the fix is to redo the work correctly, not to write a careful appendix around it. The appendix documents disciplined AI use; it cannot make undisciplined use acceptable.

### Form of the appendix per track

- **Capstone A and B (reports):** an appendix titled "Appendix: AI Provenance" at the end of the report, after the technical appendices. One to two pages.
- **Capstone C (public artifact):** the disclosure form scales to the artifact, per `AI-ETHICS.md`. A blog post carries a footer ("AI used for drafting and summarization; all findings and verification by the author"). A tooling repo carries an acknowledgments line in its README. A code contribution discloses AI assistance in the pull request description if AI played a non-trivial role. The bar is the same: honest, specific, public.

## The professional-report standard (Capstone A and B)

Capstone A and B are reports, and they are graded as reports. The technical work underneath them must be real, but a brilliant engagement written up badly is a failed deliverable, because the report is the only thing a client or employer ever sees. Both reports meet this bar:

- **Audience layering.** An executive summary a non-technical manager can read and act on, and a technical body a practitioner can reproduce from. The same finding appears in both, pitched differently.
- **A confidentiality and handling notice.** A one-line statement near the top that the report is confidential to its intended recipient. A real engagement report always carries one; on a lab target it is practice, but its presence is what a hiring manager who has seen real deliverables looks for.
- **Stated assumptions and limitations.** Capstone A carries a dedicated Assumptions and Limitations section (the time-box, what was and was not tested, credentialed versus uncredentialed, and that absence of a finding is not proof of security). Capstone B states the equivalent bounds on its investigation (the log sources available, the window investigated, and what the evidence could not establish). A report that scopes its own confidence reads as professional; one that implies it found everything does not.
- **Findings carry severity and evidence.** Each finding states its severity (with a rationale, ideally tied to CVSS or a stated rubric), the evidence that it is real, the impact if exploited, and a concrete remediation. A finding without evidence is an assertion; a finding without remediation is a complaint.
- **Reproducibility.** A reader with the same access could follow your report and reproduce your results. This is what separates a report from a story.
- **Clean prose.** Spell-checked, consistently formatted, and free of the artifacts of hurried writing. Define jargon or avoid it. No em dashes, to match the house style of the course's own prose; use commas, colons, parentheses, or semicolons.
- **No flags.** Capstone A documents methodology and findings, never HackTheBox or CTF flags. The report demonstrates how you rooted the box, not the proof string. (And the tutor never confirms a flag for you; if you find yourself wanting to paste one, re-read the no-flag rule.)

Page counts are targets, not games to play. Capstone A is 15 to 25 pages because a real engagement against a single host produces roughly that much when written honestly; if yours is 8 pages, you under-investigated, and if it is 60, you are padding. Capstone B is 10 to 15 pages on the same logic.

## RETROSPECTIVE.md: the final deliverable

The retrospective is where you close the course by reckoning, in writing, with what you can and cannot do. It is for you first; it is also a document a thoughtful interviewer would be impressed to see. It is a markdown file, 1500 to 3000 words, committed at the repo root or in your portfolio repo. Five required sections. You draft sections 2, 3, and 4 (strong patterns, target role, and interview problems) earlier, because Capstone F and Capstone E draw on them; you finalize the whole document at the end of the course.

### 1. Weak patterns

Name the pattern families where you are still weak, honestly. Not "I need to study more"; specific: "I can read a packet capture but I am slow at reconstructing a TCP stream from a noisy PCAP"; "I can write a Sigma rule but I still reach for AI before I have thought about false positives." Tie each to the month and labs that taught it. This section is worthless if it flatters you.

### 2. Strong patterns

Name the pattern families you own. The ones where, in an interview, you would welcome a hard question. Tie each to the evidence: the lab, the artifact, the capstone finding that proves it. This is the section you mine for interview talking points.

### 3. Target role and positioning

Name the one or two roles you are targeting, state which of your artifacts lead for each, and write the two-sentence positioning statement you would open a screen with. Be specific and realistic: "SOC analyst, with detection engineering as the growth path," not "a cybersecurity job." This is the target-role commitment, and it is the spine of Capstone F (the resume, the portfolio index, and the profile all order themselves around it) and the answer to the live interview question in Capstone E ("what role are you targeting and why you for it"). Commit it here once; the other tracks reference it. Your breadth (offense, defense, cloud, AI) only becomes a defensible market position once you can say which door you are knocking on and which artifacts prove you belong behind it.

### 4. Three expected interview problems, with a playbook for each

Pick three problems you genuinely expect to face in entry-level interviews. These should be specific and drawn from the actual market, for example: "given a suspicious PowerShell command line, explain what it does and whether it is malicious"; "you are handed a PCAP and asked what is happening"; "walk me through how you would scope and begin a pentest against a single web server you have authorization to test." For each, write a playbook: the steps you would take, the tools you would reach for, the concepts you would name, and the most common way candidates get it wrong. This section turns your portfolio into interview readiness, and it is the question surface the Capstone E mock screen draws on.

### 5. An honest read of the market, a 6-month maintenance plan, and a job-search channel plan

**The honest market read comes first, because it sets the expectations the plan is built on.** Write one blunt paragraph about what the job search actually looks like in your local market. The truth: the portfolio shortens the search, it does not eliminate it. Expect a search measured in months, not weeks. Expect to send many applications for each interview. Expect that your first role may be adjacent (IT support, help desk, a GRC or junior analyst seat) and that an adjacent role is a legitimate on-ramp, not a failure. A candidate who expects to walk from this course straight into a SOC seat and instead meets a months-long search can mistake a sound plan for a broken promise; naming the reality up front protects your morale and your judgment. Be specific to where you are, not generic.

Then the plan. Skills decay. Write a concrete plan to maintain and extend what you built, over the six months after the course: which platforms you will keep active (HackTheBox, a SIEM you keep running, a CTF cadence), how often, which weak patterns from Section 1 you will deliberately drill, and one stretch goal (a certification, a deeper specialization, a larger open-source contribution). Concrete: "two HTB boxes a month, written up"; not "keep practicing."

Then a job-search channel plan, because the plan above keeps your skills sharp but does not, by itself, get the work in front of a person. At the entry level the channel you use matters more than the volume you apply at. The blunt truth: a referral or a warm introduction is worth more than ten cold applications sent over the transom, and the candidates who get the first call are usually the ones who were visible to a human before the resume landed. So write your own channel plan, the same way you wrote the maintenance plan, naming concretely:

- **One community you will be active in** (a local security meetup, a Discord or Slack, a CTF team), and what "active" means for you (showing up, answering questions, posting your public writeup), not just lurking.
- **A target number of informational conversations per month** (for example, two: a coffee chat or a short call with someone doing the work you want, asked for their read on the field, not for a job).
- **The channels you will actually apply through, in priority order**, with referrals and warm introductions ahead of cold job-board applications, and a note of who in your growing network you would ask for an introduction first.
- **An honest line on the adjacent on-ramp.** Tie this back to the market read above: name the adjacent roles you would take as a legitimate first step (IT support, help desk, a GRC or junior-analyst seat), since the channel plan is what carries you from one of those into the role you are targeting.

Write the plan, do not just read this list. A channel plan you committed and can act on is the artifact; generic advice you nodded at is not.

## Acceptance criteria

- **Capstone A:** a 15 to 25 page pentest report against a legal target, authorization basis documented in writing before work began and verified by the tutor, engagement dates stated in Scope, an Assumptions and Limitations section and a confidentiality notice present, professional-report standard met, no flags, Capstone D appendix present and substantive.
- **Capstone B:** a 10 to 15 page IR report on a breach you simulated and investigated in your Month 9 SIEM, NIST 800-61 lifecycle followed, the investigation's bounds stated, professional-report standard met, Capstone D appendix present and substantive.
- **Capstone C:** at least one public, searchable written piece (a blog post or a retired-CTF writeup, sanitized), genuinely public, with AI assistance disclosed per `AI-ETHICS.md`. A contribution or repo may be added but does not satisfy the written requirement.
- **Capstone E:** a 45-minute timed mock screen sat in one sitting with AI closed, the tutor's feedback taken, and a written self-assessment committed.
- **Capstone F:** a named target role and positioning statement, a one-to-two-page role-targeted resume, a public portfolio-index page with a thesis, and a public-profile pass linking the public artifacts.
- **RETROSPECTIVE.md:** all five sections present and substantive (weak patterns, strong patterns, target role and positioning, three interview problems with playbooks, and the market read plus a 6-month maintenance plan and a job-search channel plan), 1500 to 3000 words, honest about weaknesses.
- **Five notebook entries** committed, each with a complete AI Provenance section.
- **No real credentials, keys, or sensitive data** anywhere in any deliverable or its history. Synthetic and lab data only; redact anything from a target VM that resembles a secret.
- **No em dashes** anywhere, to match the course house style.

## Verification

The tutor verifies, for each track: the authorization basis, engagement dates, and limitations section (A); that the report meets the professional standard and the Capstone D appendix is substantive and not a disclaimer (A and B); that at least one public written piece is actually public (C); that the mock screen was sat under the real constraint and the self-assessment is honest (E); and that the resume and portfolio index lead with the target-role artifacts and every claim is defensible (F). Then it runs the verification ritual: it selects one finding, one report paragraph, one SIEM query, one line of code, or one resume claim, and asks you to defend it from memory with your AI session closed. If you cannot defend it, that piece returns. The capstone is not done until you can defend every element a skeptical interviewer might probe. Capstone E is itself a whole-portfolio version of that ritual.

## Why this is the capstone deliverable

Because the promise of the course is a graduate who can do the work, get it looked at, and prove it under pressure. The pentest report proves you can run an offensive engagement to a professional standard. The IR report proves you can investigate and communicate a breach. The public written piece proves you can ship something a stranger will read and that your name returns real work in a search. The provenance appendices prove you use AI the way the field now demands: as a fast junior whose work you verify and sign. The portfolio package and target role (Capstone F) get the work in front of the person who decides, framed as one coherent story rather than a pile of repos. The timed mock screen (Capstone E) rehearses defending it all live, which is where strong candidates with unpackaged, unrehearsed work fall apart. The retrospective proves you can assess your own gaps honestly, which is the trait that turns a junior into a senior. Together they are a portfolio that answers the questions every entry-level interview asks, with evidence rather than claims, and that a hiring manager actually reads.

## How to know it is done

- Five tracks delivered, each meeting its acceptance criteria; A, B, and C each carry a Capstone D appendix or its disclosure equivalent.
- The Capstone A authorization basis documented and verified before any engagement work.
- At least one public, searchable written piece published (Capstone C).
- The timed mock screen sat and the self-assessment written (Capstone E).
- A named target role, a resume, and a public portfolio index delivered (Capstone F).
- `RETROSPECTIVE.md` committed with all five sections, including the named target role and the honest market read.
- Five notebook entries committed, each with a complete AI Provenance section.
- `.tutor/lab-log.md` shows all five capstone tracks logged.
- `.tutor/progress.md` updated to "Month 12 complete; course complete."

If any of the above is missing, the course is not complete. The tutor will not mark the course complete until all of it is present and every deliverable can be defended.
