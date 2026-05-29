---
title: "Reading"
parent: "Month 5 - Python for Security"
grand_parent: Curriculum
nav_order: 90
---

# Month 5 Reading

The Python documentation is your primary source this month. Read it. Do not skim a tutorial that paraphrases it.

Here is why this matters. The whole point of Month 5 is that you can judge AI-drafted code. You can only judge it against the real reference. The docs are that reference.

## Core: the standard library you will use

The **standard library** is the set of tools that ship with Python, no install needed.

- _docs_ Python `socket` module (for Lab 5.1). Opens raw network connections.
- _docs_ Python `argparse` module. Builds the command line for every tool.
- _docs_ Python `sqlite3` module (for Lab 5.2). A database in a single file. This is your first SQL.
- _docs_ Python `re` module (for Lab 5.2). Regex, the Month 2 skill, now in Python.
- _docs_ Python `hashlib` module (for Lab 5.3). Hashes data.
- _docs_ Python `concurrent.futures` and `asyncio` (for Lab 5.1). Two ways to do many things at once.
- _docs_ The `requests` library (for Labs 5.3 and 5.4). Handles HTTP. It is one install away, not built in.

## Concepts

- _docs_ The Have I Been Pwned range API and its **k-anonymity** model (primary source for Lab 5.3). Read how the prefix trick works before you build it.
- _reference_ **Shannon entropy**: any solid explanation of the formula and what it measures. Learn why entropy alone is not enough to judge a password.
- _docs_ The Apache combined and nginx default log formats (for Lab 5.2). These name every field, in order.
- _docs_ The DVWA project documentation (for Lab 5.4). How to install and run your own practice target.

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read it before your first lab. The drafting pattern, the provenance discipline, and the data-handling rule all come from here.

## A note on AI-generated code

When AI drafts a function that calls a standard-library method, check that the method is real. Confirm it exists, and that it behaves the way AI claims, against the docs above.

AI invents method names and parameters that sound right but do not exist. This is confident and frequent. The reading list is your defense. The verification ritual is the test of whether you used it.
