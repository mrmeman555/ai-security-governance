# AI Security & Governance — Reference Notes

A collection of reference material on agent harnesses, AI governance gaps, and recent events reshaping cybersecurity assessment practices.

---

## What happened in the last 10 weeks

**Late January — OpenClaw goes viral.** An open-source agent harness hit 100K GitHub stars in 2 days, 250K in 60 days — the fastest-growing repo in GitHub history, surpassing React's 10-year record. It proved something important: you can swap in Claude, GPT, Gemini, or a local model and the agent still works. The model is interchangeable. The harness — the orchestration layer that manages tools, permissions, memory, and multi-step execution — is what gives it agency.

**March 31 — Anthropic accidentally confirms it.** A misconfigured npm package exposed 513,000 lines of Claude Code's source — Anthropic's proprietary agent harness. Not a breach, a supply chain packaging failure. One missing config line. The leaked architecture matched OpenClaw's: same components, same patterns. Tools, permission gates, memory, subagent orchestration, audit logging. The industry could now compare the proprietary harness to the open-source one side by side. Same architecture.

**Hours later — Claw Code hits 50K stars in 2 hours.** Sigrid Jin published a clean-room rewrite of the harness in Rust and Python — no proprietary code, independently audited. It proved the architecture is reproducible. Three different harnesses, three different codebases, one converging pattern. The harness is the product.

**April 1 — Anthropic starts selling the harness as a service.** Claude Managed Agents enters beta — a pre-built, configurable agent harness running in Anthropic's cloud. Containerized execution, built-in tools, persistent sessions, network access controls. The harness is now something you buy. [Docs](https://platform.claude.com/docs/en/managed-agents/overview)

**April 7 — Project Glasswing launches.** Anthropic deployed Claude Mythos Preview to ~50 partner organizations (AWS, Apple, Google, Microsoft, CrowdStrike, Palo Alto Networks) with $100M in usage credits. Mythos found thousands of high-severity zero-days — including a 27-year-old bug in OpenBSD and a 16-year-old flaw in FFmpeg that automated tools ran 5 million times without catching. The model that runs inside the harness just demonstrated it can find what 27 years of human review missed. [Announcement](https://www.anthropic.com/glasswing)

**So where does governance go?** The harness is where permissions, tool access, audit logging, and memory persistence live. The frameworks — ISO 42001, NIST AI RMF, SOC 2 TSC — are mostly silent on it. And now the "reasonable security" baseline has shifted, because AI-powered vulnerability discovery just proved that existing scanning tools have a massive blind spot.

---

## Contents

### [Agent Harnesses — What Makes AI Models Intelligent](agent-harnesses.md)
What an agent harness is, why it matters more than the model itself, and how three real harnesses (Claude Code, OpenClaw, Claw Code) reveal a converging architecture that governance frameworks haven't caught up to yet.

### [Agent Harness Risk & Control Matrix (SOC 2 Mapping)](harness-risk-matrix.md)
A control-by-control mapping of harness governance areas — tool execution auth, payload logging, memory persistence, subagent delegation, rate/cost guardrails — to SOC 2 Trust Services Criteria. Includes vCISO implementation notes.

### [Project Glasswing — What It Means for GRC](glasswing-brief.md)
Anthropic launched Project Glasswing on April 7, 2026 with AWS, Apple, Google, Microsoft, CrowdStrike, and others. Their Mythos model found thousands of zero-day vulnerabilities — including bugs that survived 27 years of human review. This brief covers what that means for SOC 2, HITRUST, HIPAA, and vCISO advisory practices.

---

## Key Links

| Resource | Link |
|----------|------|
| Project Glasswing (Anthropic) | [anthropic.com/glasswing](https://www.anthropic.com/glasswing) |
| Claude Code leaked source (DMCA in progress) | [github.com/codeaashu/claude-code](https://github.com/codeaashu/claude-code) |
| Claurst — clean-room Rust rewrite | [github.com/Kuberwastaken/claurst](https://github.com/Kuberwastaken/claurst) |
| OpenClaw — first popular open-source harness | [github.com/openclaw/openclaw](https://github.com/openclaw/openclaw) |
| Cranium AI — harness-level governance platform | [cranium.ai](https://cranium.ai/) |
| Claude Managed Agents — Anthropic's harness-as-a-service (beta) | [platform.claude.com](https://platform.claude.com/docs/en/managed-agents/overview) |
| Innovaiden — Glasswing assessment baseline analysis | [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) |

---

*April 2026 — Aaron Reveley*

---

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
