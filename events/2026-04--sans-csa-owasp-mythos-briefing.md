# Event: SANS, CSA, and OWASP Release Emergency Mythos-Ready Security Briefing

## Date
2026-04-13 (PDF live); 2026-04-14 (formal press release)

## Source
- [MYTHOS-BRIEFING] [GlobeNewswire press release](https://www.globenewswire.com/news-release/2026/04/14/3273499/0/en/SANS-Institute-Cloud-Security-Alliance-un-prompted-and-OWASP-GenAI-Security-Project-Release-Emergency-Strategy-Briefing-as-AI-Driven-Vulnerability-Discovery-Compresses-Exploit-Time.html)
- [MYTHOS-BRIEFING] [PDF — primary artifact](https://labs.cloudsecurityalliance.org/mythos-ciso/)

## What happened

SANS Institute, the Cloud Security Alliance, [un]prompted, and the OWASP GenAI Security Project jointly released *"The AI Vulnerability Storm: Building a Mythos-Ready Security Program"* — a free 30-page strategy briefing produced over a single weekend by more than 60 named contributors and reviewed by over 250 CISOs. The PDF was published as a live draft on April 13; the coordinated press release followed April 14. It is the first multi-organization practitioner document to respond directly to the capabilities demonstrated by [Project Glasswing](2026-04--project-glasswing.md) and to translate those capabilities into an actionable framework for CISOs and boards.

The contributors include Jen Easterly (former CISA Director), Chris Inglis (former National Cyber Director), Phil Venables (Google CISO), Bruce Schneier, Heather Adkins, Rob Joyce, and Sounil Yu, among others. The breadth of the author list signals this document is intended to carry policy weight, not just practitioner guidance.

The briefing explicitly positions Mythos as an acceleration of a documented multi-year trend rather than an isolated event:

> "The window between vulnerability discovery and weaponization has collapsed into hours."
> — Rob T. Lee, Chief AI Officer and Chief of Research, SANS Institute [MYTHOS-BRIEFING]

According to the Zero Day Clock cited in the briefing, mean time from vulnerability disclosure to confirmed exploitation has fallen to **less than one day in 2026**, down from 2.3 years in 2019. [MYTHOS-BRIEFING]

## Document contents

The briefing contains four primary artifacts:

| Artifact | Contents |
|----------|----------|
| **13-item risk register** | Mapped to OWASP LLM Top 10 2025, OWASP Agentic Top 10 2026, MITRE ATLAS, and NIST CSF 2.0 |
| **11 priority actions** | With explicit start dates; PA1 is "point AI agents at your own code this week"; PA11 is "stand up a permanent VulnOps function within 12 months" |
| **10 CISO diagnostic questions** | To triage current security program posture before building |
| **Board briefing section** | Talking points, 90-day plan structure, and CFO-facing framing |

The editorial frame throughout is intentional: each risk is framed as an acceleration of something that already existed, not a new problem Mythos created. The authors state this distinction changes how organizations should respond — the task is adjusting timelines, not starting from zero.

## Governance-critical rows

**Row 12 — Regulatory Exposure** is the most material for GRC practitioners:

> "The EU AI Act takes effect in August 2026, introducing automated audit, incident reporting, and cybersecurity requirements around AI. When AI can find vulnerabilities at accessible cost, the standard for what constitutes reasonable defensive effort shifts, creating direct governance and liability exposure for organizations that do not adapt." [MYTHOS-BRIEFING]

This is a practitioner-level articulation of the same doctrinal argument the repo documents in [The Reasonable Security Baseline Just Moved](../analysis/reasonable-security-baseline.md): under *FTC v. Wyndham*'s cost-benefit framework, the "reasonable security" standard is benchmarked against available technology. When AI-driven vulnerability discovery becomes a commodity, organizations that did not use it may face the same exposure as organizations that failed to implement available security controls before Wyndham. The briefing's Row 12 makes this argument explicitly, from practitioners, in a document reviewed by 250 CISOs.

**Row 13 — AI Hype and Confusion** adds a second governance risk: teams that dismiss Mythos as marketing, or exhaust their attention parsing commentary rather than making operational changes, will miss the actual changes they need to make. The briefing identifies noise itself as a risk category.

## Who's affected

Any organization that maintains software, operates security programs, or is subject to compliance frameworks with vulnerability management requirements. The briefing is specifically addressed to CISOs, boards, and vCISOs who need to explain the Mythos capability shift to executive audiences and translate it into defensible program changes. The EU AI Act framing (August 2026 effective date) makes this immediately relevant to any organization with EU regulatory exposure.

## Key links
- [PDF — primary artifact](https://labs.cloudsecurityalliance.org/mythos-ciso/) [MYTHOS-BRIEFING]
- [GlobeNewswire press release](https://www.globenewswire.com/news-release/2026/04/14/3273499/0/en/SANS-Institute-Cloud-Security-Alliance-un-prompted-and-OWASP-GenAI-Security-Project-Release-Emergency-Strategy-Briefing-as-AI-Driven-Vulnerability-Discovery-Compresses-Exploit-Time.html) [MYTHOS-BRIEFING]
- [SANS AI Cybersecurity Summit — April 20, 2026 (free)](https://www.sans.org/cyber-security-training-events/ai-summit-2026)
- [CSA Agentic AI Security Summit — April 29–30, 2026 (free)](https://cloudsecurityalliance.org)
- [Project Glasswing event](2026-04--project-glasswing.md) — the capability disclosure this briefing responds to
- [The Reasonable Security Baseline Just Moved](../analysis/reasonable-security-baseline.md) — the repo's analysis that Row 12 corroborates

---

*Added: 2026-04-14*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
