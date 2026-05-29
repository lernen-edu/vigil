---
title: "Labs"
parent: "Month 5 - Python for Security"
grand_parent: Curriculum
nav_order: 50
---

# Month 5 Labs

Four labs. Four tools. Together they become your first public portfolio repository.

Do them in order. Each one assumes the Python the last one taught. The drafting pattern and the mandatory AI Provenance log apply to every lab (see the Month 5 README).

| Lab | Folder | Time | Floor | Tool you build |
| --- | ------ | ---- | ----- | -------------- |
| 5.1 Pure-Python Port Scanner | `lab-01-python-port-scanner/` | 10 to 12 h | 90 min | A concurrent TCP connect scanner (own hosts only) |
| 5.2 Log Parser with SQLite | `lab-02-log-parser-sqlite/` | 12 to 14 h | 90 min | A log-to-SQLite pipeline and an incident summary |
| 5.3 Password Strength Tester | `lab-03-password-strength-tester/` | 8 to 10 h | 90 min | An entropy and k-anonymity breach scorer |
| 5.4 HTTP Fuzzer (lab only) | `lab-04-http-fuzzer/` | 10 to 12 h | 90 min | A directory and parameter fuzzer (own DVWA only) |

Two labs carry hard scope rules: 5.1 and 5.4. Run them only against hosts you own. Re-read each lab's scope section before you run anything.

All four tools ship in the public `security-tools/` repository. That repository carries its own `SAFETY.md`. The full spec is in `../deliverable.md`.
