---
title: "Reading"
parent: "Month 3 - Networking Fundamentals"
grand_parent: Curriculum
nav_order: 90
---

# Month 3 Reading

Free and high-signal. Read the primary sources, the RFCs and the official tool documentation, before any blog or video. Networking is one of the best-documented fields in computing because it was built on public specifications; the habit of reading those specifications now is what lets you settle a layer-model argument or a protocol-behavior question without guessing later. This is an AI-free month; do not paste captures or addresses into an AI to have them explained. The reading list is your reference; the man pages and RFCs are the ground truth.

## Core (read these as you work the labs)

- _RFC_ RFC 1122, *Requirements for Internet Hosts: Communication Layers* - the authoritative four-layer TCP/IP model. Read this whenever a learning resource's layer assignment seems off; this is the document that settles it.
- _RFC_ RFC 791, *Internet Protocol* - the IPv4 header, field by field. The structure you will see in every Layer 3 packet you capture.
- _RFC_ RFC 950, *Internet Standard Subnetting Procedure* - the original definition of subnetting (Lab 3.1).
- _RFC_ RFC 4632, *Classless Inter-Domain Routing (CIDR)* - how prefix-based addressing replaced classes (Lab 3.1).
- _RFC_ RFC 9293, *Transmission Control Protocol (TCP)* - the current consolidated TCP specification: the handshake, flags, sequence numbers, and the orderly close (Labs 3.3).
- _RFC_ RFC 2131, *Dynamic Host Configuration Protocol* - the DORA lease lifecycle and the option fields you will read in your capture (Lab 3.3).
- _RFC_ RFC 1035, *Domain Names: Implementation and Specification* - the DNS message format and record types (Lab 3.3).
- _docs_ The Wireshark User's Guide, chapters on capturing live traffic and on display filters - the primary reference for Lab 3.3.

## Reference (consult as needed)

- _RFC_ RFC 1918, *Address Allocation for Private Internets* - the private ranges your Lab 3.2 subnets must use.
- _RFC_ RFC 826, *An Ethernet Address Resolution Protocol* - what ARP does on a local segment and why it is a spoofing target.
- _RFC_ RFC 792, *Internet Control Message Protocol* - what ping and traceroute actually send.
- _RFC_ RFC 2663, *IP Network Address Translator (NAT) Terminology and Considerations* - the vocabulary for what your Lab 3.2 router does when it NATs.
- _RFC_ RFC 3021, *Using 31-Bit Prefixes on IPv4 Point-to-Point Links* - the /31 special case that trips people in Lab 3.1.
- _man_ `man ip`, `man ip-route`, `man tcpdump`, `man pcap-filter`, `man dig` - on your own machine, for every tool you reach for.
- _docs_ Your hypervisor's networking documentation (UTM or VirtualBox) - the authoritative reference for its network modes (Lab 3.2).

## Structured external curriculum

- _course_ TryHackMe "Network Fundamentals" path - the guided, hands-on consolidation for Lab 3.4. Use its room material to learn technique; do not use external walkthroughs to skip the tasks.

## Optional (overview only; do not rely on these in place of the RFCs)

- _video_ A reputable overview of the OSI model and the TCP/IP stack, for a first orientation before the RFCs. Treat any video as a map, not the territory; popular videos frequently oversimplify the layer model. When a video and an RFC disagree, the RFC wins.

## A note on sources

When a lab asks you to cite a source, cite an RFC, a man page, or official tool documentation, not a blog post and not a video. Two reasons. First, the primary sources are precise where secondary sources are approximate, and networking punishes approximation. Second, building the habit of reaching for the specification now is exactly what makes you able to catch an AI, in a later month, confidently citing a protocol behavior that no RFC actually describes.
