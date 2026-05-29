---
title: "Deliverable"
parent: "Month 8 - Cryptography and PKI"
grand_parent: Curriculum
nav_order: 91
---

# Month 8 Deliverable: The Annotated TLS 1.3 Handshake (plus a private CA)

## What you produce

Two things, with a deliberate split between what is public and what is private:

1. **`tls-handshake-annotated.md`** (the headline deliverable): a message-by-message walkthrough of a real TLS 1.3 handshake you captured and decrypted yourself in Lab 8.3, written so a peer one month behind you could follow it. This is a portfolio piece. It shows that you can read a real cryptographic protocol exchange off the wire and explain it precisely. A hiring manager can probe that skill in five minutes, and it separates "I read about TLS" from "I understand TLS."

2. **A working private CA and certificates** from Lab 8.2: your root CA certificate, the issued server certificate, and the configuration and notes documenting the three deliberate misconfigurations. These live in a **private** repository because they involve key material.

The deliverable is the pair, with the public writeup grounded in the private hands-on work.

## The public / private split, stated explicitly

This split is the point, not a formality. Getting it right is itself part of the deliverable.

**Public (your portfolio):**

- `tls-handshake-annotated.md`, the annotated handshake. There is nothing secret in a TLS handshake to a public website you chose to visit; the handshake negotiates keys, it does not reveal them, and the certificate it carries is the server's public certificate that anyone can fetch. So the annotation can be public. Confirm before publishing that your capture was to a public site you deliberately chose, on your own network, with nothing sensitive in flight, and that you are annotating the handshake (not dumping decrypted application data).

**Private (never public, ever):**

- The CA private key and the server private key from Lab 8.2. Private keys never enter a public repository, in any commit, ever, not even for a throwaway lab CA.
- The Lab 8.2 repository as a whole, which holds those keys.
- The TLS key log file from Lab 8.3, which contains session secrets. This is deleted at the end of Lab 8.3, not committed anywhere.

If you are unsure whether something is safe to make public, the default is private. The habit of erring toward private with anything key-adjacent is one of the most valuable things this month builds.

## Specification for `tls-handshake-annotated.md`

- **Source.** A real TLS 1.3 handshake you captured and decrypted yourself (Lab 8.3). Not a textbook example, not an AI-generated transcript. The annotation must be grounded in your own capture, and it should say so ("captured from my own browser connecting to [site] on [date]").
- **Coverage.** Every message in the TLS 1.3 handshake, in order: the ClientHello (with its key-share, supported-groups, and supported-versions extensions), the ServerHello (with the chosen cipher suite and the server's key share), the point after which the handshake becomes encrypted, the encrypted flight (encrypted extensions, the now-encrypted certificate, certificate verify, server Finished), and the client Finished. For each message: what it is, what it carries, and what cryptographic decision it represents.
- **The TLS 1.2 contrast.** A section contrasting your 1.3 handshake with the TLS 1.2 handshake it replaced: which messages differ, why 1.3 needs fewer round trips, why the certificate is now encrypted, and why forward secrecy is mandatory in 1.3.
- **Accuracy over polish.** Every claim must be traceable either to what you observed in your own capture or to the RFC (8446 for 1.3, 5246 for 1.2). This is a crypto deliverable; a confident, wrong sentence is worse than a plain, correct one. If you cannot trace a claim to your capture or the RFC, cut it.
- **Audience and tone.** A peer one month behind you. Define terms the first time you use them. Conversational and precise, the house tone of the course's prose.
- **No em dashes**, to match the house style of the course. Use commas, colons, parentheses, or semicolons.

## Acceptance criteria

- `tls-handshake-annotated.md` annotates a real, self-captured TLS 1.3 handshake message by message, with the TLS 1.2 contrast section present.
- Every technical claim is traceable to the capture or to the RFC; the writeup names which.
- The writeup defines its terms and reads cleanly for a peer one month behind.
- A private repository contains the working CA, the issued server certificate, the three documented misconfigurations, and a `.gitignore` that excludes key material, with **no private key in any commit in the repository's history.**
- The TLS key log file from Lab 8.3 has been deleted, not committed.
- An **AI Provenance** statement accompanies the deliverable, consistent with the month's restriction: it states which plain-language concept questions (if any) AI was asked, that AI did not annotate the handshake or do any crypto math, and what each AI explanation was verified against. If AI was used only for plain-language concepts, say so; if not at all, say that.
- No em dashes anywhere in the writeup.

## Verification

The tutor confirms the private repository exists and contains no key material in its history (a single leaked key fails the deliverable), confirms the key log file was deleted, and confirms the annotated writeup covers every handshake message with the 1.2 contrast.

Then it runs the verification ritual on the annotation: it points at one handshake message you annotated (likely the ServerHello or the key-share extension) and asks you to explain, from memory with your AI session closed, what that message carries, what cryptographic decision it represents, and how the same step differed in TLS 1.2. If you captured and read the handshake yourself, this is easy. If AI wrote the annotation, it is not. The deliverable is not done until you can defend the message it picks.

## Why this is the Month 8 deliverable

A TLS handshake is where every primitive in this month assembles: symmetric and asymmetric crypto, key agreement, hashing, signatures, certificates, and the chain of trust, all in one short exchange that secures most of the internet. Annotating a real one proves you understand not just the parts but how they fit. The public/private split proves something a hiring manager cares about just as much: that you handle key material with the discipline of someone who can be trusted with production secrets. The annotated handshake goes in your portfolio. The discipline of keeping the keys out of it goes on your record as a practitioner who does not leak.

## How to know it is done

- `tls-handshake-annotated.md` committed (to your public writeups, with the keys-private discipline confirmed), annotating a real captured TLS 1.3 handshake message by message, with the 1.2 contrast.
- A private repository with the working CA, the server certificate, and the three documented misconfigurations, and no private key anywhere in its history.
- The Lab 8.3 key log file deleted.
- Three lab notebook entries committed, each with a complete and honest AI Provenance section.
- The cold-revisit week's sub-tasks completed and logged.
- `.tutor/progress.md` updated to "Month 8 complete; ready for Month 9."
