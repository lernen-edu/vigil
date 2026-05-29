---
title: "Reading"
parent: "Month 8 - Cryptography and PKI"
grand_parent: Curriculum
nav_order: 90
---

# Month 8 Reading

Primary sources, and they matter more this month than any other. Cryptography is the domain where secondary summaries (and AI paraphrases) are most often subtly wrong. It is also where the authoritative documents (the RFCs, the NIST publications) are unusually readable. Read the RFC, not the blog about the RFC. When this month's reading and an AI explanation disagree, the reading wins, every time.

## Core (read these)

- _RFC_ [RFC 8446: The Transport Layer Security (TLS) Protocol Version 1.3](https://www.rfc-editor.org/rfc/rfc8446.html) - the ground truth for Lab 8.3. Read the handshake protocol section closely; it names and orders every message you will annotate.
- _RFC_ [RFC 5246: The Transport Layer Security (TLS) Protocol Version 1.2](https://www.rfc-editor.org/rfc/rfc5246) - obsoleted by RFC 8446, but still the definitive specification of the TLS 1.2 handshake you contrast against. Read its handshake section for the comparison.
- _RFC_ [RFC 5280: Internet X.509 Public Key Infrastructure Certificate and CRL Profile](https://www.rfc-editor.org/rfc/rfc5280) - the authoritative source for what each X.509 certificate field means and how chain validation works. Essential for Lab 8.2. Read at least the certificate-fields and basic-path-validation sections.
- _docs_ [The OpenSSL documentation](https://docs.openssl.org/master/) and your local `man openssl` plus the per-subcommand pages (`openssl-req`, `openssl-x509`, `openssl-ca`, `openssl-genpkey`, `openssl-verify`, `openssl-s_server`) - the primary reference for every command in Lab 8.2.
- _wiki_ [The Wireshark TLS wiki page](https://wiki.wireshark.org/TLS) - the authoritative reference for decrypting TLS with the `SSLKEYLOGFILE` key log mechanism, used in Lab 8.3.

## Reference (consult as needed)

- _RFC_ [RFC 6960: Online Certificate Status Protocol (OCSP)](https://www.rfc-editor.org/rfc/rfc6960) - the primary source for the revocation concepts. You do not implement OCSP, but you should be able to explain what it is for and why revocation is the hard part of PKI.
- _RFC_ [RFC 4648: The Base16, Base32, and Base64 Data Encodings](https://www.rfc-editor.org/rfc/rfc4648) - the specification behind the encoding challenges in Lab 8.1. When you want to know exactly what Base64 specifies, this is the document.
- _NIST_ [FIPS 180-4: Secure Hash Standard (SHS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.180-4.pdf) - the standard defining the SHA-2 family. Read enough to know what a cryptographic hash function guarantees and why MD5 and SHA-1 are no longer acceptable for security.
- _NIST_ [FIPS 198-1: The Keyed-Hash Message Authentication Code (HMAC)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.198-1.pdf) - the HMAC standard. The primary source for why you do not build a MAC out of a bare hash.
- _NIST_ [FIPS 186-5: Digital Signature Standard (DSS)](https://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.186-5.pdf) - the digital-signature standard. Read for what a signature provides that a MAC does not.
- _NIST_ [SP 800-57 Part 1: Recommendation for Key Management](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final) - the authoritative reference on key sizes and key lifecycle. Use it when you want to know why a key length is considered adequate, rather than trusting an AI's number.
- _NIST_ [SP 800-90A: Recommendation for Random Number Generation Using Deterministic Random Bit Generators](https://csrc.nist.gov/pubs/sp/800/90/a/r1/final) - the primary source behind the "weak RNG" failure mode. Skim enough to understand why predictable randomness silently destroys everything built on it.

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read it before your first lab. Decision-tree question Q2 ("could the AI's output be wrong in a way you would not catch?") is the entire month's AI discipline in one line.
- _required_ `SAFETY.md` at the repo root, specifically the section on legal targets: CryptoHack and your own machine are in scope; nothing else is.

## A note on sources, and on AI in crypto

This reading list leans hard on RFCs and NIST publications because they are the only sources that do not hallucinate. When you ask AI to explain a crypto concept in plain language (the one use this month allows), treat every factual claim it makes as a guess to confirm against the documents above. AI will tell you, with total confidence, that one TLS message comes before another when it does not, that a mode of operation provides a property it does not, or that a key size is safe when the standard says otherwise. The reading list is your defense. The verification ritual is the test of whether you used it. In this field, "I read it in the RFC" is the only sentence that ends an argument.
