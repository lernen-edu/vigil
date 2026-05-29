---
title: "Deliverable"
parent: "Month 2 - Linux CLI Mastery and Regex"
grand_parent: Curriculum
nav_order: 91
---

# Month 2 Deliverable: The Linux Survival Cheat Sheet and Five Shell Scripts

## What you produce

Two artifacts:

1. A `linux-survival.md` cheat sheet, **written from memory at the end of the month, with no copy-paste from the web**.
2. The **five working shell scripts** from Lab 2.2, in a **public** repository.

Together they are the proof that this month landed: the cheat sheet shows what you retained, and the scripts show you can turn that knowledge into working automation. The scripts are also the first code-bearing entry in your public portfolio, the precursor to the larger `security-tools/` repository you build in Month 5.

## Artifact 1: the cheat sheet, from memory

### The constraint is the point

You write `linux-survival.md` from memory. No copy-paste from a website, no pasting from the man pages, no AI. You may glance at your own notebook entries and your own `regex-log.md` and `pipelines.md` to jog recall, because you wrote those, but the cheat sheet itself is composed from what is in your head at the end of the month.

A cheat sheet assembled by pasting from Stack Overflow teaches you nothing and you cannot defend it. One you wrote from memory is a map of what you actually retained, and, more usefully, the gaps in it are a precise list of what to revisit. If you cannot recall the octal for "owner read-write, group read, other none" without looking, that gap is the deliverable doing its job: it tells you where to drill before Month 3.

### Coverage

The cheat sheet should cover, at a level you would actually find useful at three in the morning on a host you have never seen:

- **Filesystem and navigation.** The directories that matter (`/etc`, `/var`, `/proc`, `/usr`, `/home`, `/tmp`) and what is in each. Moving around, finding files by name and by content.
- **Permissions.** Symbolic and octal notation, the common octals (`644`, `755`, `600`, `640`), `chmod` and `chown`, and what the setuid, setgid, and sticky bits mean.
- **Processes and signals.** Listing and inspecting processes, finding one by name, the common signals and when to use each, and the `SIGTERM`-versus-`SIGKILL` distinction.
- **Text processing.** The `grep`, `sed`, `awk`, `cut`, `sort`, `uniq` toolkit, the three standard streams, redirection, and the `sort | uniq -c | sort -rn` counting idiom.
- **Bash discipline.** The shebang, `set -euo pipefail` and what each flag does, quoting, exit codes, and the structure of a conditional and a loop.
- **Regex.** Character classes, anchors, quantifiers (greedy and lazy), grouping, alternation, backreferences, lookaround, and a compact statement of the BRE-versus-ERE-versus-PCRE differences. This section is the one most worth getting right, because it is the most reused skill in the course.
- **Package management and services.** `apt` essentials, finding a package's files with `dpkg -L`, and the `systemctl` and `journalctl` commands for checking a service.

### Specification

- **Length:** whatever it takes to be genuinely useful and no longer. A cheat sheet is terse by nature; if it reads like a textbook, it is not a cheat sheet.
- **Format:** Markdown, organized by the sections above, scannable. Tables and short code fences are appropriate here (a cheat sheet is the one place compact command examples belong).
- **Honesty:** if there is a section you could not write confidently from memory, mark it. A cheat sheet with an honest "weak here, revisit" note is worth more than one that papers over a gap, and it directs your cold-revisit study.
- **No em dashes**, to match the house style of the course's prose. Use commas, colons, parentheses, or semicolons.

## Artifact 2: the five shell scripts, in a public repo

### What goes in the repo

The five scripts from Lab 2.2: the system information dump, the log tail with `grep` filters, the scheduled backup, the fail2ban-style watcher, and the service health checker. Each with:

- A header comment (shebang, `set -euo pipefail`, a one-line description, and a scope or safety note where the script needs one).
- A short README for the repository explaining what the collection is, how to run each script, and the scope warning for the watcher (it operates on your own logs only).
- A sample run or sample output for at least the system-info, log-tail, and watcher scripts, so a reader can see what each produces without running it.

A suggested structure (the exact layout is yours; the requirement is that each script is runnable and documented):

```
linux-scripts/
|- README.md            # What this is, how to run each script, scope note for the watcher
|- sysinfo.sh           # Task 1: system information dump
|- logtail.sh           # Task 2: log tail with grep filters
|- backup.sh            # Task 3: scheduled backup
|- authwatch.sh         # Task 4: fail2ban-style watcher (own logs only)
|- healthcheck.sh       # Task 5: service health checker
|- samples/             # Sample inputs and outputs (synthetic data only)
```

### Acceptance criteria

- **Five working scripts**, each runnable, each starting with the shebang and `set -euo pipefail`, each quoting its variables, handling its error cases, and exiting with a meaningful code.
- **A repository README** that explains the collection and carries the watcher's scope warning (own systems only) where a reader will see it, not buried.
- **The repository is public.** A private repo does not advance your portfolio. If a script is too rough to be public, the fix is to polish it, not to hide it.
- **Synthetic or own-VM data only.** No real third-party IP addresses, hostnames, credentials, or production logs anywhere in the repo or its git history. The watcher's sample run uses synthetic addresses; the log-tail's sample uses a synthetic or your-own-VM log. This is the same data-handling rule the Month 5 deliverable enforces, and it starts here.
- **No AI was used**, consistent with the AI-free zone. Because no AI was used, there is no AI disclosure to add this month; the repo README simply does not claim AI assistance. (From Month 5 onward, public repos carry an AI disclosure line; this month they do not, because there is nothing to disclose.)

## Verification

The tutor verifies the deliverable the way it verified the Month 1 boot writeup: by checking that you produced it yourself.

- For the **cheat sheet**, the tutor picks one section at random and asks you to reproduce or expand it from memory, in more depth than the cheat sheet itself goes. The regex section and the permissions section are likely targets, because they are the most reused and the most precise. If you wrote the sheet from memory, this is easy. If you pasted it, it is not.
- For the **scripts**, the tutor picks one script and asks you to explain a specific line (a quoting decision, an error-handling branch, the exit-code logic) from memory. This is the same spot-check Lab 2.2 used; the deliverable just confirms it holds across the polished, public versions.

The deliverable is not done until you can pass both checks.

## Why this is the Month 2 deliverable

The cheat sheet is a retention instrument disguised as a portfolio piece: writing it from memory forces a full recall of the month and surfaces exactly what did not stick. The scripts are the first evidence in your portfolio that you can build reliable automation, with the shell discipline (`set -euo pipefail`, error handling, meaningful exit codes) that every later month assumes. Month 5 reimplements these same five tools in Python, and the comparison (what Bash made easy, what it made painful, what a real language buys you) is only meaningful if the Bash versions are genuinely yours.

## How to know it is done

- `linux-survival.md` committed, demonstrably written from memory, with any weak sections honestly marked.
- The five scripts in a public repository, each runnable and documented, with the watcher's scope warning in the README and synthetic-or-own data only.
- Five lab notebook entries committed (one per lab).
- The Month 1 cold revisit completed and logged.
- `.tutor/lab-log.md` shows all five Month 2 labs logged.
- `.tutor/progress.md` updated to "Month 2 complete; ready for Month 3."

If the cheat sheet was assembled by copy-paste rather than written from memory, the month is not done. The constraint is the curriculum, not a formality.
