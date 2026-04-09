# The Reasonable Security Baseline Just Moved

## The Shift

Every compliance framework — SOC 2, HIPAA, HITRUST, ISO 27001, CMMC — requires organizations to implement "reasonable" or "proportionate" security measures. That standard is benchmarked against prevailing industry practices.

[Project Glasswing](../events/2026-04--project-glasswing.md) changed the benchmark. When an AI model can find vulnerabilities that survived 27 years of expert human review and 5 million automated test executions, the definition of what constitutes adequate vulnerability management has shifted. Assessments completed before April 2026 are benchmarked against a demonstrably lower standard.

## What This Means in Practice

- Vulnerability management controls scoped against CVE databases alone now have a known blind spot — zero-days that AI can find but scanners cannot
- "We run regular vulnerability scans" is no longer sufficient as a control narrative if the scans only check known CVEs
- The gap between "we scan for known vulnerabilities" and "we discover unknown vulnerabilities" is now a documentable risk

**The question that's coming:** "Should our vulnerability management program account for AI-augmented discovery?" Within 18 months, the answer is probably yes.

## Legal Precedent — FTC "Reasonable Security"

The FTC has historically benchmarked "reasonableness" against available technology. In *FTC v. Wyndham Worldwide*, the court upheld the FTC's authority to enforce data security standards based on what was commercially available and what the company should have known.

**The Glasswing implication:** Project Glasswing establishes that AI-driven vulnerability scanning is now commercially "available" to defenders — at least to the ~50 partner organizations. As this capability broadens, its non-use becomes a potential indicator of negligence in future enforcement. The precedent is clear: "we didn't know" stops being a defense when the capability is publicly documented and accessible.

## Cyber Liability Insurance

New policy language is emerging requiring "AI-Native Defense" or evidence of AI-augmented code scanning as a condition for coverage of zero-day exploits. The logic: "human-only" review is now demonstrably insufficient for thousands of vulnerabilities that AI can find. Carriers are beginning to price this into their risk models.

## PCAOB / AICPA on AI in Audit

Current PCAOB and AICPA guidance emphasizes auditor independence and warns against auditors using AI tools that "audit their own work" or implementing the very controls they test. This creates a tension: assessors need to understand AI-augmented tools to evaluate client controls, but can't use the same tools to perform their own assessments without independence concerns.

## The Supply Chain Irony

Worth noting: the event that made Glasswing publicly visible happened because of a supply chain failure at Anthropic itself. On March 31, a [misconfigured npm package](../events/2026-03--claude-code-leak.md) exposed the full source architecture of Claude Code — an AI agent harness used by hundreds of thousands of developers. A missing line in a config file. That's the kind of operational security gap that SOC 2 and ISO 27001 controls are supposed to prevent.

The irony is hard to miss: the company building the most powerful vulnerability detection AI in history was itself vulnerable to a packaging misconfiguration.

## vCISO Advisory Angle

This opens up a few natural conversations with clients:

- Most vulnerability management programs are scoped against known CVEs. Glasswing exposed a class of risk that doesn't live in any database yet.
- Organizations don't need to adopt AI-augmented scanning today, but documenting the risk and having a position on it seems like it'll matter soon.
- When Mythos-class tools become commercially available (12-18 months), clients who already have a policy position will be ahead of those scrambling to catch up.

Potential service areas this touches: AI-augmented assessment methodology, policy updates for AI-assisted vulnerability management, client readiness assessments, gap analysis against the emerging baseline.

---

**Sources:**
- [Project Glasswing — Anthropic](https://www.anthropic.com/glasswing)
- [Innovaiden — Glasswing assessment baseline analysis](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline)
- [Simon Willison — Glasswing analysis](https://simonwillison.net/2026/Apr/7/project-glasswing/)

---

*Added: 2026-04-08*
