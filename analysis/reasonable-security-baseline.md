# The Reasonable Security Baseline Just Moved

## FTC precedent — "reasonable security"

In *FTC v. Wyndham Worldwide Corp.*, 799 F.3d 236 (3d Cir. 2015), the Third Circuit upheld the FTC's authority under Section 5 (unfairness prong) to enforce data security standards. The key holding: companies have "fair notice" that failing to maintain reasonable security can constitute an unfair practice. The court applied a cost-benefit analysis framework for reasonableness. [FTC-WYNDHAM]

The case arose from three data breaches resulting in $10M+ in fraud. The FTC's case page, blog post on the ruling, and the full opinion are available via Justia. [FTC-WYNDHAM]

## System card cost data

The [Mythos Preview system card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD] documents what AI-driven vulnerability discovery costs:

| Target | Campaign cost | Per-exploit cost |
|--------|--------------|-----------------|
| OpenBSD (1,000 runs) | ~$20,000 | ~$50 per successful run |
| FFmpeg (hundreds of runs) | ~$10,000 | — |
| Linux kernel exploit chains | — | Under $2,000 per chain |
| General range | — | $50-$2,000 per exploit |

[GLASSWING-CARD]

> "Engineers at Anthropic with no formal security training have asked Mythos Preview to find remote code execution vulnerabilities overnight, and woken up the following morning to a complete, working exploit" [GLASSWING-CARD]

> "Over 99% of the vulnerabilities we've found have not yet been patched" [GLASSWING-CARD]

Against Firefox 147's JavaScript engine, Mythos produced 181 working exploits where the previous model managed 2. [GLASSWING-CARD]

The Linux kernel finding: Mythos autonomously chained up to 4 kernel vulnerabilities to gain full machine control. [GLASSWING-CARD]

## CISA budget signal

On April 8, 2026 — one day after Glasswing launched — the Pentagon's FY2027 budget proposal was released. [FY2027-BUDGET]

- Proposes $1.5T defense spending (42% YoY increase) [FY2027-BUDGET, Vision Times]
- Cuts CISA by $707M (from ~$2.9B to ~$2.4B) [FY2027-BUDGET, MeriTalk]

Sources: MeriTalk reporting on CISA cuts, Cybersecurity Dive budget analysis, Vision Times on defense total. [FY2027-BUDGET]

## Access and timeline

Project Glasswing is restricted to ~50 partner organizations (AWS, Apple, Google, Microsoft, CrowdStrike, Palo Alto Networks, JPMorganChase, NVIDIA, Broadcom, Linux Foundation). [GLASSWING]

Anthropic does not plan to make Mythos Preview generally available but aims to "enable users to safely deploy Mythos-class models at scale" with safeguards in an upcoming Opus model. Innovaiden estimates a 12-18 month capability gap before Mythos-class models are broadly accessible. [INNOVAIDEN-GLASSWING]

## The supply chain context

The event that made Glasswing publicly visible followed a supply chain failure at Anthropic itself. On March 31, a [misconfigured npm package](../events/2026-03--claude-code-leak.md) exposed 513,000 lines of Claude Code — an AI agent harness used by hundreds of thousands of developers. Boris Cherny (Anthropic head of Claude Code) described it as "a plain developer error" — a missing `.npmignore` entry for Bun-generated source maps. [DMCA-ANTHROPIC] [CLAUDE-LEAK-TECHCRUNCH]

---

**Sources:**
- [FTC v. Wyndham Worldwide Corp.](https://law.justia.com/cases/federal/appellate-courts/ca3/14-3514/14-3514-2015-08-24.html), 799 F.3d 236 (3d Cir. 2015) [FTC-WYNDHAM]
- [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD]
- [Project Glasswing — Anthropic](https://www.anthropic.com/glasswing) [GLASSWING]
- [Innovaiden — Glasswing assessment baseline](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) [INNOVAIDEN-GLASSWING]
- [Pentagon FY2027 Budget](https://cdn.meritalk.com/articles/trump-fy2027-budget-cuts-cisa-by-707m-reduces-st-agencies/) [FY2027-BUDGET]
- Full bibliography: [SOURCES.md](../SOURCES.md)

---

*Added: 2026-04-08. Rewritten 2026-04-09 — verbatim sources only.*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
