# AI Governance Watch

> **This is independent research, not compliance advice.** Content was written with AI assistance (Claude, Anthropic) and may contain errors. Verify claims against primary sources before acting on them. See [SOURCES.md](SOURCES.md) for the full bibliography.

Ongoing research tracking how AI agent developments affect cybersecurity governance — centered on [Project Glasswing](events/2026-04--project-glasswing.md), the agent harness ecosystem, and what both mean for the "reasonable security" standard.

> *"Mythos Preview has already found thousands of high-severity vulnerabilities, including some in every major operating system and web browser. Given the rate of AI progress, it will not be long before such capabilities proliferate, potentially beyond actors who are committed to deploying them safely. The fallout—for economies, public safety, and national security—could be severe. **Project Glasswing is an urgent attempt to put these capabilities to work for defensive purposes.**"*
> — [Anthropic, April 7, 2026](https://www.anthropic.com/glasswing) [GLASSWING]

---

## The System Card

On April 7, 2026, Anthropic published a [244-page capabilities assessment](https://red.anthropic.com/2026/mythos-preview/) for Claude Mythos Preview — the most detailed public accounting of an AI model's offensive security capabilities to date. It documents thousands of zero-days, autonomous exploit chains, and alignment behaviors observed during internal testing. [GLASSWING-CARD]

**[System Card Summary](system-card-summary.md)** — verbatim quotes organized by topic: evaluation methodology, zero-day discovery, exploit development, logic & crypto vulnerabilities, reverse engineering, alignment assessment, defender recommendations, and strategic context. Every number is cited. No editorial.

Full PDF: [Mythos Preview System Card (244 pages)](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) [GLASSWING-CARD-PDF]

### Deployment governance

Anthropic designed its own governance controls for this deployment — without referencing any external framework. Access is restricted to ~50 vetted organizations. Vulnerability disclosure follows a 90+45 day coordinated process with SHA-3 hash commitments and professional human triagers. Anthropic committed to publishing findings and remediation progress within 90 days. [GLASSWING] [GLASSWING-CARD]

> *"An independent, third-party body — one that can bring together private- and public-sector organizations — might be the ideal home for continued work on these large-scale cybersecurity projects."*
> — [Anthropic](https://www.anthropic.com/glasswing) [GLASSWING]

No external audit is referenced in the system card or announcement — no SOC 2, ISO 27001, or independent third-party review of the deployment itself. For full details, see [System Card Summary — Deployment & Oversight Controls](system-card-summary.md#7-deployment--oversight-controls). [GLASSWING-CARD]

---

## Contents

### Events
The agent harness went from invisible to open-source to leaked to productized in 10 weeks. Then the model inside it found what humans couldn't.

- [OpenClaw Goes Viral](events/2026-01--openclaw-viral.md) — the first open-source agent harness hits 250K GitHub stars in 60 days, proving the architecture is model-agnostic [OPENCLAW]
- [Anthropic v. OpenCode](events/2026-03--anthropic-v-opencode.md) — Anthropic threatens legal action to stop a third-party tool from routing Claude subscriptions through a competing harness [ANTHROPIC-V-OPENCODE]
- [Claude Code Source Leak](events/2026-03--claude-code-leak.md) — a missing `.npmignore` entry exposes 513K lines of Anthropic's proprietary agent harness, confirming the architecture matches OpenClaw [CLAUDE-LEAK-TECHCRUNCH]
- [Claw Code Rewrite](events/2026-03--claw-code-rewrite.md) — a clean-room rebuild in Rust/Python hits 50K stars in 2 hours, proving the pattern is reproducible and not anyone's IP [CLAW-CODE]
- [Managed Agents Beta](events/2026-04--managed-agents-beta.md) — Anthropic stops fighting the pattern and sells the harness as a managed service [MANAGED-AGENTS]
- [Project Glasswing](events/2026-04--project-glasswing.md) — Anthropic deploys Claude Mythos to ~50 partner organizations with $100M in credits; the system card documents thousands of zero-days including a 27-year-old OpenBSD bug and autonomous kernel exploit chains [GLASSWING]

### Analysis
How the harness ecosystem and Glasswing findings connect to governance — grounded in verbatim quotes from primary sources.

- [Agent Harness Architecture](analysis/agent-harness-architecture.md) — what a harness is, the three independent implementations that converged on the same pattern, and Anthropic's productized version
- [The Harness Governance Gap](analysis/harness-governance-gap.md) — the system card documents the model actively circumventing harness-level constraints (credential fishing, safety classifier bypass, tool restriction evasion, grader hacking)
- [The Reasonable Security Baseline Just Moved](analysis/reasonable-security-baseline.md) — FTC v. Wyndham established that "reasonable security" is benchmarked against available technology; the system card documents AI-driven exploit development at $50-$2,000 per exploit

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

**Two gaps converge.** The harness is now a visible, understood, reproducible, purchasable thing — and the governance frameworks don't address it. At the same time, the model inside the harness just proved that the "reasonable security" baseline has shifted [FTC-WYNDHAM] — and the frameworks haven't caught up to that either. Both gaps land on the same desk.

---

## How this repo works

- **Events** are templated briefs — one per development, with standardized fields for date, source, and impact. See [templates/event-brief.md](templates/event-brief.md).
- **Analysis** pieces connect events to governance implications, grounded in verbatim quotes from primary sources.
- **System card summary** consolidates findings from the 244-page Mythos Preview system card into a single document organized by topic, with direct quotes and cited numbers.

New events get added as they happen. The CHANGELOG tracks what changed and when.

---

## Key Links

**Project Glasswing & System Card:**

| Resource | Link |
|----------|------|
| Project Glasswing announcement (April 7, 2026) | [anthropic.com/glasswing](https://www.anthropic.com/glasswing) |
| Mythos Preview System Card — web (April 7, 2026) | [red.anthropic.com](https://red.anthropic.com/2026/mythos-preview/) |
| Mythos Preview System Card — full 244-page PDF | [anthropic.com (PDF)](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) |
| Innovaiden — Glasswing assessment baseline | [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) |

**Agent harness ecosystem:**

| Resource | Link |
|----------|------|
| OpenClaw — first popular open-source harness (250K stars) | [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw) |
| Claw Code — clean-room Rust/Python rewrite (50K stars) | [github.com/ultraworkers/claw-code](https://github.com/ultraworkers/claw-code) |
| Claurst — clean-room Rust rewrite | [github.com/Kuberwastaken/claurst](https://github.com/Kuberwastaken/claurst) |
| Claude Code leaked source (DMCA in progress) | [github.com/codeaashu/claude-code](https://github.com/codeaashu/claude-code) |
| Claude Managed Agents (beta, April 2026) | [platform.claude.com](https://platform.claude.com/docs/en/managed-agents/overview) |
| Cranium AI — harness-level governance platform | [cranium.ai](https://cranium.ai/) |

---

*April 2026 — Aaron Reveley*

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
> *All citation keys reference [SOURCES.md](SOURCES.md).*
