# What Project Glasswing Means for Your Assessment Practice

> **For:** Justin Graham, Steadfast Partners
> **From:** Aaron Reveley
> **Date:** April 8, 2026
> **Format:** Practitioner brief — not a news summary. Focused on what changes for SOC 2, HITRUST, HIPAA, and vCISO advisory.

---

## The Event

On April 7, 2026, Anthropic launched Project Glasswing — a restricted initiative giving ~50 organizations access to Claude Mythos Preview, a frontier AI model that has already found thousands of high-severity zero-day vulnerabilities across every major operating system and web browser.

**Partners:** AWS, Apple, Google, Microsoft, Cisco, CrowdStrike, Palo Alto Networks, JPMorganChase, NVIDIA, Broadcom, Linux Foundation.

**Funding:** $100M in model usage credits + $4M in direct donations to open-source security organizations (Alpha-Omega, OpenSSF, Apache Software Foundation).

**Key findings so far:**
- 27-year-old vulnerability in OpenBSD (crash any server with two packets)
- 16-year-old vulnerability in FFmpeg that automated testing tools executed 5 million times without catching
- Thousands of previously unknown high-severity flaws across foundational software

**Access:** Restricted. Not publicly available. Anthropic estimates Mythos-class models will be broadly deployable in 12-18 months once safeguards are built.

---

## Why This Matters for GRC Consulting

### 1. The "Reasonable Security" Baseline Just Moved

Every framework you work with — SOC 2, HIPAA, HITRUST, ISO 27001, CMMC — requires organizations to implement "reasonable" or "proportionate" security measures. That standard is benchmarked against prevailing industry practices.

**The problem:** When an AI model can find vulnerabilities that survived 27 years of expert human review and 5 million automated test executions, the definition of what constitutes adequate vulnerability management has shifted. Assessments completed before April 2026 are benchmarked against a demonstrably lower standard.

**What this means in practice:**
- Vulnerability management controls scoped against CVE databases alone now have a known blind spot — zero-days that AI can find but scanners cannot
- "We run regular vulnerability scans" is no longer sufficient as a control narrative if the scans only check known CVEs
- The gap between "we scan for known vulnerabilities" and "we discover unknown vulnerabilities" is now a documentable risk

**The question clients will start asking:** "Should our vulnerability management program account for AI-augmented discovery?" The answer is going to be yes within 18 months. Firms that help clients prepare now are ahead.

### 2. HITRUST Assessment Scope

HITRUST rolls HIPAA + SOC 2 + NIST into one unified assessment. If the vulnerability management controls underlying those frameworks need to account for AI-augmented discovery capability, the HITRUST assessment scope expands:

- **Control 07.d (Technical Vulnerability Management)** — currently satisfied by regular scanning and patching. Post-Glasswing, assessors may need to ask whether the organization has evaluated AI-augmented discovery tools or documented a risk acceptance for not using them.
- **Control 01.v (Information Access Restriction)** — zero-day exposure in foundational software (OS, browsers, media libraries) affects the risk calculus for access controls built on top of that software.

This isn't a requirement today. But HITRUST updates its control framework regularly, and the next revision will almost certainly reference AI-augmented vulnerability management. Assessors who understand this shift before the framework catches up can advise clients proactively.

### 3. HIPAA Risk Analysis

HIPAA's Security Rule (§164.308(a)(1)) requires covered entities to "conduct an accurate and thorough assessment of the potential risks and vulnerabilities to the confidentiality, integrity, and availability of electronic protected health information."

**The shift:** If AI can find zero-day vulnerabilities in the software that stores and transmits ePHI — and those vulnerabilities have existed for decades undetected — then a HIPAA risk analysis that doesn't account for this class of risk is arguably incomplete.

**Healthcare-specific concern:** Healthcare organizations are the #1 target for ransomware. The software they depend on (OS kernels, browsers, media processing libraries like FFmpeg) is exactly where Mythos found its most critical vulnerabilities. A dental clinic running unpatched FFmpeg for imaging software now has a named, documented risk that didn't exist in any database last week.

**For Steadfast's healthcare clients:** This is a conversation to have during the next risk assessment cycle. Not as a scare tactic — as a genuine update to the threat landscape that their risk analysis should reflect.

### 4. SOC 2 Trust Services Criteria

**CC3.2 (Risk Assessment)** — Must now account for accelerated exploitation windows. If an AI can find a 27-year-old bug in hours, traditional "low" risk ratings for legacy code are no longer defensible. Risk assessments should consider: "What is our exposure to zero-day vulnerabilities in foundational software, and what is our detection capability for vulnerabilities that don't appear in known databases?"

**CC4.1 (Monitoring)** — Language needs to shift from "periodic" to near-continuous automated scanning. Manual quarterly pentests may no longer meet the "effective" threshold given the scale of AI-driven discovery.

**CC7.1 (Vulnerability Management)** — Language must expand from "remediation of known vulnerabilities" to include preemptive discovery using AI-native tools that operate at machine speed. The residual risk statement should acknowledge whether detection capabilities extend beyond known-CVE scanning. This becomes a finding if the risk isn't acknowledged.

**Practical impact for SOC 2 engagements:** When writing control narratives for vulnerability management, the DE/OE assessment should note the scope of the organization's detection capabilities. Simply having a vulnerability scanner is no longer "reasonable" if the scanner only checks known CVEs and AI tools can find what it can't.

### 5. Legal Precedent — FTC "Reasonable Security"

The FTC has historically benchmarked "reasonableness" against available technology. In *FTC v. Wyndham Worldwide*, the court upheld the FTC's authority to enforce data security standards based on what was commercially available and what the company should have known.

**The Glasswing implication:** Project Glasswing establishes that AI-driven vulnerability scanning is now commercially "available" to defenders — at least to the ~50 partner organizations. As this capability broadens, its non-use becomes a potential indicator of negligence in future enforcement. The precedent is clear: "we didn't know" stops being a defense when the capability is publicly documented and accessible.

### 6. Cyber Liability Insurance

New policy language is emerging requiring "AI-Native Defense" or evidence of AI-augmented code scanning as a condition for coverage of zero-day exploits. The logic: "human-only" review is now demonstrably insufficient for thousands of vulnerabilities that AI can find. Carriers are beginning to price this into their risk models.

### 7. PCAOB / AICPA on AI in Audit

Current PCAOB and AICPA guidance emphasizes auditor independence and warns against auditors using AI tools that "audit their own work" or implementing the very controls they test. This creates a tension: assessors need to understand AI-augmented tools to evaluate client controls, but can't use the same tools to perform their own assessments without independence concerns.

### 5. vCISO Advisory — The Client Conversation

For Steadfast's vCISO engagements, this is a proactive advisory opportunity:

**The 90-day conversation:**
- "Here's what happened with Glasswing. Here's what it means for your vulnerability management program."
- "Your current scans check known CVEs. This new class of AI tool finds things that aren't in any database. You don't need to adopt it today, but you need to document the risk and plan for it."
- "Within 18 months, AI-augmented vulnerability discovery will be commercially available. Let's build your adoption roadmap now so you're not scrambling."

**The service line opportunity:**
- AI-augmented assessment methodology development
- Policy updates to account for AI-assisted vulnerability management
- Client readiness assessments for when Mythos-class tools become available
- Gap analysis: current vulnerability management vs. AI-augmented baseline

---

## The Supply Chain Angle

Worth noting: the event that made Glasswing publicly visible happened because of a supply chain failure at Anthropic itself. On March 31, a misconfigured npm package exposed the full source architecture of Claude Code — an AI agent harness used by hundreds of thousands of developers. A missing line in a config file. That's the kind of operational security gap that SOC 2 and ISO 27001 controls are supposed to prevent.

The irony is instructive: the company building the most powerful vulnerability detection AI in history was itself vulnerable to a packaging misconfiguration. That's the story you tell clients when they ask "does this really matter for us?"

---

## Timeline

| When | What's happening | Source |
|------|-----------------|--------|
| Now (April 2026) | Glasswing restricted to ~50 partner orgs. Vulnerability disclosures beginning. | [Anthropic](https://www.anthropic.com/glasswing) |
| Already underway | HITRUST launched an [AI Security Assessment](https://hitrustalliance.net/assessments-and-certifications/aisecurityassessment) (late 2024) — 51 controls mapped to ISO 23894 and NIST AI RMF. Schellman published a [mapping from HITRUST AI to ISO 42001](https://www.schellman.com/blog/ai-services/hitrust-ai-security-assessment-path-to-iso-42001). The frameworks are already moving. | HITRUST, Schellman |
| 12-18 months | AI-powered vulnerability discovery at Glasswing's level becomes broadly accessible. "The capability gap between Project Glasswing participants and the rest of the market is temporary, likely 12 to 18 months." Anthropic plans to ship safeguards on an upcoming Opus model first, then enable Mythos-class deployment at scale. | [Innovaiden](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline), [Axios](https://www.axios.com/2026/04/07/anthropic-mythos-preview-cybersecurity-risks) |
| By 2028 | Gartner predicts AI will drive 50% of cybersecurity incident response. Separately, Gartner forecasts 40% of enterprise apps will feature task-specific AI agents by 2026. As AI-augmented discovery becomes commercially available and framework bodies continue adding AI-specific controls, "do you use AI-augmented vulnerability scanning?" becomes a natural assessment question. | [Gartner](https://www.gartner.com/en/newsroom/press-releases/2026-03-17-gartner-predicts-ai-applications-will-drive-50-percent-of-cybersecurity-incident-response-efforts-by-2028), [Bessemer](https://www.bvp.com/atlas/securing-ai-agents-the-defining-cybersecurity-challenge-of-2026) |

---

## Sources

- [Project Glasswing — Anthropic](https://www.anthropic.com/glasswing)
- [Project Glasswing and the New Baseline for Cybersecurity Assessment — Innovaiden](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline)
- [CrowdStrike on Mythos Preview](https://www.crowdstrike.com/en-us/blog/crowdstrike-founding-member-anthropic-mythos-frontier-model-to-secure-ai/)
- [CyberScoop — Open Source Vulnerability Implications](https://cyberscoop.com/project-glasswing-anthropic-ai-open-source-software-vulnerabilities/)
- [Fortune — Anthropic Claude Mythos](https://fortune.com/2026/04/07/anthropic-claude-mythos-model-project-glasswing-cybersecurity/)
- [HITRUST AI Security Assessment](https://hitrustalliance.net/assessments-and-certifications/aisecurityassessment)
- [Schellman — HITRUST AI to ISO 42001 mapping](https://www.schellman.com/blog/ai-services/hitrust-ai-security-assessment-path-to-iso-42001)
- [Simon Willison — Glasswing analysis](https://simonwillison.net/2026/Apr/7/project-glasswing/)

---


