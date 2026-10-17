# SOC Alert Prioritization

> Bootcamp lab: simulated scenario (TripleTen Cybersecurity, 2026)

## Context
Five alerts hit the queue at the same time: ransomware, an AiTM
phishing attempt, pass-the-hash toward a domain controller, DNS
tunneling, and an internal port scan. You can't contain everything
at once, so the real question was which one to stop first, and why.

## What I did
- Analyzed each of the five alerts: source, urgency, assets at risk,
  possible false positive, correlation with the others, and
  priority action.
- Ranked the pass-the-hash compromise of the domain controller
  (a backdoor Domain Admin account created within seconds) first,
  because latent risk with no ceiling outweighed damage already done.
- Chose containment over investigation or notification: disable the
  backdoor account, reset the krbtgt account twice, and isolate the
  source host while preserving its memory.
- Wrote down my assumptions and what I didn't know, such as how the
  entry point was compromised and how much credential data had
  been extracted.

## Tools & methods
Alert triage, risk prioritization, Active Directory incident
response concepts.

## Deliverables
- Report: /Proyecto Sprint 2_.pdf

## Instructor review
Approved. Praised for prioritizing by latent risk and separating
coincidence from evidence.

## What I learned
The lesson that stuck: “it already happened” is never a reason to wait if the attacker is still connected. 
A live channel means it’s still an active incident. 
I also learned to check every alert against confidentiality, integrity, and availability before ranking it, and to make sure the action I write in the table is exactly the decision I explain in the text.
