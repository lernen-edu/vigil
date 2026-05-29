# Vigil

A 12-month, lab-driven course that takes a complete novice to a working cybersecurity practitioner with a public portfolio. AI-augmented. Hands-on. Honest about ethics and legality.

Vigil is fronted by a demanding Socratic tutor that runs inside your AI coding agent. The tutor does not write your labs, hand you answers, or confirm CTF flags. It enforces the discipline that turns twelve months of work into a body of evidence you can defend in an interview.

Vigil is a Lernen-edu course, sibling to [Muster](https://github.com/lernen-edu) (LeetCode pattern mastery) and Agentwright (agentic engineering).

## Start here

```
# 1. Clone the course
git clone https://github.com/lernen-edu/vigil.git
cd vigil

# 2. Open it in your AI coding agent (Claude Code shown; see the support matrix below)
claude

# 3. Ask the tutor to orient you
#    "What are you, and what are the rules?"
```

Then read, in order: `getting-started.md` (set up your Mac and home lab), `SAFETY.md` and `AI-ETHICS.md` (the boundary that keeps this work legal), and `curriculum/month-00-setup/README.md` (your first month).

Complete novice means no prior security or coding experience is assumed. The on-ramp includes a self-paced, AI-free Python primer that you start in Month 0 and finish during Months 1 to 4, so you reach the Python month (Month 5) ready. `getting-started.md` sets it up.

A working adult finishes Vigil in about 12 months at 10 to 15 hours per week. Full-time pacing collapses it to roughly 6 months.

## How this course is different

Vigil enforces seven pedagogical principles. They are rules, not suggestions, and the tutor holds you to them:

1. **Concept first, command second.** No tool runs until you can write down what it does to the wire, the disk, or the kernel.
2. **The lab attempt floor.** 45 to 90 minutes of unaided work before any hint or walkthrough.
3. **Hints, not flags.** A six-rung hint ladder, one rung per ask. The tutor never confirms a CTF flag.
4. **The lab notebook is the gate.** No notebook entry committed, no advancement to the next lab.
5. **Spaced revisits every three weeks.** The tutor pulls a prior lab and asks you to redo a subtask cold.
6. **AI is an apprentice's tool, not a master's.** An AI-free zone for the fundamentals (Months 0 to 4), then AI augmentation unlocks one pattern per month, always under provenance discipline.
7. **You defend what you submit, AI-assisted or not.** Every AI-augmented artifact is subject to a random verification ritual.

The full human-facing contract is in `tutor-reference.md`. The tutor's enforcement contract is `.tutor/tutor-core.md`.

## What you graduate with

By Month 12 you have a public portfolio: a security-tools repository, a hardened-Windows writeup, a web-security portfolio, an annotated TLS handshake, an incident-response report, three pentest writeups, a cloud-and-AI security review, and a capstone (a full pentest report, an IR report, and a public artifact), each with documented AI provenance. The graduate is positioned for an entry-level role (SOC analyst, junior security engineer, junior penetration tester) at a mid-tier company. The course is honest that true expert depth takes longer than a year; see the curriculum overview for that framing.

## The 12 months

Full master index and per-month detail: `curriculum/README.md`.

| Month | Topic | Canonical deliverable |
| ----- | ----- | --------------------- |
| 0  | Setup and home lab | Working, documented VM stack |
| 1  | IT foundations and hardware | "What happens at boot" writeup |
| 2  | Linux CLI mastery and regex | Five shell scripts and a cheat sheet |
| 3  | Networking fundamentals | Annotated home-lab network diagram |
| 4  | Network tools and packet analysis | Five PCAP analyses |
| 5  | Python for security (AI unlocks) | Four security tools (public repo) |
| 6  | Windows security | Hardened domain-controller writeup |
| 7  | Web application security and SQL | Web-security portfolio and custom vuln app |
| 8  | Cryptography and PKI | Annotated TLS 1.3 handshake |
| 9  | Defensive operations (blue team) | Incident-response report |
| 10 | Offensive operations (red team) | Three pentest writeups |
| 11 | Cloud and AI system security | Cloud misconfig writeup and AI security review |
| 12 | Capstone | Pentest report, IR report, public artifact |

## Supported AI coding agents

The tutor activates from a per-agent entry-point file at the repo root. Pick one agent and commit to it for the course.

| Agent | Entry-point file | Mode |
| ----- | ---------------- | ---- |
| Claude Code | `CLAUDE.md` | Full enforcement |
| Codex CLI | `AGENTS.md` | Full enforcement |
| Gemini CLI | `GEMINI.md` | Full enforcement |
| OpenCode | `AGENTS.md` | Full enforcement |
| Pi Coding Agent | `AGENTS.md` | Full enforcement |
| GitHub Copilot | `.github/copilot-instructions.md` | Advisory (see the file) |

Each file redirects the agent to `.tutor/tutor-core.md`. There is no install script and no MCP server; the entry-point files plus the tutor core are the entire distribution mechanism.

## Repository map

```
vigil/
├── README.md              # This file
├── getting-started.md     # Mac + home-lab + agent setup
├── tutor-reference.md     # The human-facing tutor contract
├── SAFETY.md              # Legal and ethical scaffolding (read before Month 0)
├── AI-ETHICS.md           # Operational AI-use ethics (read before Month 5)
├── CLAUDE.md AGENTS.md GEMINI.md   # Per-agent tutor entry points
├── .github/copilot-instructions.md # Copilot entry point
├── .tutor/                # Tutor contract + runtime state (not part of the public site)
│   ├── tutor-core.md      # The tutor's enforcement contract (the source of truth)
│   ├── session.json       # Per-learner session state (template)
│   ├── progress.md  lab-log.md
│   └── notebook/          # Your lab notebook lives here
└── curriculum/            # The course
    ├── README.md          # Master 12-month index
    └── month-00 .. month-12/
```

## A note on the tutor

The tutor is demanding by design. It will not say "great question." It will not soften a refusal because you are frustrated. It will not write your labs, and it will not apologize for any of that. If you want a warm assistant, there are many; this is not one. The bluntness is the point: cybersecurity work is performed under pressure, and the muscle for it is built here. Read the "note on the demanding posture" in `tutor-reference.md` before you decide whether this course is for you.

## Safety and legality

This course teaches techniques that are legal in some contexts and criminal in others. **Read `SAFETY.md` and `AI-ETHICS.md` before you begin.** The one-sentence version: you may only test systems you demonstrably own or have explicit written authorization to test. The tutor enforces this on every prompt, and it will not bend.

## License

Dual-licensed:

- **Course content** (everything under `curriculum/`, plus `index.md`, `getting-started.md`, `tutor-reference.md`, `SAFETY.md`, and `AI-ETHICS.md`) is licensed under [CC BY 4.0](LICENSE-CONTENT).
- **Tutor scaffolding and code** (`.tutor/`, the per-agent entry-point files, and `_config.yml`) is licensed under the [MIT License](LICENSE-CODE), copyright Lernen-edu.

See `LICENSE-CONTENT` and `LICENSE-CODE` for the full terms.
