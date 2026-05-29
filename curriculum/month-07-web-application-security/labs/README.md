---
title: "Labs"
parent: "Month 7 - Web Application Security (and SQL)"
grand_parent: Curriculum
nav_order: 50
---

# Month 7 Labs

Five labs, completed in order. Lab 7.1 builds the SQL fluency that every web lab depends on and is AI-free. Labs 7.2 to 7.5 are web security against authorized targets only, under the brainstorming-variations AI pattern. The lab attempt floor, the scope rule, and the mandatory AI Provenance log apply to every one (see the Month 7 README).

| Lab | Directory | Time budget | Floor | What you build or produce |
| --- | --------- | ----------- | ----- | -------------------------- |
| 7.1 SQL Fluency | `lab-01-sql-fluency/` | 12 to 14 h | 90 min | Hand-written fluency across the full SQL surface, AI-free |
| 7.2 PortSwigger Apprentice | `lab-02-portswigger-apprentice/` | 12 to 14 h | 90 min per stuck lab | Burp Suite as a daily driver and apprentice-level coverage of seven flaw classes |
| 7.3 OWASP Juice Shop | `lab-03-owasp-juice-shop/` | 9 to 11 h | 90 min per stuck challenge | Twenty documented challenges with reproduction steps |
| 7.4 DVWA Walkthrough | `lab-04-dvwa-walkthrough/` | 9 to 11 h | 90 min | One documented vulnerability per OWASP Top 10 (2025) category, via Burp |
| 7.5 Custom Vulnerable App | `lab-05-custom-vulnerable-app/` | 8 to 10 h | 90 min | A small app with two deliberate, documented flaws (your code) |

Every lab after the first carries a hard scope rule: Burp and every crafted request run only against your own DVWA, your own Juice Shop, the PortSwigger Web Security Academy (authorized by its own terms), or your own custom app. Re-read each lab's scope section before you run anything. Lab 7.5's app is removed from any public hosting once the lab is done; its vulnerable code is yours to write and never the tutor's to provide.

The total lands at roughly 55 hours. SQL fluency and the PortSwigger ladder are the heaviest because they are the foundation everything else stands on. Commit a notebook entry for each lab, then write the end-of-month `web-security-portfolio.md` (see `../deliverable.md`) before advancing to Month 8.
