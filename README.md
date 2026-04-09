# AI Governance Watch

> **This is independent research, not compliance advice.** The analysis here reflects one practitioner's interpretation of how recent AI developments intersect with governance frameworks (SOC 2, HIPAA, HITRUST, ISO 42001, NIST AI RMF). It is not endorsed by the AICPA, NIST, ISO, HITRUST Alliance, or HHS. Framework gap claims are the author's assessment — not audit findings. Do not use this as a substitute for qualified legal, compliance, or security counsel. Content was written with AI assistance (Claude, Anthropic) and may contain errors. Events are moving fast; verify claims against primary sources before acting on them. See [SOURCES.md](SOURCES.md) for the full bibliography, [repo-governance.md](controls/repo-governance.md) for content controls, and [RISKS.md](RISKS.md) for the full risk register.

### Known risks to this repo ([full register](RISKS.md))

This list is not guaranteed to be comprehensive. This repo exists for personal practice and reference.

| Risk | Severity | Key question |
|------|----------|-------------|
| [RR-01](RISKS.md#rr-01--content-staleness) Staleness | **HIGH** | When was this last reviewed? |
| [RR-02](RISKS.md#rr-02--source-concentration) Source concentration | MEDIUM | How much comes from Anthropic's own disclosures? |
| [RR-03](RISKS.md#rr-03--ai-hallucination-in-content) AI hallucination | MEDIUM | Has every factual claim been verified against its source? |
| [RR-04](RISKS.md#rr-04--single-author-bias) Single-author bias | **HIGH** | Who else has reviewed this analysis? |
| [RR-05](RISKS.md#rr-05--unverified-sources) Unverified sources | MEDIUM | Which claims depend on pending sources? |
| [RR-06](RISKS.md#rr-06--framework-interpretation-error) Framework misreading | MEDIUM | Was the actual standard text consulted? |
| [RR-07](RISKS.md#rr-07--dual-use-concern) Dual-use | LOW | Does this add info beyond what's already public? |
| [RR-08](RISKS.md#rr-08--scope-creep) Scope creep | LOW | Does every piece serve the governance thesis? |
| [RR-09](RISKS.md#rr-09--vendor-advocacy) Vendor advocacy | LOW | Are product mentions descriptive or prescriptive? |
| [RR-10](RISKS.md#rr-10--temporal-compression-bias) Temporal compression | **HIGH** | Was there a cooling-off period before publishing? |
| [RR-11](RISKS.md#rr-11--overstatement-of-gaps) Gap overstatement | MEDIUM | Would an auditor agree these are gaps? |

Ongoing research tracking how AI agent developments affect cybersecurity governance frameworks. Focused on the agent harness ecosystem, Project Glasswing, and what both mean for SOC 2, HITRUST, HIPAA, ISO 42001, and NIST AI RMF.

---

## Contents

### Events
Individual briefs on key developments, each with framework impact analysis.

- [OpenClaw Goes Viral](events/2026-01--openclaw-viral.md) — first open-source harness, fastest-growing GitHub repo ever
- [Anthropic v. OpenCode](events/2026-03--anthropic-v-opencode.md) — Anthropic sues to protect the harness
- [Claude Code Source Leak](events/2026-03--claude-code-leak.md) — 513K lines exposed via npm misconfiguration
- [Claw Code Rewrite](events/2026-03--claw-code-rewrite.md) — clean-room rebuild, 50K stars in 2 hours
- [Managed Agents Beta](events/2026-04--managed-agents-beta.md) — Anthropic sells the harness as a service
- [Project Glasswing](events/2026-04--project-glasswing.md) — Mythos finds thousands of zero-days

### System Card Workpapers
Technical workpapers analyzing the [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) (244 pages). Each workpaper is self-contained.

- [Evaluation Methodology](system-card/evaluation-methodology.md) — scaffold, severity tiers, cost data
- [Zero-Day Discovery](system-card/zero-day-discovery.md) — OpenBSD, FFmpeg, VMM, aggregate stats
- [Exploit Development](system-card/exploit-development.md) — N-day case studies, kernel chaining, browser exploitation
- [Logic & Crypto Vulnerabilities](system-card/logic-and-crypto-vulns.md) — auth bypasses, TLS/AES-GCM/SSH weaknesses
- [Reverse Engineering](system-card/reverse-engineering.md) — closed-source analysis capabilities
- [Alignment Assessment](system-card/alignment-assessment.md) — sandbox escape, credential fishing, grader hacking, SAE interpretability
- [Defender Recommendations](system-card/defender-recommendations.md) — Anthropic's guidance for organizations
- [Strategic Context](system-card/strategic-context.md) — threat landscape transition, historical parallels

### Analysis
Deeper pieces connecting events to governance implications.

- [Agent Harness Architecture](analysis/agent-harness-architecture.md) — what a harness is, the converging pattern
- [The Harness Governance Gap](analysis/harness-governance-gap.md) — where ISO 42001, NIST AI RMF, and SOC 2 fall short
- [The Reasonable Security Baseline Just Moved](analysis/reasonable-security-baseline.md) — FTC precedent, insurance, the shifting standard

### Frameworks
Living documents that accumulate findings per compliance framework.

- [SOC 2](frameworks/soc2.md) — CC3.2, CC4.1, CC6.1, CC7.1 findings
- [HITRUST](frameworks/hitrust.md) — 07.d, 01.v, AI Security Assessment
- [HIPAA](frameworks/hipaa.md) — §164.308(a)(1), BAA for managed harnesses
- [ISO 42001](frameworks/iso42001.md) — 8.2, A.5, A.7 gaps
- [NIST AI RMF](frameworks/nist-ai-rmf.md) — GOVERN 2.1, MEASURE 2.6, MAP 3.1

### Controls
- [Harness Risk & Control Matrix (SOC 2 Mapping)](controls/harness-risk-matrix.md)
- [Repository Governance Controls](controls/repo-governance.md) — how this repo governs its own content: sourcing, review, corrections, bias
- [Repository Risk Register](RISKS.md) — running list of risks to this repo's credibility, with current severity and open questions

---

## TLDR

In 10 weeks, the agent harness — the orchestration layer that gives AI models agency — went from invisible to open-source to leaked to productized. Three independent codebases proved the architecture is converging into a standard. Then the model inside the harness found thousands of zero-days that humans missed for decades. Two governance gaps now exist: the frameworks don't address the harness, and the "reasonable security" baseline just shifted. Both gaps land on the same desk.

---

## What happened in the last 10 weeks

**Late January — The world finds out what a harness is.** OpenClaw, an open-source agent harness, hit 100K GitHub stars in 2 days and 250K in 60 days — the fastest-growing repo in GitHub history [OPENCLAW] [OPENCLAW-MEDIUM-210K] [OPENCLAW-MEDIUM-REACT]. It showed that the model is interchangeable. Claude, GPT, Gemini, a local model — swap them in, the agent still works. The thing that gives a model agency isn't the model. It's the harness: the orchestration layer that manages tools, permissions, memory, and execution.

**Weeks before the leak — Anthropic sues to protect the harness.** Anthropic threatened legal action against OpenCode, a third-party coding agent that let users route their Claude subscription through OpenCode's harness instead of Claude Code [ANTHROPIC-V-OPENCODE]. OpenCode complied and removed the plugins. The message was clear: the harness is the product, and Anthropic would litigate to protect it. You can use their model — but only through their orchestration layer.

**March 31 — That same harness leaks.** A misconfigured npm package exposed 513,000 lines of Claude Code [CLAUDE-LEAK-TECHCRUNCH] — the proprietary harness Anthropic had just sued to protect. When people compared it to OpenClaw, they saw the same architecture. Tools, permission gates, memory, subagent orchestration, audit logging. Not similar — the same pattern. The industry now had proof: there's a converging standard for how you give an LLM agency.

**Anthropic tries to contain it — and makes it worse.** DMCA takedown notices accidentally took down 8,100 legitimate GitHub repos [DMCA-ANTHROPIC]. Anthropic had to retract most of them, ultimately targeting only 1 repo and 96 forks with actual leaked code. The clean-room rewrites were untouchable.

**Hours later — Someone rebuilds it from scratch.** Claw Code, a clean-room rewrite in Rust and Python, hit 50K stars in 2 hours [CLAW-CODE]. No proprietary code, independently audited. Three independent implementations, three different codebases, one architecture. The harness pattern is reproducible. It's not anyone's IP. It's an emerging standard.

**April 1 — Anthropic stops fighting and starts selling.** Claude Managed Agents enters beta [MANAGED-AGENTS] — the harness as a managed service. Containerized execution, built-in tools, persistent sessions, network access controls. Anthropic isn't fighting the pattern. They're monetizing it. The harness is now a product category.

**April 7 — The model inside the harness finds what humans couldn't.** Project Glasswing launches [GLASSWING]. Anthropic deploys Claude Mythos to ~50 partner organizations (AWS, Apple, Google, Microsoft, CrowdStrike, Palo Alto Networks) with $100M in usage credits. Anthropic publishes a 244-page system card [GLASSWING-CARD]. Mythos finds thousands of high-severity zero-days — including a 27-year-old bug in OpenBSD, a 16-year-old flaw in FFmpeg that automated tools ran 5 million times without catching, and autonomously chained Linux kernel vulnerabilities to gain full machine control.

**April 8 — The headlines hit and the budget drops.** Glasswing dominates NBC [GLASSWING-NBC], Fortune [GLASSWING-FORTUNE], CyberScoop [GLASSWING-CYBERSCOOP]. CrowdStrike and Palo Alto Networks stocks surge [GLASSWING-CROWDSTRIKE]. Former national security officials push Section 702 FISA renewal [FISA-702]. The same day, the Pentagon's FY2027 budget proposes massive AI warfare expansion — while cutting CISA by $707M [FY2027-BUDGET]. The federal government is expanding AI offense and reducing civilian defense at the same moment.

**Two gaps converge.** The harness is now a visible, understood, reproducible, purchasable thing — and the governance frameworks (ISO 42001 [ISO-42001], NIST AI RMF [NIST-AI-RMF], SOC 2 TSC [SOC2-TSC]) don't address it. At the same time, the model inside the harness just proved that the "reasonable security" baseline has shifted [FTC-WYNDHAM] — and the frameworks haven't caught up to that either. Both gaps land on the same desk.

---

## How this repo works

- **Events** are templated briefs — one per development, with standardized fields for date, source, impact, and framework mapping. See [templates/event-brief.md](templates/event-brief.md).
- **Analysis** pieces synthesize across events to surface governance implications.
- **Framework** docs are living trackers — findings accumulate as new events occur. See [templates/framework-update.md](templates/framework-update.md).
- **System card workpapers** (`system-card/`) are self-contained technical analyses — one per major section of the Mythos system card, each standalone.
- **Controls** are mappings of harness-level risks to specific framework criteria.

New events get added as they happen. Framework docs get updated when an event affects a specific control or section. The CHANGELOG tracks what changed and when.

---

## Key Links

| Resource | Link |
|----------|------|
| Project Glasswing (Anthropic) | [anthropic.com/glasswing](https://www.anthropic.com/glasswing) |
| Mythos Preview System Card (web) | [red.anthropic.com](https://red.anthropic.com/2026/mythos-preview/) |
| Mythos Preview System Card (244-page PDF) | [anthropic.com (PDF)](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) |
| Claude Code leaked source (DMCA in progress) | [github.com/codeaashu/claude-code](https://github.com/codeaashu/claude-code) |
| OpenClaw — first popular open-source harness | [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw) |
| Claw Code — clean-room Rust/Python rewrite | [github.com/ultraworkers/claw-code](https://github.com/ultraworkers/claw-code) |
| Cranium AI — harness-level governance platform | [cranium.ai](https://cranium.ai/) |
| Claude Managed Agents (beta) | [platform.claude.com](https://platform.claude.com/docs/en/managed-agents/overview) |
| Innovaiden — Glasswing assessment baseline | [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) |
| Claurst — clean-room Rust rewrite | [github.com/Kuberwastaken/claurst](https://github.com/Kuberwastaken/claurst) |

---

*April 2026 — Aaron Reveley*

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
> *All citation keys reference [SOURCES.md](SOURCES.md). See [repo-governance.md](controls/repo-governance.md) for sourcing standards.*
