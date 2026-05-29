---
title: "Labs"
parent: "Month 11 - Cloud and AI System Security"
grand_parent: Curriculum
nav_order: 50
---

# Month 11 Labs

Five labs, completed in order. The first three are cloud: build, break, detect, then a pair of authorized AWS games. The last two are AI system security: attack, then review. The lab attempt floor applies to every one. The IaC-drafting AI pattern applies to the cloud labs; AI becomes the target in the AI labs. The mandatory AI Provenance log applies to all five (see the Month 11 README).

Two rules lead this month and are repeated in every relevant lab: tear down billed AWS resources after every session, and test only systems you own or are explicitly authorized to test.

| Lab | Directory | Time budget | Floor | What you build |
| --- | --------- | ----------- | ----- | -------------- |
| 11.1 AWS Free-Tier Build | `lab-01-aws-free-tier-build/` | 12 h | 90 min | A Terraform-defined VPC, EC2, S3, and RDS in your own account, plus the budget-alarm and teardown habits |
| 11.2 Misconfigure and Detect | `lab-02-misconfig-and-detect/` | 10 h | 90 min | A reproduced S3 and security-group misconfiguration, its detection in CloudTrail and GuardDuty, and the Terraform fix |
| 11.3 flaws.cloud and flaws2.cloud | `lab-03-flaws-cloud/` | 10 h | 45 min per stuck level | Hands-on intuition for how cloud misconfigurations are actually exploited, and the no-flag-confirmation habit |
| 11.4 Prompt Injection Lab | `lab-04-prompt-injection-lab/` | 13 h | 90 min | A local and a hosted chatbot you attack with direct, indirect, RAG corpus-poisoning, and MCP tool-poisoning injection, and a reproducible attack record |
| 11.5 AI System Security Review | `lab-05-ai-system-review/` | 8 h | multi-hour | A five-finding security review of a chosen LLM application in the Month 10 report format |

Total budget: roughly 53 hours of lab work, with this month's reading and the cold-revisit week running alongside the labs rather than on top of them.

Complete all five, commit a notebook entry for each (with AI Provenance), write the two end-of-month deliverables (see `../deliverable.md`), and confirm every AWS resource is torn down before advancing to Month 12.
