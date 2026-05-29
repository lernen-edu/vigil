---
title: "Deliverable"
parent: "Month 1 - IT Foundations and Hardware"
grand_parent: Curriculum
nav_order: 91
---

# Month 1 Deliverable: The Boot-Process Writeup

## What you produce

A writeup, `month-01-foundations.md`, in your lab notebook. It explains what happens between pressing the power button and seeing a login prompt. Write it for a smart non-engineer: a friend explaining it over coffee, not a textbook.

This is the first artifact in your public portfolio. By the end of the course it will live in a `writeups/` folder in your main work repository. It is the piece that shows you can explain a technical system clearly, which is half of every interview you will face.

## Specification

- **Length:** 800 to 1500 words.
- **Audience:** a smart person with no engineering background. Your favorite non-technical relative is the test reader.
- **Tone:** conversational and precise. A friend explaining it over coffee. Not a textbook, not a Wikipedia summary.
- **Coverage:** the chain from power-on to login prompt. Touch firmware (BIOS or UEFI), the boot loader, the kernel, the init system, and the login. You do not need every detail. You need to give a non-engineer an accurate mental model.
- **Constraint:** define every piece of jargon you use, in line, the first time it appears. If you cannot define a term simply, you do not yet understand it well enough to use it. Either learn it or cut it.

## Acceptance criteria

- The writeup is 800 to 1500 words and committed to your notebook.
- A non-engineer could read it and come away with a correct, if simplified, model of the boot process.
- Every technical term is defined the first time it is used.
- The piece draws on what you actually saw in Lab 1.2, not only on what you read. A line like "when I interrupted the boot on my own VM, I saw..." is the mark of a writeup grounded in practice.
- No em dashes, to match the house style of the course's own prose. Use commas, colons, parentheses, or semicolons.

## Verification

The tutor will not write this for you. It will check that you wrote it yourself by picking one sentence at random and asking you to expand on it from memory, in greater technical depth than the writeup itself goes. If you wrote the piece, this is easy. If you generated it, it is not.

## Why this is the Month 1 deliverable

Explaining a system simply is the skill that separates someone who memorized facts from someone who understands a mechanism. A hiring manager screening for a junior role cannot test your depth in 45 minutes, so they test your ability to explain. This deliverable is where you start building the explanation muscle. The Month 12 capstone reports, and your first interview, will lean on it.

## How to know it is done

- `month-01-foundations.md` is committed to `.tutor/notebook/` (or to your work repo's `writeups/` folder, with a link from the notebook).
- The three lab notebook entries are committed.
- `.tutor/lab-log.md` shows all three Month 1 labs logged.
- `.tutor/progress.md` is updated to "Month 1 complete; ready for Month 2."
