---
title: "Deliverable"
parent: "Month 7 - Web Application Security (and SQL)"
grand_parent: Curriculum
nav_order: 91
---

# Month 7 Deliverable: The Web Security Portfolio and the Custom Vulnerable App

## What you produce

Two artifacts:

1. A `web-security-portfolio.md` documenting your five completed labs with screenshots and reproduction steps. This is a lasting portfolio piece; a hiring manager will read it.
2. The **custom vulnerable app's repository** from Lab 7.5: a public repo containing the app's source, its two documented flaws and fixes, and a README leading with the "intentionally vulnerable, never expose" warning. The repository is public for review; any running instance is removed from public hosting once the lab is done.

Together they demonstrate that you understand web flaws from both sides: as someone who can find and document them, and as someone who can introduce and remove them in code.

## Part 1: web-security-portfolio.md

### Specification

- **Length:** as long as the evidence requires, but written tight. Roughly 2000 to 4000 words plus screenshots is typical. Padding is not the goal; reproducible, well-explained findings are.
- **Audience:** a technically literate reader screening you for a junior web-security or application-security role. They will skim for whether your findings are reproducible and whether you understand the flaws or merely ran them.
- **Structure:** one section per lab (7.1 through 7.5). The SQL section (7.1) summarizes your fluency and includes your prepared-statement writeup. Each web section (7.2 through 7.5) presents representative findings with reproduction steps and screenshots of the request and response in Burp.
- **Mapping:** every web finding is mapped to its OWASP Top 10 (2025) category, with a one-sentence justification. The DVWA section's category coverage and the Juice Shop recognition retrospective both feed this.
- **Constraint:** define each flaw class the first time it appears, briefly, in your own words. If you cannot define it simply, you do not yet understand it well enough to claim it as a finding.

### What goes in, what stays out

- **In:** reproduction steps, screenshots of requests and responses, your category mappings, your low-versus-high comparisons from DVWA, your prepared-statement writeup, and an honest account of what you found by recognition versus what you stumbled into.
- **Out:** no scoreboard tokens, no PortSwigger "solved" banners presented as proof (the reproduction steps are the proof), and nothing that reads as a copied published walkthrough. Your own payloads in your own reproduction steps are fine; this is your work product.
- **Scope statement:** the portfolio opens with a one-paragraph scope statement naming the four authorized target classes you worked against (your DVWA, your Juice Shop, the PortSwigger Academy under its terms, your own app), so any reader knows you operated inside authorization. This is the professional habit `SAFETY.md` builds.

### Acceptance criteria

- All five labs are represented, each with substantive evidence.
- Every web finding maps to an OWASP Top 10 (2025) category with a justification.
- Reproduction steps are precise enough that the reader could reproduce a finding on their own authorized copy of the target.
- A scope statement opens the document.
- No em dashes, to match the house style; use commas, colons, parentheses, or semicolons.
- An AI disclosure footer noting where the brainstorming-variations pattern was used and that the author verified every payload (per `AI-ETHICS.md`).

## Part 2: the custom vulnerable app repository

### Specification

- **Public repository** containing the app you wrote in Lab 7.5 (your code, no AI-generated app).
- **README leads** with the warning that the app is intentionally vulnerable and must never be run on a reachable network, followed by local-run instructions, the two flaws (each with its OWASP category and reproduction steps), and the fix for each with a before-and-after diff.
- **AI disclosure** in the README: the app code was written by the author without AI; AI was used only to brainstorm attack-payload variations during testing.
- **Teardown confirmed:** any running instance that was ever placed on a reachable host is taken down once the lab is complete. The repository (source only) stays; the running app does not.

### Acceptance criteria

- The repository is public and the source is present.
- Two distinct flaws from two different OWASP Top 10 (2025) categories, each traceable to specific lines, each with reproduction steps and an explained fix.
- The README leads with the "intentionally vulnerable, never expose" warning and includes the AI disclosure.
- No real credentials or secrets anywhere in the repo or its history; synthetic data only.
- No running instance remains on any public or reachable host.

## Verification

The tutor confirms both artifacts exist: the portfolio with all five labs and a scope statement, and the public app repository with two documented flaws, fixes, the teardown warning, and the AI disclosure. It confirms no reachable instance of the vulnerable app remains.

Then it runs the verification ritual twice: once on a finding in the portfolio (pick a payload or a category mapping; explain it from memory with the AI session closed) and once on a line of the custom app's code (explain what it does and why it is or is not exploitable). The deliverable is not done until you can defend both.

## Why this is the Month 7 deliverable

This is the portfolio piece that most directly maps to a job. Application security and web-focused roles are among the most common entry points into the field, and the screen for them is exactly what this deliverable demonstrates: can you find a flaw, explain which class it is, reproduce it cleanly, and fix it. The custom app proves the developer's-eye view; the portfolio proves the attacker's-eye view; the scope statement and teardown prove the professional discipline that separates someone employable from someone dangerous. The Month 10 pentest reports and the Month 12 capstone build directly on the reporting habits you establish here.

## How to know it is done

- `web-security-portfolio.md` committed, all five labs represented, scope statement and AI disclosure present, every web finding mapped to an OWASP 2025 category.
- The custom vulnerable app's public repository exists with two documented flaws and fixes, the teardown warning leads the README, and no reachable instance remains.
- Five lab notebook entries committed, each with a complete AI Provenance section (a declared null is complete for Lab 7.1).
- The cold-revisit week's sub-task completed and logged.
- You can pass the verification ritual on a portfolio finding and on a line of your app's code.
- `.tutor/progress.md` updated to "Month 7 complete; ready for Month 8."
