---
title: "Labs"
parent: "Month 9 - Defensive Operations (Blue Team)"
grand_parent: Curriculum
nav_order: 50
---

# Month 9 Labs

Four labs, building from infrastructure to authored detections to a worked investigation. Complete them in order. Each one assumes the SIEM and the query fluency the previous one built. The detection-rule drafting pattern and the mandatory AI Provenance log apply to every lab (with a false-positive analysis for every AI-drafted rule). See the Month 9 README.

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 9.1 SIEM Setup | `lab-01-siem-setup/` | 12 to 14 h | 90 min | A running SIEM ingesting your Month 6 and 7 logs, and the habit of querying real telemetry |
| 9.2 Five Sigma Rules | `lab-02-five-sigma-rules/` | 15 to 17 h | 90 min | Five authored detections, two converted and firing, each with a false-positive analysis and a response runbook |
| 9.3 SPL and KQL Drills | `lab-03-spl-kql-drills/` | 10 to 12 h | 90 min | Three detections in Splunk SPL and Microsoft KQL, plus one in your own SIEM's language, proven as SQL dialects |
| 9.4 Investigation | `lab-04-investigation/` | 12 to 14 h | multi-hour (3 h) | A worked incident and the professional IR report that is this month's deliverable |

Labs 9.1, 9.2, and 9.3 are detection-engineer work: you author and tune rules. Lab 9.4 is alert-consumer work: you receive what a detection raised and decide what happened. You build both roles on purpose, because each one teaches you what the other needs.

A scope rule runs through the whole month. Every log source you ingest comes from systems you own (your home-lab VMs and your own web app) or from a training platform whose terms authorize the activity. You do not point a SIEM agent, an IDS sensor, or a query at anything you do not own or are not explicitly authorized to monitor. Re-read each lab's scope section before you wire anything up. The IR report ships per `../deliverable.md`.
