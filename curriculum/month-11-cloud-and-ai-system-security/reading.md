---
title: "Reading"
parent: "Month 11 - Cloud and AI System Security"
grand_parent: Curriculum
nav_order: 90
---

# Month 11 Reading

Primary sources first, as always. This month has two halves, so the reading does too. The cloud half leans on AWS's own documentation, the CIS benchmark, and the Terraform provider docs; the AI half leans on the OWASP GenAI project, the protocol specifications, and the model-hub documentation. Read the primary source before any blog that paraphrases it; the whole point of the verification ritual is that you can check AI's claims and a reviewer's claims against the real reference.

## Cloud security (Weeks 1 to 2)

### Core

- _docs_ AWS "Shared Responsibility Model" (the canonical statement of where AWS's responsibility ends and yours begins).
- _docs_ The Terraform AWS provider documentation (primary source for every resource you write in Labs 1 and 2).
- _docs_ AWS S3 "Blocking public access to your Amazon S3 storage" (the four Block Public Access settings: `BlockPublicAcls`, `IgnorePublicAcls`, `BlockPublicPolicy`, `RestrictPublicBuckets`).
- _docs_ AWS IAM user guide, especially policies, roles, and the security best practices section (least privilege; prefer roles and short-lived credentials over long-lived access keys).
- _docs_ AWS CloudTrail user guide (what is logged, the event record structure, management versus data events).
- _docs_ AWS GuardDuty user guide (finding types, severities, the data sources it analyzes, and its pricing model).
- _reference_ The CIS Amazon Web Services Foundations Benchmark (the authoritative, vendor-neutral source for the "common misconfigurations" your `cloud-misconfigs.md` documents; read the IAM, S3, networking, and logging sections).

### Reference (consult as needed)

- _docs_ AWS VPC, EC2, and RDS user guides (the per-service shared-responsibility and free-tier-eligibility details).
- _docs_ AWS Budgets documentation (for the cost alarm; read this before you spend anything).
- _docs_ AWS EC2 instance metadata service documentation, including IMDSv2 (for the metadata-as-credential-source levels in Lab 3).
- _docs_ The AWS pricing pages for every service you provision (check before you apply; the free tier has edges).

## AI system security (Weeks 3 to 4)

### Core

- _docs_ The OWASP Top 10 for LLM Applications (2025), the OWASP Gen AI Security Project. The full list, by ID and name, is the taxonomy for Labs 4 and 5 and the deliverable. Read the entry for each of the ten, not just the headline. _Note: every "(2025)" citation in this month is pinned to that revision on purpose. A 2026 edition is in progress at the OWASP GenAI project; when it lands, the LLM01 to LLM10 numbering and names may shift, so treat the 2025 citations as dated and check the OWASP GenAI project for the current revision before you cite it in a deliverable._
- _docs_ The OWASP Agentic Security Initiative, "Agentic AI: Threats and Mitigations" (the threat taxonomy for agentic and multi-agent systems), and the MAESTRO layered threat-modeling model that accompanies it.
- _docs_ The Model Context Protocol specification at the official site (the architecture, and the security guidance, including the human-in-the-loop principle for tool invocation). Read this before reviewing any MCP-based application in Lab 5.
- _docs_ The OWASP MCP Top 10 (the emerging industry framework for MCP-specific risks: tool poisoning, tool definition mutation, cross-server interference, credential aggregation).
- _docs_ HuggingFace Hub documentation: "Pickle Scanning" (why pickle weights can execute code on load, via the `REDUCE` and `GLOBAL` opcodes, and what the Hub's import scanner does) and the `safetensors` documentation (the safe weight format and why it carries no code).

### Concepts

- _reference_ Simon Willison's writing on prompt injection, particularly the original framing of the problem and the direct-versus-indirect distinction. He coined much of the working vocabulary; read it for the why, not just the what.
- _docs_ The Ollama documentation (running and prompting a local model; the API for your Lab 4 harness).
- _docs_ Your hosted model provider's API documentation and its usage and safety policy. You must know your own provider's terms before you test an application against it.

### Reference (consult as needed)

- _reference_ The Cloud Security Alliance "Agentic AI Red Teaming Guide" (practical agentic vulnerability categories; useful if your Lab 5 application is agentic).
- _docs_ The Python `pickle` and `pickletools` standard-library documentation (the `pickletools` module reads a pickle's opcodes without executing them; relevant to the supply-chain assessment).

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read it before Lab 1 (the IaC-drafting pattern and the provenance discipline) and again before Lab 4 (rule 5: the line between studying injection on your own systems and weaponizing it). The decision trees there are the operational version of this month's discipline.
- _required_ `SAFETY.md` at the repo root. Re-read the "what counts as a legal target" section; this month adds AWS resources you provision and AI systems you run, and removes nothing.

## A note on sources for AI security

AI security moves fast, and a great deal of what is written about it online is vendor marketing or speculation. When you cite a source in your deliverables, cite the OWASP GenAI project, the protocol specifications, the model-hub documentation, or a named practitioner with primary-source standing, not a blog summarizing them. AI tools will confidently cite frameworks and CVEs that do not exist; the primary sources above are how you catch that, and catching it is the skill this whole course exists to build.
