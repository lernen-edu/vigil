---
title: "Labs"
parent: "Month 4 - Network Tools and Packet Analysis"
grand_parent: Curriculum
nav_order: 50
---

# Month 4 Labs

Three labs, done in order. Each has its own directory with a full spec. The lab attempt floor and the no-AI rule apply to every one. Month 4 is in the AI-free zone, so there is no AI guidance section in any lab and no AI Provenance section in any notebook entry.

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 4.1 PCAP Analysis | `lab-01-pcap-analysis/` | 20 to 24 h | 90 min per capture | The reading habit and five SOC-handoff reports |
| 4.2 Nmap Exploration | `lab-02-nmap-exploration/` | 10 to 12 h | 90 min | The ability to explain every scan at the packet level, own lab only |
| 4.3 Wireshark CTF | `lab-03-wireshark-ctf/` | 10 to 12 h | 45 min per stuck challenge | Display-filter and Follow-Stream fluency under pressure |

Lab 4.2 carries a hard scope rule: you run `nmap` only against the VMs on your own host, never against any other system. Re-read the scope section in that lab before you scan anything.

Lab 4.1 works on captures you download from the public training sources listed in `../ctf-set/README.md`. Reading a capture file is passive and carries no scope concern. The provenance of the files does carry one, and both that lab and the `ctf-set` note address it.

Complete all three, commit a notebook entry for each, and produce the five PCAP analysis reports that are the month's deliverable (see `../deliverable.md`) before advancing to Month 5.
