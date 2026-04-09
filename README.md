# AI Security & Governance — Research Tracker

Ongoing research into agent harnesses, AI governance gaps, and events reshaping cybersecurity assessment practices. Tracking Project Glasswing, the agent harness ecosystem, and what it all means for GRC frameworks.

---

## Contents

### [Agent Harnesses — What Makes AI Models Intelligent](agent-harnesses.md)
What an agent harness is, why it matters more than the model itself, and how three real harnesses (Claude Code, OpenClaw, Claw Code) reveal a converging architecture that governance frameworks haven't caught up to yet.

### [Agent Harness Risk & Control Matrix (SOC 2 Mapping)](harness-risk-matrix.md)
A control-by-control mapping of harness governance areas — tool execution auth, payload logging, memory persistence, subagent delegation, rate/cost guardrails — to SOC 2 Trust Services Criteria.

### [Project Glasswing — What It Means for GRC](glasswing-brief.md)
Anthropic launched Project Glasswing on April 7, 2026 with AWS, Apple, Google, Microsoft, CrowdStrike, and others. Their Mythos model found thousands of zero-day vulnerabilities — including bugs that survived 27 years of human review. This brief covers what that means for SOC 2, HITRUST, HIPAA, and vCISO advisory practices.

---

## TLDR

In 10 weeks, the agent harness — the orchestration layer that gives AI models agency — went from invisible to open-source to leaked to productized. Three independent codebases proved the architecture is converging into a standard. Then the model inside the harness found thousands of zero-days that humans missed for decades. Two governance gaps now exist: the frameworks don't address the harness, and the "reasonable security" baseline just shifted. Both gaps land on the same desk.

---

## What happened in the last 10 weeks

**Late January — The world finds out what a harness is.** OpenClaw, an open-source agent harness, hit 100K GitHub stars in 2 days and 250K in 60 days — the fastest-growing repo in GitHub history. It showed that the model is interchangeable. Claude, GPT, Gemini, a local model — swap them in, the agent still works. The thing that gives a model agency isn't the model. It's the harness: the orchestration layer that manages tools, permissions, memory, and execution.

**Weeks before the leak — Anthropic sues to protect the harness.** Anthropic threatened legal action against OpenCode, a third-party coding agent that let users route their Claude subscription through OpenCode's harness instead of Claude Code. OpenCode complied and removed the plugins. The message was clear: the harness is the product, and Anthropic would litigate to protect it. You can use their model — but only through their orchestration layer.

**March 31 — That same harness leaks.** A misconfigured npm package exposed 513,000 lines of Claude Code — the proprietary harness Anthropic had just sued to protect. When people compared it to OpenClaw, they saw the same architecture. Tools, permission gates, memory, subagent orchestration, audit logging. Not similar — the same pattern. The industry now had proof: there's a converging standard for how you give an LLM agency.

**Anthropic tries to contain it — and makes it worse.** DMCA takedown notices accidentally took down 8,100 legitimate GitHub repos. Anthropic had to retract most of them, ultimately targeting only 1 repo and 96 forks with actual leaked code. The clean-room rewrites were untouchable.

**Hours later — Someone rebuilds it from scratch.** Claw Code, a clean-room rewrite in Rust and Python, hit 50K stars in 2 hours. No proprietary code, independently audited. Three independent implementations, three different codebases, one architecture. The harness pattern is reproducible. It's not anyone's IP. It's an emerging standard.

**April 1 — Anthropic stops fighting and starts selling.** Claude Managed Agents enters beta — the harness as a managed service. Containerized execution, built-in tools, persistent sessions, network access controls. Anthropic isn't fighting the pattern. They're monetizing it. The harness is now a product category. [Docs](https://platform.claude.com/docs/en/managed-agents/overview)

**April 7 — The model inside the harness finds what humans couldn't.** Project Glasswing launches. Anthropic deploys Claude Mythos to ~50 partner organizations (AWS, Apple, Google, Microsoft, CrowdStrike, Palo Alto Networks) with $100M in usage credits. Mythos finds thousands of high-severity zero-days — including a 27-year-old bug in OpenBSD and a 16-year-old flaw in FFmpeg that automated tools ran 5 million times without catching. [Announcement](https://www.anthropic.com/glasswing)

**Two gaps converge.** The harness is now a visible, understood, reproducible, purchasable thing — and the governance frameworks (ISO 42001, NIST AI RMF, SOC 2 TSC) don't address it. At the same time, the model inside the harness just proved that the "reasonable security" baseline has shifted — and the frameworks haven't caught up to that either. Both gaps land on the same desk.

---

## Key Links

| Resource | Link |
|----------|------|
| Project Glasswing (Anthropic) | [anthropic.com/glasswing](https://www.anthropic.com/glasswing) |
| Claude Code leaked source (DMCA in progress) | [github.com/codeaashu/claude-code](https://github.com/codeaashu/claude-code) |
| Claurst — clean-room Rust rewrite | [github.com/Kuberwastaken/claurst](https://github.com/Kuberwastaken/claurst) |
| OpenClaw — first popular open-source harness | [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw) |
| Claw Code — clean-room Rust/Python rewrite | [github.com/ultraworkers/claw-code](https://github.com/ultraworkers/claw-code) |
| Cranium AI — harness-level governance platform | [cranium.ai](https://cranium.ai/) |
| Claude Managed Agents — Anthropic's harness-as-a-service (beta) | [platform.claude.com](https://platform.claude.com/docs/en/managed-agents/overview) |
| Innovaiden — Glasswing assessment baseline analysis | [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) |

---

*April 2026 — Aaron Reveley*

---

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
