---
title: "Reading"
parent: "Month 4 - Network Tools and Packet Analysis"
grand_parent: Curriculum
nav_order: 90
---

# Month 4 Reading

Free and high-signal, primary sources first. The official tool documentation is the authority this month; read it before any blog that paraphrases it. Reading the real reference, rather than a narrated summary, is the same discipline that lets you judge AI output starting next month. This is the last AI-free month; spend it reading.

## Core (the tool documentation you will use)

- _docs_ [Wireshark User's Guide](https://www.wireshark.org/docs/wsug_html_chunked/) - the primary reference for the capture, the Statistics menus, Follow Stream, and Export Objects you use in Labs 4.1 and 4.3.
- _docs_ [Wireshark Display Filter Reference](https://www.wireshark.org/docs/dfref/) - the field names and operators for display filters, including `matches` (regex) and `contains`. This is the reference behind every filter you write.
- _docs_ [tcpdump man page](https://www.tcpdump.org/manpages/tcpdump.1.html) and [pcap-filter man page](https://www.tcpdump.org/manpages/pcap-filter.7.html) - the command-line capture tool and the BPF capture-filter syntax. Read both; that filter syntax is shared with Wireshark capture filters.
- _docs_ [Nmap Reference Guide](https://nmap.org/book/man.html) - the authoritative source for scan types, port states, timing templates, and detection. The man page on your machine (`man nmap`) is the same content. Primary source for Lab 4.2.
- _docs_ [Nmap Scripting Engine documentation](https://nmap.org/book/nse.html) - what the NSE is, its script categories, and why category matters for scope and noise (Lab 4.2, Stage 3).
- _docs_ [Ncat / netcat documentation](https://nmap.org/ncat/guide/) - what `netcat` sends and listens for; the "TCP/IP Swiss Army knife" at the packet level.

## Concepts

- _reference_ The `traceroute` man page on your own machine (`man traceroute`) - how TTL expiry and ICMP Time Exceeded messages map a path, and how the UDP, ICMP, and TCP variants differ through firewalls.
- _reference_ RFC 792 (ICMP), the sections on Time Exceeded and Destination Unreachable - the primary source for why `traceroute` and UDP scans behave as they do. You read IP and TCP headers in Month 3; this is the ICMP companion.
- _reference_ The TCP three-way handshake and TCP flags - your own Month 3 notebook entry and RFC 9293 (TCP). You need this cold to tell an open port from a closed one in a capture.

## PCAP sources and challenge platforms

- _source_ [MalwareTrafficAnalysis.net](https://www.malware-traffic-analysis.net/) - the source of the captures for Lab 4.1. Its exercises and tutorials index provides labeled captures of real malicious traffic, authorized for exactly this training use. See `ctf-set/README.md` for how to use it without spoiling the analysis.
- _source_ The Wireshark project's sample-capture wiki - a clean source of protocol-practice captures (used in Lab 4.3's Stage 1 and 2 practice). Lighter on malicious traffic than the primary source, but useful for drilling the method on traffic you can read safely.
- _platform_ The TryHackMe "Wireshark CTFs" room and its prerequisite Wireshark rooms - the basis of Lab 4.3. Authorized through the platform's terms of use. Listed with alternatives in `ctf-set/README.md`.

## On reading documentation, one last time before AI unlocks

This month is the last of the AI-free zone. Starting in Month 5 you may use AI under discipline, and the only way to use it safely is to be able to check it against the real reference. Every filter, flag, and protocol behavior you internalize this month from the primary sources above is part of the toolkit you will use to catch AI when it confidently describes a Wireshark filter that does not exist, or an `nmap` flag that does not do what it claims.

## A note on sources

When a lab asks you to cite a source, cite from "Core" or "Concepts," not from a blog and not from a video walkthrough. Tool documentation and RFCs are the authority. Blog posts and YouTube walkthroughs are where CTF spoilers and confidently-wrong claims live. Building the habit of reaching for the primary source now is what makes you able to evaluate AI output in Month 5.
