---
title: "Reading"
parent: "Month 7 - Web Application Security (and SQL)"
grand_parent: Curriculum
nav_order: 90
---

# Month 7 Reading

Primary sources first. The vendors and standards bodies here (OWASP, PortSwigger, the database projects, the relevant RFCs) wrote the authoritative material; read it before any third-party tutorial. The whole point of the brainstorming-variations pattern is that you can judge an AI-suggested payload, and you can only do that against the real reference for the flaw class.

A note on editions: this month uses the **2025** edition of the OWASP Top 10, published at `https://owasp.org/Top10/2025/`. Read that one, and confirm the category names and ordering against the official page when you cite them (OWASP iterates an edition through release candidates before it is finalized, so the exact wording can shift slightly; the official URL is always authoritative). If a blog or an older course cites the 2021 ordering (where injection was A03 and broken access control was A01), it is out of date for this month; the 2025 list reorders and renames several categories.

## Core: SQL (Week 1, Lab 7.1)

- _docs_ The PostgreSQL documentation, tutorial and reference sections on `SELECT`, joins, aggregate functions (`GROUP BY`, `HAVING`), subqueries, and `PREPARE` (prepared statements). The primary source for the relational and parameterization concepts of the SQL week.
- _docs_ The MySQL reference manual, the chapters on `JOIN` syntax, `GROUP BY` and aggregates, subqueries, and prepared statements (`PREPARE`/`EXECUTE`). Read alongside the Postgres docs so the dialect differences register.
- _reference_ Either database's explanation of `NULL` and three-valued logic. This is what makes outer joins and `NOT IN` behave the way they do; it is the source of the most common SQL surprises.

## Core: the OWASP Top 10 (Weeks 2 to 4, Labs 7.2 to 7.5)

- _docs_ The OWASP Top 10 (2025) list and its per-category pages, at `https://owasp.org/Top10/2025/`. This is the map for the whole back half of the month. The 2025 categories are: A01 Broken Access Control, A02 Security Misconfiguration, A03 Software Supply Chain Failures, A04 Cryptographic Failures, A05 Injection, A06 Insecure Design, A07 Authentication Failures, A08 Software or Data Integrity Failures, A09 Security Logging and Alerting Failures, A10 Mishandling of Exceptional Conditions.
- _docs_ The OWASP Cheat Sheet Series, specifically the cheat sheets for SQL injection prevention, cross-site scripting prevention, cross-site request forgery prevention, and authentication. These are the fix-side primary sources you use in Lab 7.5.

## Core: HTTP, sessions, and the browser security model

- _spec_ RFC 9110 (HTTP Semantics): methods, status codes, and the meaning of idempotency (which underlies CSRF). You do not need to read it cover to cover; read the sections on methods and status codes.
- _docs_ MDN Web Docs on HTTP cookies, the same-origin policy, and CORS. MDN is the standard reference for browser behavior; these three pages are the foundation for the session and CSRF labs.
- _docs_ MDN on the `Set-Cookie` attributes `HttpOnly`, `Secure`, and `SameSite`, and what each defends against.

## Core: the tool

- _docs_ The Burp Suite Community documentation: proxy configuration, installing the Burp CA certificate, the Proxy history, and Repeater. PortSwigger makes both the tool and the Academy; their docs are the primary source.
- _docs_ The PortSwigger Web Security Academy learning materials for each flaw class (SQL injection, XSS, CSRF, access control, SSRF, file upload, authentication). Each topic page is a primary-source explanation written by the tool's authors.
- _legal_ The PortSwigger Web Security Academy terms of use. Read this so you know exactly what you are authorized to test and where that authorization ends.

## The practice applications

- _docs_ The OWASP Juice Shop project documentation (deployment and the project's statement of purpose). Use it to set up and understand the app; do not use the companion solutions guide, which is a walkthrough and would defeat Lab 7.3.
- _docs_ The DVWA project documentation: setup, the security-level switch, and its explicit warning against exposing the app. DVWA's module source is open; read it for the low-versus-high comparison in Lab 7.4.

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read it before your first web lab. The brainstorming-variations pattern, the provenance discipline, the data-handling rule, and the disclosure expectation for the custom app's public repo all come from here.
- _required_ `SAFETY.md` at the repo root. The four-target scope rule for this month is its direct application; the custom-app teardown obligation is too.

## A note on sources

When a lab asks you to cite a source, cite OWASP, PortSwigger, the database documentation, the relevant RFC, or MDN, not a blog and not a video walkthrough. Web security is a field where outdated and wrong tutorials are abundant and confident, and where AI will cite payloads and "best practices" that no longer apply. Building the habit of reaching for the primary source is what lets you tell the current technique from the stale one, and the working payload from the plausible-looking dud.
