---
title: "Labs"
parent: "Month 8 - Cryptography and PKI"
grand_parent: Curriculum
nav_order: 50
---

# Month 8 Labs

Three labs, done in order. Each has its own directory with a full specification. The lab attempt floor and the restricted AI rule apply to every one (see the Month 8 README). The AI Provenance log is required in every notebook entry, even when the only honest entry is "AI was not used on this work."

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 8.1 CryptoHack Introduction and General | `lab-01-cryptohack-intro/` | 14 to 16 h | 90 min per stuck challenge | Byte-level fluency with encodings, XOR, and the no-flag habit |
| 8.2 Build Your Own CA | `lab-02-build-your-own-ca/` | 14 to 16 h | multi-hour (3 h) | A working private CA, a served HTTPS site, three documented misconfigurations |
| 8.3 TLS Handshake Annotation | `lab-03-tls-handshake-annotation/` | 10 to 12 h | 90 min | A decrypted, message-by-message annotation of a real TLS 1.3 handshake |

Two things to flag before you start. First, the CryptoHack lab (8.1) relies on an external platform. See `../ctf-set/README.md` for the scope note on why that platform is an authorized target and nothing else is. Second, the CA lab (8.2) produces private keys, so its repository is **private**, and key material never enters public history. Lab 8.3 produces the raw material for the month's deliverable (`../deliverable.md`), so do it carefully and keep your capture.

Re-read each lab's scope and AI-guidance sections before you begin it. In a month about trust, the discipline is the lesson.
