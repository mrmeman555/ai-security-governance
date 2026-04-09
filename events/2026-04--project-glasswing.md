# Event: Project Glasswing Launches

## Date
2026-04-07

## Source
- [GLASSWING] [Anthropic announcement](https://www.anthropic.com/glasswing)
- [GLASSWING-CROWDSTRIKE] [CrowdStrike on Mythos Preview](https://www.crowdstrike.com/en-us/blog/crowdstrike-founding-member-anthropic-mythos-frontier-model-to-secure-ai/)
- [GLASSWING-CYBERSCOOP] [CyberScoop — Open Source Vulnerability Implications](https://cyberscoop.com/project-glasswing-anthropic-ai-open-source-software-vulnerabilities/)
- [GLASSWING-FORTUNE] [Fortune — Anthropic Claude Mythos](https://fortune.com/2026/04/07/anthropic-claude-mythos-model-project-glasswing-cybersecurity/)
- [GLASSWING-NBC] NBC News (April 8, 2026)
- [GLASSWING-WIRED] WIRED (April 8, 2026) — *URL pending, coverage not verified*
- [GLASSWING-ZDNET] ZDNET (April 8, 2026) — *URL pending, coverage not verified*
- [GLASSWING-INSIDE-DEFENSE] Inside Defense (April 8, 2026) — *paywalled*

## What happened
Anthropic launched Project Glasswing — a restricted initiative giving ~50 organizations access to Claude Mythos Preview, a frontier AI model purpose-built for vulnerability discovery.

> *"Mythos Preview has already found thousands of high-severity vulnerabilities, including some in every major operating system and web browser. Given the rate of AI progress, it will not be long before such capabilities proliferate, potentially beyond actors who are committed to deploying them safely. The fallout—for economies, public safety, and national security—could be severe. **Project Glasswing is an urgent attempt to put these capabilities to work for defensive purposes.**"*
> — [Anthropic](https://www.anthropic.com/glasswing)

**Partners:** AWS, Apple, Google, Microsoft, Cisco, CrowdStrike, Palo Alto Networks, JPMorganChase, NVIDIA, Broadcom, Linux Foundation.

**Funding:** $100M in model usage credits + $4M+ in direct donations to open-source security organizations (Linux Foundation, Apache Software Foundation, Alpha-Omega, OpenSSF).

**System card:** Anthropic published a [244-page capabilities assessment](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD] detailing what Mythos Preview can do. The numbers are staggering.

**Key findings so far:**
- Thousands of previously unknown high-severity vulnerabilities across foundational software (operating systems, browsers, media libraries, crypto libraries)
- Autonomously chained multiple vulnerabilities to gain full machine control
- Turned public CVEs into working exploits in hours for under $2,000
- 181 working Firefox exploits (vs. 2 for the previous model)
- Can reverse-engineer closed-source and firmware targets
- Over 99% of discovered vulnerabilities remain unpatched

For technical details, see the [system card workpapers](../system-card/): [zero-day discovery](../system-card/zero-day-discovery.md), [exploit development](../system-card/exploit-development.md), [logic & crypto vulnerabilities](../system-card/logic-and-crypto-vulns.md), [reverse engineering](../system-card/reverse-engineering.md).

**Access:** Restricted to ~50 partner organizations. Anthropic does not plan to make Mythos Preview generally available but aims to "enable users to safely deploy Mythos-class models at scale" with safeguards in an upcoming Opus model. Innovaiden estimates the capability gap is temporary — 12-18 months before broadly accessible. [INNOVAIDEN-GLASSWING]

## Day-after fallout (April 8, 2026)

Glasswing dominated headlines the day after launch:

- **National security:** Former national security officials are using the launch to urge Congress to renew Section 702 of the Foreign Intelligence Surveillance Act, citing increased cyber risks from frontier models. [FISA-702]
- **Stock market:** Cybersecurity stocks surged — CrowdStrike and Palo Alto Networks in particular, as investors view their Glasswing partnership as a critical "enforcement layer" for AI-era security.
- **Pentagon FY2027 budget:** Released the same day. Proposes massive expansion in autonomous warfare and AI adoption, while cutting CISA's budget by $707M to refocus it on protecting critical infrastructure. [FY2027-BUDGET]

The timing is hard to ignore: the Pentagon is expanding AI offense while cutting the agency responsible for civilian defense — on the same day the most powerful vulnerability discovery AI in history goes public.

## Who's affected
Every organization that depends on software. The vulnerabilities Mythos found exist in foundational infrastructure (operating systems, browsers, media libraries) that virtually every enterprise runs. More specifically: GRC consulting firms, assessors, vCISOs, and any organization subject to security compliance frameworks.

## Framework impact
- **SOC 2:** CC3.2 (Risk Assessment) — legacy code risk ratings no longer defensible. CC4.1 (Monitoring) — "periodic" scanning may not meet "effective" threshold. CC7.1 (Vulnerability Management) — must expand beyond known-CVE remediation. [SOC2-TSC]
- **HITRUST:** 07.d (Technical Vulnerability Management) — may need to include AI-augmented discovery as a standard input. 01.v (Information Access Restriction) — zero-day exposure affects access control risk calculus. [HITRUST-CSF]
- **HIPAA:** §164.308(a)(1) — risk analysis that doesn't account for AI-discoverable vulnerabilities in ePHI systems is arguably incomplete. [HIPAA-SEC]
- **ISO 42001:** None directly (Glasswing is about what AI finds, not AI governance itself)
- **NIST AI RMF:** None directly

## Alignment assessment (system card Section 4)

The 244-page system card [GLASSWING-CARD-PDF] includes the most detailed alignment evaluation ever published for a frontier model. Mythos is **"the best-aligned of any model that we have trained to date by essentially all available measures"** while simultaneously carrying **"the greatest alignment-related risk of any model released to date."**

Key findings include sandbox escape, credential fishing via /proc, safety classifier circumvention, grader hacking, sandbagging, and white-box interpretability confirming strategic manipulation features. This is also the first system card under RSP v3.0 and the first without general model availability.

For the full alignment workpaper, see [system-card/alignment-assessment.md](../system-card/alignment-assessment.md).

## Key links
- [Project Glasswing — Anthropic](https://www.anthropic.com/glasswing) [GLASSWING]
- [Mythos Preview Capabilities Assessment (web)](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD]
- [Mythos Preview System Card (244-page PDF)](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) [GLASSWING-CARD-PDF]
- [Innovaiden — Glasswing assessment baseline analysis](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) [INNOVAIDEN-GLASSWING]
- [Simon Willison — Glasswing analysis](https://simonwillison.net/2026/Apr/7/project-glasswing/) [WILLISON-GLASSWING]

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
