# AI Ethics for Cybersecurity Work

This document is the operational ethics scaffolding for AI use in the Vigil course and in the cybersecurity career that follows. It is not a values statement. It is a set of decision trees for specific situations that will arise.

Read it before Month 5 (when AI assistance first unlocks). Re-read it before Month 10 (offensive operations) and Month 11 (cloud and AI system security). The rules apply during the course and they apply in your future work.

## The framing

You are the senior reviewing a junior teammate's work. The AI is the junior. The AI is fast and confident; it is sometimes right in ways you could not have produced as quickly; it is also sometimes wrong in ways that are dangerously plausible. Your job is to integrate its speed without inheriting its errors.

You sign the report. You ship the code. You answer the question in the interview. The AI does none of these things. Your name is on the work, regardless of who or what helped produce it.

## The five rules

### 1. The AI-free zone is for your benefit, not for the tutor's

For Months 0 to 4, do not use AI assistance on the fundamentals labs. The tutor will refuse to help you with the AI-free zone work, but the discipline is yours to enforce when the tutor cannot see what you are doing.

The reason: you cannot evaluate AI output you do not understand. If you build the fundamentals with AI doing the work, you will not be able to tell when AI is wrong on the fundamentals later. The cost of accepting wrong AI output during this period is undetectable for months and then severe when an interview question reveals the gap.

If you ignore this rule, you will get through the course. You will not get through an interview.

### 2. AI Provenance is real documentation, not theater

From Month 5, every lab notebook entry must include an AI Provenance section. The format is given in `tutor-reference.md`. The discipline is:

- Document which AI tool you used (model, interface), as if filing a citation.
- Document what you asked, in enough detail that someone reading the entry six months later could reproduce your conversation.
- Document what was generated.
- Document what you verified, by what method. "I checked it" is not verification. "I ran the regex against five log lines I crafted by hand and confirmed it matched the three I intended and skipped the two I intended" is verification.
- Document what you discarded as wrong.

This documentation is for the tutor, but more importantly it is for you. In a year, when you are working a real incident at 2 AM and the AI gives you a detection rule, the discipline you built here is what tells you whether to trust it or test it.

### 3. The verification ritual is the safety net

When the tutor selects an element from your AI-augmented work and asks you to explain it without your AI session open, the right response is to actually do that. Not to consult the AI again. Not to vamp confidently.

If you cannot explain it, that is not a failure of the ritual; it is the ritual working. You did not actually understand the artifact you submitted. The lab is not done. Return to the source material, build the understanding, and resubmit.

The professional version of this ritual is the interview. When an interviewer asks "why does this WHERE clause behave this way," the candidates who can answer cleanly are the candidates who built the verification habit during their training. The ones who cannot are the ones who skipped this rule in their course.

### 4. Do not feed sensitive data to public AI services

Public AI services (the chat interfaces of major LLM vendors, AI features in popular IDEs, browser-based assistants) log inputs in ways that range from temporary to permanent. The vendors' policies vary, change over time, and are sometimes violated. Operationally, you should assume that anything you paste into a public AI service has been logged, may be used for training, and may eventually surface in unexpected places.

Do not paste any of the following into a public AI service:

- Client data (during your future career).
- Employer data (during your future career).
- Lab data that includes credentials, tokens, or keys, even from a deliberately-vulnerable VM.
- Production PCAPs that capture real traffic on real networks (including your home network).
- Code containing hardcoded credentials.
- Any data subject to a regulatory regime you operate under (PHI, PCI, GDPR-scoped personal data).

If you need AI help with sensitive content, use a self-hosted model (Ollama for offline LLM work, installed during Month 0 setup; see getting-started.md) or an enterprise tier of a vendor with a no-training contractual guarantee.

A capture is not only data you might paste; it is data you collected. When you capture traffic on a shared home network (Month 4), you can incidentally record the device traffic of housemates or family who never agreed to it. Recording other people's communications without consent is a separate legal question (wiretap and consent law) from the access rules in `SAFETY.md`, and it varies by jurisdiction. Capture only traffic to and from devices you control, or get the explicit consent of everyone on the network, and never paste a capture that may contain a third party's traffic into a public AI service.

### 5. Do not prompt-inject around safety filters

You will see, in Month 11 and in your career, that AI models can be jailbroken. The course teaches you about this so you can defend systems against it.

What the course does not authorize, and what you should not do:

- Use jailbreaks to generate offensive content (malware, exploits, phishing templates) for course labs. The labs that need such content provide it explicitly.
- Use jailbreaks to bypass restrictions on a model you are paying for. The terms of service govern your use; bypassing them is breach of contract at minimum and may be more in some jurisdictions.
- Train yourself in jailbreak technique against a model you do not have authorization to test. (Yes, this is rare. Yes, the rules still apply.)

Studying jailbreak technique against a model you have authorization to test, as part of Month 11's AI system security labs, is in scope. The line is "authorization to test." Same line as everywhere else in this course.

## The decision tree for ambiguous situations

When you face an AI-related decision where the right action is not obvious, walk this tree:

**Q1: If this AI assistance becomes public, would you defend it?** If no, do not use it.

**Q2: Could the AI's output be wrong in a way you would not catch?** If yes, you do not yet understand the underlying concept well enough to use AI here. Build the understanding first.

**Q3: Could the AI's output be misused if the AI ignored its safety guardrails?** If yes, do not use AI for this task even if the model would technically comply.

**Q4: Are you about to paste content the vendor's logs should not see?** If yes, switch to a self-hosted or enterprise-tier model, or do the work by hand.

**Q5: Are you using AI to compensate for the discipline of the course rather than to accelerate work you could do yourself?** If yes, stop. The course is the discipline.

When none of the answers above is yes, AI assistance is appropriate. Use it well, document it honestly, and verify it carefully.

## Disclosure in deliverables

When you produce a deliverable that will be seen by a potential employer or a client (your Month 12 capstone reports; your public blog posts; any work-product portfolio piece), disclose AI assistance:

- A capstone pentest report includes an "AI Provenance" appendix with the same format used in your notebook entries throughout the course.
- A blog post mentions AI use in a footer ("AI used for [drafting, summarization, regex generation]; verification by author").
- A GitHub repo's README includes a line in its acknowledgments if AI played a non-trivial role.

The disclosure is not an admission of weakness. It is a demonstration of professional discipline. Employers who reject candidates for disclosing AI use are signalling that they will hire candidates who are dishonest about it.

## The "this would be easier if I just" trap

Most violations of this document do not look like violations from the inside. They look like efficiency. "This would be easier if I just asked AI to write the script and read it later." "This would be easier if I just pasted the log in and got the summary."

Catch yourself when the phrase "this would be easier if I just" appears in your thinking. The easier path is rarely the path that builds the skill. The friction the course imposes is the curriculum, not an obstacle to it.

## A final word

The cybersecurity field has spent two years adapting to AI's arrival. The candidates who have done well are the ones who built AI literacy on top of fundamental skill. The candidates who have done badly are the ones who skipped the fundamental skill on the assumption that AI would compensate for the gap. The interviewing process detects this gap quickly. The course is designed to put you in the first group.

The rules in this document are the operational version of that strategy. They are imposed gently in Months 0 to 4 (AI is just off-limits), more substantively in Months 5 onward (AI is permitted under discipline), and they continue to govern your work after the course ends. They are not a phase. They are how this work is done.
