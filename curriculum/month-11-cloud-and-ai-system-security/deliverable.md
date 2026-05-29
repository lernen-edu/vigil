---
title: "Deliverable"
parent: "Month 11 - Cloud and AI System Security"
grand_parent: Curriculum
nav_order: 91
---

# Month 11 Deliverables: cloud-misconfigs.md and ai-system-review.md

This month produces two deliverables, one per half. Both are portfolio pieces a hiring manager will read, and both carry an AI Provenance section, because that discipline is what a 2026 employer screens for. They mirror the two surfaces of the month: the cloud writeup is a defender's reference; the AI review is an attacker's report in the Month 10 format.

## Deliverable 1: cloud-misconfigs.md

### What you produce

A writeup, `cloud-misconfigs.md`, documenting the **five most common AWS misconfigurations**, and for each: what it is, what it exposes, how it is detected, and the **Terraform control that prevents it**. This is the defender's reference you would hand a team that is about to build on AWS.

Fed by Lab 1 (you built the correct baseline), Lab 2 (you reproduced two misconfigurations, detected them, and fixed them in Terraform), and Lab 3 (you saw several exploited from the attacker's side in the flaws games and mapped each to a control).

### Required structure

For each of the five misconfigurations, a section containing:

- **The misconfiguration**: what it is, in one or two sentences, with the AWS primitive involved (a bucket, a security group, an IAM policy, a logging setting, an encryption setting).
- **Impact**: what an attacker gains, and the blast radius. Be concrete; "data exposure" is weaker than "any unauthenticated internet user can list and download every object in the bucket."
- **Detection**: how you would notice it, by which signal (a CloudTrail event, a GuardDuty finding, a configuration check), and what that signal does and does not catch.
- **Prevention in Terraform**: the control that prevents it, expressed as Terraform. This is **your** code, written and verified by you, drawn from your Lab 1 and Lab 2 work. It must be code you can defend line by line under the verification ritual.
- **Provenance note**: where AI drafted any of the Terraform and how you verified it (this rolls up into the deliverable's AI Provenance section).

Anchor your selection of the five on the CIS Amazon Web Services Foundations Benchmark rather than picking from memory, so the choice has provenance. Reasonable selections include: a publicly accessible S3 bucket (missing Block Public Access), an over-permissive security group (ingress from `0.0.0.0/0` on a management port), an over-broad IAM policy or a long-lived access key where a role belongs, CloudTrail not enabled or not covering all regions, and unencrypted data at rest (S3 or RDS). At least two must be ones you personally reproduced and fixed in Lab 2.

### Acceptance criteria

- **Five distinct misconfigurations**, each with all five subsections above.
- **The Terraform actually prevents the misconfiguration.** A reviewer (and the tutor) can read the control and see how it closes the exposure. The S3 control includes all four Block Public Access settings; the network control narrows ingress to a specific source; and so on.
- **At least two misconfigurations trace to your own Lab 2 work**, with the detection grounded in the CloudTrail or GuardDuty evidence you actually saw.
- **An AI Provenance section** documenting where AI drafted Terraform and how you verified each block. This is the public-facing version of your notebook provenance.
- **No live credentials, no real account IDs, no real bucket names** anywhere in the document. Redact or use placeholders; the writeup is going in your portfolio.
- **No em dashes**, to match the house style; use commas, colons, parentheses, or semicolons.

### Verification

The tutor confirms the five sections are complete and the Terraform controls map to their misconfigurations, then runs the verification ritual on one Terraform block, chosen at random, with your AI session closed. You explain why that control closes that exposure. If you cannot, the block returns until you can defend it.

## Deliverable 2: ai-system-review.md

### What you produce

A security review, `ai-system-review.md`, of **one open-source LLM application you chose, ran yourself, and analyzed**, documenting **five distinct attack paths**, formatted exactly like a Month 10 pentest report. This is the artifact that demonstrates you can do AI security review work, against the newest surface in the field.

Fed by Lab 4 (where you demonstrated injection, indirect injection, and tool abuse against your own chatbots) and Lab 5 (where you scoped, analyzed, attacked, and reported on your chosen application).

### Required structure

The Month 10 pentest-report structure, applied to an AI application:

- **Scope and authorization**: the application by name and version, your deployment of it, the explicit statement that you own and are authorized to test it, and what is out of scope (anyone else's instance; the upstream model's own infrastructure).
- **Methodology**: how you approached the review (the architecture and attack-surface map, the OWASP LLM mapping, the supply-chain assessment).
- **Findings**: five distinct findings, each with:
  - A title and a **severity rating** (with a defensible rationale, not just a label).
  - The **affected component**.
  - The **OWASP LLM Top 10 (2025) category** it maps to.
  - A **reproduction summary**: the technique, described clearly enough to be reproduced, but **not** a copy-paste exploit and **never** a payload aimed at producing harmful content. Verbatim payloads stay in your private notebook.
  - The **impact**.
- **Recommendations**: each tied to a finding, written so the application's maintainer could act on it. Note where a mitigation is only partial (system-prompt defenses, for example, are partial by nature).
- **AI Provenance appendix**: your provenance log restructured as the report's appendix, keeping AI's drafting and structuring help clearly separate from your own analytical findings.

### Acceptance criteria

- **Five distinct attack paths**, mapping to distinct OWASP LLM categories (not one vulnerability described five ways). At least one is an indirect-injection or supply-chain path.
- **A supply-chain assessment** is present, covering the model's source and weight format (pickle versus `safetensors` and the deserialization risk), provenance signals, and the dependency posture.
- **Severity ratings are defensible**, with rationale; no inflated criticals without justification.
- **Recommendations are actionable** and tied to findings, with partial mitigations flagged as partial.
- **The report stays within `AI-ETHICS.md` rule 5**: it reviews to find and describe weaknesses, and contains no harmful payloads and no attacks against systems you do not own.
- **An AI Provenance appendix** makes clear the findings are your analysis, not AI's.
- **No real secrets, no verbatim harmful payloads, no real third-party data** in the document.
- **No em dashes**; house style.

### Verification

The tutor confirms the five findings are distinct and mapped, the supply-chain assessment is present, and the format matches a Month 10 report, then runs the verification ritual on one finding: you explain the attack path at the trust-boundary level, your severity rationale, and why your mitigation is sufficient or only partial, from memory. A finding you cannot defend returns.

## Why these are the Month 11 deliverables

Together they prove you can reason about both of the API-driven surfaces a 2026 employer is most worried about. `cloud-misconfigs.md` shows you can build, detect, and prevent on the cloud control plane, with Terraform you own. `ai-system-review.md` shows you can take an AI application apart with the same professional rigor you brought to a vulnerable machine in Month 10. The pair, with their provenance sections, is a compact demonstration of the exact competence the entry-level market is short of: fundamentals, plus the two new surfaces, plus disciplined AI fluency.

## How to know they are done

- `cloud-misconfigs.md` committed: five misconfigurations, each with impact, detection, and preventive Terraform you can defend; AI Provenance section present; at least two grounded in your own Lab 2 work.
- `ai-system-review.md` committed: five distinct attack paths in the Month 10 format, supply-chain assessment present, defensible severities, actionable recommendations, AI Provenance appendix.
- Both pass the verification ritual.
- Every AWS resource provisioned this month is torn down (the cloud deliverable does not require a live environment; it requires the writeup).
- Five lab notebook entries committed, each with a complete AI Provenance section.
- `.tutor/progress.md` updated to "Month 11 complete; ready for Month 12."
