---
title: "Reading"
parent: "Month 2 - Linux CLI Mastery and Regex"
grand_parent: Curriculum
nav_order: 90
---

# Month 2 Reading

Free and high-signal. Primary sources first: man pages and official manuals before anything else. This month, more than any other, the reading lives on your own machine. The `man` pages for the tools you use are the authoritative reference, and reading them rather than a blog that paraphrases them is part of the curriculum. The discipline of reaching for the manual builds the habit that lets you evaluate AI output when it unlocks in Month 5.

## Core: the manuals on your own machine

These are the primary sources for the bulk of the month. Read the relevant sections before reaching for anything secondary.

- `man hier`: the filesystem hierarchy, from the source. The map for Lab 2.1 Task 2.
- `man bash`: the shell itself. For Lab 2.2, the sections on `set`, parameter expansion, quoting, and conditional expressions (`[[ ]]`) are the ones that matter. This is dense; read it in pieces, alongside the scripts you are writing.
- `man 7 regex`: the POSIX regular-expression manual, covering BRE and ERE precisely. The primary source for Lab 2.3's dialect work.
- `man grep`, `man sed`, `man awk`, `man cut`, `man sort`, `man uniq`: the text-processing toolset for Lab 2.4. `man grep`'s notes on BRE, ERE, and PCRE tie directly to Lab 2.3.
- `man 7 signal`, `man ps`, `man kill`: processes and signals for Lab 2.1.
- `man chmod`, `man stat`, `man 2 setuid`, `man sudoers`: permissions and privilege, for Labs 2.1 and 2.5.

## Core: official manuals and specifications

- _docs_ The GNU Bash Reference Manual: the authoritative manual for the shell, more navigable than `man bash` for reading cover to topic. The primary reference for Lab 2.2's shell discipline.
- _spec_ The Filesystem Hierarchy Standard: the official specification for what lives in `/etc`, `/var`, `/usr`, and the rest. Background for Lab 2.1.
- _docs_ The GNU Coreutils manual: the official reference for `cut`, `sort`, `uniq`, and the other small tools you chain in Lab 2.4.
- _docs_ The GNU `gawk` manual: deeper than the `awk` man page; read the field-processing chapter for Lab 2.4. You do not need all of `awk`.
- _docs_ The PCRE2 pattern documentation (`pcre2pattern`): the authoritative reference for the Perl-compatible regex features (lookaround, lazy quantifiers, named groups) that the POSIX dialects lack. Primary source for the PCRE half of Lab 2.3.
- _spec_ The POSIX specification's chapter on regular expressions, for the exact definitions of the character classes (`[[:digit:]]`, `[[:alpha:]]`).

## Concepts and formats

- _docs_ The Apache HTTP Server documentation on log formats (combined and common log format definitions). Primary source for Lab 2.4 Group A.
- _docs_ The nginx documentation on the `log_format` directive and its default `combined` format. Primary source for Lab 2.4 Group A.
- _docs_ The systemd `journald` and `rsyslog` documentation for the structure of a syslog line. Primary source for Lab 2.4 Group B.
- _reference_ The principle of least privilege, as defined in an authoritative security reference (the NIST glossary defines it cleanly). The defensive backbone of Lab 2.5.

## Lab platforms (free)

- TryHackMe "Linux Fundamentals" Parts 1, 2, and 3 (free rooms) for Lab 2.1.
- RegexOne (free interactive lessons) for Lab 2.3.
- Regex Crossword (free puzzles) for Lab 2.3.
- The GTFOBins project (free, open catalog) for Lab 2.5. Read it for mechanism, not as a list of commands.

## Tools you may use to inspect your own work (not AI)

- ShellCheck (free): a static analyzer for shell scripts. Using it to find bugs in your own scripts is a linter, not AI assistance, the same way a compiler warning is not AI assistance. Understand every warning it raises rather than blindly applying its fix.
- A multi-engine regex tester (regex101 and similar are free): use it to inspect and visualize patterns you wrote and to confirm which dialect a construct belongs to. Do not use it to have a pattern generated for you; in this AI-free month, the pattern is yours to write.

## A note on sources

The rule from Month 1 still holds: when a lab asks you to cite a source, cite from "Core" or "Concepts," not from a blog or a video walkthrough. This month leans even harder on primary sources than Month 1 did, because the `man` pages and official manuals are genuinely the best documentation that exists for these tools, and because the habit of reading them is what makes you able to judge AI's claims about shell and regex behavior when AI unlocks in Month 5. Blogs paraphrase the manuals and frequently get the BRE-versus-ERE-versus-PCRE distinction wrong; the manuals do not.
