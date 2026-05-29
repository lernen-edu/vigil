# Safety, Legality, and Ethics

This document is the legal and ethical scaffolding for the Vigil course. Read it before Month 0 and re-read it before Month 10 (offensive operations).

The course teaches techniques that are legal in some contexts and criminal in others. The line between the two is sometimes one click. This document, plus `AI-ETHICS.md`, plus the tutor's ethical guardrails, are how you stay on the legal side of that line.

## The fundamental rule

You may only test, scan, exploit, or otherwise interact with systems you demonstrably own or have explicit written authorization to test.

There are no exceptions. Not "I'm just looking." Not "the company has a bug bounty." Not "my friend said it was OK." Not "I have an account on the service." Not "the system is broken anyway." Not "the lab said to use a real-world target."

If you cannot point to specific written authorization, you do not have it.

## What counts as a legal target for course work

The following are legal targets for the labs in this course:

- Your own machines (the Mac you are reading this on; any home-lab VMs running on it).
- Deliberately vulnerable virtual machines you have downloaded and are running on your own hardware (VulnHub, OWASP Juice Shop, DVWA, HackTheBox VPN-hosted boxes, TryHackMe rooms, picoCTF challenges).
- AWS resources you provision under your own account and explicitly intend to test (Month 11).
- Free, public-purpose security training platforms with clear terms of use that authorize the activity (CryptoHack, PortSwigger Web Security Academy, OverTheWire).

The following are not legal targets, in any month, under any framing:

- Your employer's infrastructure.
- Your school's infrastructure.
- A friend's machine, "with permission" given verbally.
- A public service or website you happen to use ("just to see if it has SQLi").
- Any system at a coffee shop, hotel, airport, or shared network.
- Any system you do not own and do not have explicit written authorization to test, regardless of whether it appears to be "fair game."

The tutor will refuse to assist with any work that touches a non-legal target. If you push, it will continue to refuse. This is not the tutor being precious. It is the tutor protecting you from a federal criminal charge.

## The Computer Fraud and Abuse Act (CFAA)

In the United States, the CFAA (18 U.S.C. § 1030) criminalizes "unauthorized access" to computer systems. The statute is broad and has been interpreted broadly by prosecutors. Notable consequences:

- Accessing a system without authorization, even if no data is taken, can be a misdemeanor or felony depending on intent and damage.
- Exceeding authorized access (you had permission to do A, you did B instead) is also chargeable under the statute.
- Penalties range from fines to prison time, scaled to the value of the system, the intent, and prior offenses.
- The CFAA has been used to prosecute security researchers who believed they were acting in good faith. The legal cost of a defense, even when ultimately successful, is significant.

The Supreme Court narrowed the "exceeds authorized access" provision in *Van Buren v. United States* (2021), but the underlying "unauthorized access" provision remains broad. The Department of Justice updated its CFAA charging policy in 2022 to deprioritize good-faith security research, but the underlying law has not changed.

If you are outside the United States, your country has its own computer-crime statutes, and some reach further than the CFAA in a way this course touches directly. The European Union, United Kingdom, Canada, and Australia all have analogous unauthorized-access laws. They differ in detail; they do not differ in concept. One difference does matter for what you will actually do here:

**Dual-use tool laws.** Some jurisdictions criminalize the possession or distribution of "hacking tools," not only their unauthorized use. Germany's Strafgesetzbuch section 202c (the so-called "hacker paragraph") and the United Kingdom's Computer Misuse Act section 3A both reach the making, supplying, or obtaining of tools designed for unauthorized access. This course has you install offensive tooling (nmap, Metasploit, the fuzzer you write in Month 5, the whole Kali kit) and publish write-ups that describe offensive technique. In the United States that is ordinary security work. Under a dual-use-tool statute, the install and the publication can themselves be the regulated acts, independent of whether you ever touch a system you do not own. If you operate in such a jurisdiction, the question is not only "did I test an authorized target" but also "am I permitted to possess and share these tools and write-ups at all." Get local advice before you publish offensive content, and look up your own jurisdiction rather than assuming the US framing in this document is the whole picture where you live.

This document is not legal advice. If you find yourself in a situation that may have legal exposure, retain an attorney with security-practice experience. The Electronic Frontier Foundation (eff.org) maintains a list of security-aware legal resources.

## What happens if you find a vulnerability

You will, during this course, find vulnerabilities in real systems. Not because you went looking outside the lab scope, but because you will sometimes notice things in passing. Or because you will work on a CTF that turns out to be modeled on a real product. Or because you will set up tooling that incidentally scans your home network.

The decision tree:

**If the vulnerability is in your own system.** Patch it. Note it in your notebook. Move on. No further action needed.

**If the vulnerability is in a lab environment (VulnHub VM, HTB box, training platform).** The platform expects this. Submit it through the platform's normal mechanism (CTF flag, lab completion, writeup post-retirement). No external disclosure.

**If the vulnerability is in a vendor product you happen to be running (e.g., a security flaw in your router, your password manager, your operating system).** Practice responsible disclosure: contact the vendor's security team (usually `security@<vendor>.com` or a `.well-known/security.txt` file on their website), provide a clear technical writeup, give them a reasonable disclosure window (typically 90 days), and do not publicly post the details before that window expires. Do not exploit the vulnerability beyond what is needed to confirm its presence. Document the disclosure timeline.

**If the vulnerability is in a service you use (a website, an app, a SaaS product).** Stop immediately. Take no further action against the system. If you wish to report the vulnerability, look for a vulnerability disclosure program or bug bounty on the vendor's site. If they do not have one, contact `security@<vendor>` once with a clear writeup, and do not engage further. Do not test the vulnerability again to confirm.

**If the vulnerability is at your employer.** Stop. Report to your security team or manager. Do not exploit it, do not document it publicly, do not discuss it outside the chain of command at work. Your employment agreement and your employer's policies govern your actions; this course does not override them.

**If, during an authorized engagement, you accidentally touch something outside the agreed scope (an out-of-scope host, a neighboring system, another tenant).** Stop interacting with it immediately. Do not explore it to see how far in you got. Write down exactly what you touched, when, and how you noticed, in your engagement notes. Report it to the engagement's point of contact; in a lab, note it in your lab notebook and treat the box's stated scope as the contract. Out-of-scope contact handled this way (stop, document, disclose) is a normal engagement event. Out-of-scope contact you hide, or keep exploring, is how authorized work turns into unauthorized access. Month 10 drills this exact reflex, because it is the boundary you are most likely to cross by accident rather than intent.

When in doubt, do less rather than more. Inaction has rarely been criminal; over-eager testing has often been.

## AI-related ethical considerations

See `AI-ETHICS.md` for the AI-specific ethical scaffolding. Headline rules:

- Do not prompt-inject around AI safety filters to generate offensive content, even for "lab purposes."
- Do not paste client data, employer data, or any other confidential material into public AI services.
- Disclose AI assistance in any deliverable that will be shown to an employer or client.
- Treat AI output as the work of a fast, error-prone junior teammate. You are the senior. You sign the report.

## The capstone special case

The Month 12 capstone includes a full pentest report. The target must be a legal target per the rules above. The capstone's `deliverable.md` requires you to document in writing the authorization basis for the target before any work begins. The tutor will verify this before allowing work on the capstone.

For learners who do not yet have a job with explicit authorization to perform pentests, the recommended capstone targets are:

- A retired HackTheBox box (these are explicitly authorized for write-ups once retired).
- A VulnHub VM you have downloaded.
- A deliberately-vulnerable environment you have built yourself (Vulhub, DVWA, OWASP Juice Shop with custom challenges).

Bug bounties are not recommended as capstone targets. The scoping is too narrow, the legal review is too dependent on the specific program's terms, and the risk of accidentally testing out-of-scope is high.

## Hardware and physical safety

The course is software-only. You will not be asked to physically tamper with hardware, attempt physical entry to facilities, or perform any kind of physical pentest. If a lab appears to suggest you do so, that is a bug; report it as an issue on the repo.

Wireless attacks (Wi-Fi cracking, Bluetooth, NFC) are not covered in the course's lab content for legal reasons; observing your own neighbor's Wi-Fi is illegal in most jurisdictions regardless of intent. If your career trajectory takes you toward wireless work, pursue it after the course in a lab environment you control end-to-end.

## Reporting concerns

If you encounter content in the course that you believe pushes against these guardrails, or if you find yourself in a situation where the course's instructions seem to invite a CFAA violation, report it as a GitHub issue with the tag `safety`. The course author treats safety issues as the highest priority and addresses them before any other course updates.

## A final word

Cybersecurity is one of the few fields where the techniques you learn on a Tuesday afternoon can land you in federal court on a Friday. The discipline of staying on the legal side of the line is part of the skill, not an annoyance separate from it. Every working cybersecurity professional does this navigation every day. The course teaches it from Month 0 because it is foundational.

If a job ever asks you to do work that would violate these rules, refuse and document. If you are unsure whether something is permitted, ask in writing before doing it, and keep the response. Your career, your finances, and your liberty depend on disciplined adherence to authorized scope.
