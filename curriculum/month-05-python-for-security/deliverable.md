---
title: "Deliverable"
parent: "Month 5 - Python for Security"
grand_parent: Curriculum
nav_order: 91
---

# Month 5 Deliverable: The security-tools Repository

## What you produce

A **public** GitHub repository named `security-tools/`. It holds the four tools you built this month, each documented and tested, plus a repository-level `SAFETY.md`.

This is the first major public artifact in your portfolio. A hiring manager will look at it. It should look like the work of someone who can be trusted with a production system.

## Required structure

```
security-tools/
├── README.md            # What this repo is, who built it, the AI disclosure footer
├── SAFETY.md            # The legal-use boundary for every tool here
├── port-scanner/        # Lab 5.1
│   ├── README.md        # Usage + scope warning (own hosts only)
│   ├── port_scanner.py
│   └── tests/
├── log-parser/          # Lab 5.2
│   ├── README.md
│   ├── log_parser.py
│   └── tests/
├── password-tester/     # Lab 5.3
│   ├── README.md
│   ├── password_tester.py
│   └── tests/
└── http-fuzzer/         # Lab 5.4
    ├── README.md        # Usage + scope warning (own DVWA only), leading the file
    ├── http_fuzzer.py
    └── tests/
```

The exact filenames are yours. The structure is the requirement: one folder per tool, each with a README and tests.

## Acceptance criteria

- **Four working tools.** Each runs from the instructions in its own README. Each has a test suite that passes from one command.
- **A repository `SAFETY.md`.** It states the legal-use boundary. It names which tools are **dual-use** (the scanner and the fuzzer: built for defense, but usable for attack) and says what authorized use looks like.
- **Scope warnings lead the README** of the port scanner and the HTTP fuzzer. Not buried. First.
- **An AI disclosure** in the repository README's acknowledgments. One line: AI was used in a drafting role, and the author verified all code. This is the public version of your provenance discipline. It is the exact thing employers screen for (see `AI-ETHICS.md` on disclosure).
- **The repository is public.** A private repo does not move your portfolio. If a tool is too rough to be public, polish it. Do not hide it.
- **No real credentials, no real passwords, no real-target output** anywhere in the repo or its history. Synthetic data only.

## Verification

The tutor checks that the repository is public, the tests pass, the scope warnings and `SAFETY.md` are present, and the AI disclosure is in the README.

Then the tutor runs the **verification ritual**: it picks one function from one tool, at random, and asks you to explain it from memory, with your AI session closed. The deliverable is not done until you can defend that function.

## Why this is the Month 5 deliverable

This repository is the proof that the AI-free months worked. You built four real tools. You used AI as a drafting junior, verified its output, and packaged the result responsibly, with the scope discipline a professional brings.

It is two things at once: a portfolio piece, and a demonstration of AI fluency. AI fluency is the single most-screened-for trait in the 2026 entry-level market. The reports in Months 9, 10, and 12 build on the habits this repository establishes.

## How to know it is done

- The `security-tools/` repository is public, with four tested tools and a repo `SAFETY.md`.
- Scope warnings lead the dual-use tools' READMEs. The AI disclosure is in the repo README.
- Four notebook entries are committed, each with a complete AI Provenance section.
- The cold-revisit week's sub-tasks are completed and logged.
- `.tutor/progress.md` is updated to "Month 5 complete; ready for Month 6."
