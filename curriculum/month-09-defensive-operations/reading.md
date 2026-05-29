---
title: "Reading"
parent: "Month 9 - Defensive Operations (Blue Team)"
grand_parent: Curriculum
nav_order: 90
---

# Month 9 Reading

Primary sources first. The detection format, the query languages, the IR framework, and the attacker taxonomy this month all have authoritative homes. Read those, not a blog that paraphrases them. The whole point of the detection-rule drafting pattern is that you can judge an AI-drafted rule against the real specification, and you can only do that if you have read it.

## Core: detection authoring (Lab 9.2)

- _docs_ [Sigma Detection Format documentation](https://sigmahq.io/docs/) and the [project home](https://sigmahq.io/). The `logsource`, `detection`, and `condition` semantics. Short, and worth reading in full before you write a rule.
- _spec_ [The Sigma rule specification](https://github.com/SigmaHQ/sigma-specification/) (modifiers, filters, taxonomy). The authoritative reference when the documentation is ambiguous.
- _repo_ [The SigmaHQ main rule repository](https://github.com/SigmaHQ/sigma). Read real, community-reviewed rules to see how experienced authors handle field selection and exclusions. Read them to learn the craft, not to copy a rule into your lab.
- _docs_ The `sigma-cli` documentation for `sigma convert`, the available backends, and pipelines. The current tooling. Do not follow a 2021 tutorial that uses the older `sigmac` invocation.

## Core: SIEM and query languages (Labs 9.1 and 9.3)

- _docs_ The Wazuh documentation (deployment, agent enrolment, decoders and field extraction) or the Security Onion documentation (installation, component services, importing and querying), whichever SIEM you choose for Lab 9.1. Primary source for the pipeline.
- _docs_ The Splunk Search Reference and SPL documentation (the `search`, `stats`, `where`, `table`, `sort` commands), plus the Splunk Free documentation for the daily ingestion cap and free-tier limits.
- _docs_ The [Kusto Query Language (KQL) documentation](https://learn.microsoft.com/en-us/kusto/query/) on Microsoft Learn (the `where`, `summarize`, `project`, `join`, `sort` operators).
- _docs_ The query-language documentation for the SIEM you built in Lab 9.1, which depends on which one you chose. **Wazuh's indexer is an OpenSearch fork**, so its query language is the [OpenSearch Piped Processing Language (PPL)](https://docs.opensearch.org/latest/search-plugins/sql/ppl/index/) in the OpenSearch Query Workbench, with Dashboards Query Language (DQL) and Lucene query-string syntax in the search bar. **Security Onion 2.4 is built on Elasticsearch** (Logstash, Kibana, Elastic Agent), so its pipe language is [Elastic's ES|QL](https://www.elastic.co/guide/en/elasticsearch/reference/current/esql.html) in Kibana, with Kibana Query Language (a Lucene-style filter syntax, not the Kusto KQL you will meet in Sentinel) or Lucene in the search bar. There is no PPL and no OpenSearch Query Workbench in Security Onion. The trap to avoid: OpenSearch PPL and Elastic's ES|QL are different languages in the same family, so confirm which one your stack actually speaks before you reuse a query.
- _docs_ [Microsoft Sentinel pricing and billing](https://learn.microsoft.com/en-us/azure/sentinel/billing), for the free-trial terms, the ingestion cap, and how billing works after the trial. Read this before you provision anything, and set a teardown reminder.
- _reference_ Your own Month 7 SQL notes. The SIEM query languages are SQL dialects. Keep the original beside you so the dialects are a translation, not a fresh memorization.

## Core: IDS and IPS (concept; Lab 9.2 and the cold revisit)

- _docs_ [Suricata Rules documentation](https://docs.suricata.io/en/latest/rules/index.html). How a network signature is structured, and what inline blocking (IPS) versus passive alerting (IDS) means for sensor placement. For the cold-revisit week, also read the Suricata command-line usage for offline pcap mode (`suricata -r <pcap> -S <rules> -l <out>`), so you can run your own rule against a Month 4 capture and watch it fire in `fast.log` or `eve.json` without standing up a sensor.
- _docs_ [Snort 3 rule writing guide](https://docs.snort.org/rules/) and the [Snort project home](https://www.snort.org/). The rule header and body, and the action keywords. You will read a rule, not become a Snort expert this month.

## Core: incident response and attacker taxonomy (Lab 9.4)

- _publication_ [NIST SP 800-61 Revision 3 (2025)](https://csrc.nist.gov/pubs/sp/800/61/r3/final), Incident Response Recommendations and Considerations for Cybersecurity Risk Management. The current guidance, which reframes incident response as risk management aligned to the CSF 2.0 functions.
- _publication_ NIST SP 800-61 Revision 2, the long-standing four-phase incident-handling lifecycle (Preparation; Detection and Analysis; Containment, Eradication, and Recovery; Post-Incident Activity). Most working IR reports are still structured around this lifecycle, so read it alongside Revision 3. The tension between the two is the month's lesson on judgment versus checklist.
- _docs_ [The MITRE ATT&CK website](https://attack.mitre.org/). Use the matrix to navigate from a behavior to its tactic and technique, and the technique pages to confirm a mapping and see which data sources a technique touches. ATT&CK is a map, not a score.

## Concepts and craft

- _reference_ A published, professional incident-response report, or a public vendor or CERT post-incident report. Read it as a model for the structure and register of your Lab 9.4 deliverable. You are imitating the form of real reports, not a CTF writeup.
- _reference_ The Pyramid of Pain (David Bianco), for why some indicators of compromise cost an attacker more to change than others. It informs how you weight the IOCs you extract in Lab 9.4.
- _docs_ The Microsoft Windows security audit event documentation (4624, 4625, 4688) and the Sysmon documentation, for the exact event IDs and field names your detections target. Reinforces Month 6.

## On AI use this month

- _required_ `AI-ETHICS.md` at the repo root. Re-read before your first lab. The detection-rule drafting pattern, the mandatory false-positive analysis, the synthesis-only allowance in Lab 9.4, and the rule against pasting lab telemetry into public AI services all come from here.

## A note on AI-drafted rules and queries

When AI drafts a Sigma rule, an SPL search, or a KQL query, two things must be verified against the sources above before you trust it. First: every field and function it names must actually exist, in your log source and in the dialect. AI confidently invents plausible field names and query functions that do not exist, and a rule against a nonexistent field parses cleanly and never fires. Second: the rule's logic must survive contact with benign activity at production volume. The specification will not tell you this, but your own environment and your false-positive analysis will. The reading list is your defense against the first failure. The verification ritual is the test of whether you used it.
