---
title: "Deliverable"
parent: "Month 3 - Networking Fundamentals"
grand_parent: Curriculum
nav_order: 91
---

# Month 3 Deliverable: The Annotated Home-Lab Network Diagram

## What you produce

Two things, delivered together:

1. A **network diagram of your home lab**, annotated with subnets, routing, DHCP scopes, and DNS resolvers. This is the network you built in Lab 3.2, drawn so that another engineer could understand its addressing and traffic flow at a glance.
2. The **three Wireshark captures from Lab 3.3** (DHCP, DNS, TCP three-way handshake), each with your own field-by-field annotations.

Both live in your lab notebook, or in a `month-03-networking/` directory in your work repo with a link from the notebook. The diagram proves you can model a network. The annotated captures prove you can read one. Together they are the portfolio evidence that the model is in your head. Every later month and every interview assumes it.

## Specification: the diagram

- **Scope:** your own lab network from Lab 3.2 (the two subnets, the router VM, the path to the internet) plus your host. Your own systems only; nothing you do not own appears on it.
- **Subnets:** every subnet labeled with its network address, prefix (CIDR), and usable host range. The arithmetic must match what you hand-derived in Lab 3.1; a diagram with a broadcast address that contradicts its prefix is a failed diagram.
- **Routing:** the router and its interfaces shown, with each interface's address; the default route and the inter-subnet routes indicated so a reader can trace how a packet gets from subnet A to subnet B and out to the internet. Mark where NAT happens.
- **DHCP scopes:** for any subnet served by DHCP, the scope (the range of addresses the server hands out) and the lease parameters a client receives (gateway, DNS servers), consistent with what you actually saw in your Lab 3.3 DHCP capture.
- **DNS resolvers:** which resolver each subnet's clients use, consistent with your Lab 3.3 DNS capture and your Lab 3.2 build.
- **Format:** any clear medium is acceptable: a diagramming tool, or a careful hand drawing photographed legibly. Clarity and accuracy are graded, not artistic polish. A legend defines every symbol you use.

## Specification: the annotated captures

- **Three captures**, one each for DHCP (the DORA exchange), DNS (a query and its response), and a TCP three-way handshake, saved as capture files and captured from your own lab traffic only (the Lab 3.3 scope rule is absolute and is restated here: own traffic on your own lab network).
- **Annotations:** for each capture, the full exchange identified in order, and one representative packet annotated field by field, with each significant field's name, value, meaning, the OSI layer it belongs to, and the RFC that defines it. These are the artifacts you produced in Lab 3.3; this deliverable is where you finalize and present them.
- **Your own words:** the annotations explain each field in your own words, not pasted from a tool's tooltip and not generated. The tutor verifies this by spot-check (below).

## Acceptance criteria

- The diagram is committed and shows subnets, routing (with NAT marked), DHCP scopes, and DNS resolvers, all internally consistent and arithmetically correct against Lab 3.1.
- The diagram's addressing matches the network you actually built in Lab 3.2 and the parameters you actually captured in Lab 3.3. A reader could use it to trace a packet from a subnet-A host to the internet and back.
- All three captures are present, scoped to their exchange, and captured from your own lab traffic.
- Each capture has a field-by-field annotation of one packet, with field, value, meaning, OSI layer, and defining RFC.
- A legend defines every symbol in the diagram.
- No real third-party traffic, no other people's data, appears in any capture; everything is traffic you generated yourself in your own lab.
- No em dashes, to match the house style of the course's own prose; use commas, colons, parentheses, or semicolons.

## Verification

The tutor will not produce this for you. It verifies in two ways. First, it picks one element of the diagram (a subnet's prefix, the NAT boundary, a DHCP scope) and asks you to justify it from memory, including the arithmetic where addressing is involved. Second, it picks one annotated field from one capture and asks you to explain it from memory: what it means, which layer it belongs to, and what would change if it held a different value. If you built the network and read the packets yourself, both are straightforward. If you copied a diagram or had a field explained for you, both expose it.

This is an AI-free month, so there is no AI Provenance section on the notebook entries and none here. The verification is simply that the work is yours.

## Why this is the Month 3 deliverable

A network diagram is the first thing a team hands a new engineer. It is also the first thing an incident responder draws when no diagram exists. Drawing an accurate network you built, and defending every subnet and route on it, rehearses real operational work. The annotated captures are the other half. Reading one exchange on the wire is the foundation that Month 4's packet analysis, Month 8's TLS handshake work, and every later investigation stand on. This deliverable turns the abstract model from the reading into a concrete artifact you own and can defend.

## How to know it is done

- The annotated home-lab network diagram is committed, with subnets, routing, DHCP scopes, DNS resolvers, and a legend.
- The three annotated captures are committed alongside it.
- Four lab notebook entries are committed (`lab-01-subnetting-drills.md`, `lab-02-virtual-network-build.md`, `lab-03-protocol-captures.md`, `lab-04-tryhackme-networking.md`).
- The subnetting method sheet is written and survives a cold read.
- `.tutor/lab-log.md` shows all four Month 3 labs logged.
- `.tutor/progress.md` updated to "Month 3 complete; ready for Month 4."

If any of the above is missing, the month is not done. The tutor will not advance you to Month 4 until all of it is present.
