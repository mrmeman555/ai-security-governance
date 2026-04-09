# Event: Claude Code Source Leak

## Date
2026-03-31

## Source
- [TechCrunch — Anthropic took down thousands of repos](https://techcrunch.com/2026/04/01/anthropic-took-down-thousands-of-github-repos-trying-to-yank-its-leaked-source-code-a-move-the-company-says-was-an-accident/)
- [Futurism — Anthropic suddenly cares about IP](https://futurism.com/artificial-intelligence/anthropic-suddenly-cares-about-intellectual-property-claude-leak)
- [GitHub DMCA notice](https://github.com/github/dmca/blob/master/2026/03/2026-03-31-anthropic.md)

## What happened
A misconfigured npm package (version 2.1.88 of @anthropic-ai/claude-code) shipped a 59.8 MB source map file that exposed the complete TypeScript source code — 513,000 lines across 1,906 files. Security researcher Chaofan Shou tweeted the discovery, and 16 million people saw the thread.

This was the proprietary harness Anthropic had just sued to protect (see [Anthropic v. OpenCode](2026-03--anthropic-v-opencode.md)). The leaked architecture revealed:
- **~40 tools** — file read/write, bash execution, web search, notebook editing, subagent dispatch
- **Dynamic permission checking** — every tool call goes through a permission gate (allow, deny, ask user)
- **Memory consolidation** — "autoDream" system that summarizes and compresses context between sessions
- **Subagent orchestration** — spawns child agents with isolated contexts for parallel work
- **Undercover mode** — strips Anthropic branding from commits (for enterprise clients)
- **Feature flags** — KAIROS (always-on proactive assistant), ULTRAPLAN (remote Opus planning sessions)
- **Hook system** — PreToolUse, PostToolUse, PreCompact, SubagentStart/Stop lifecycle events

Not a breach. Not a hack. A supply chain packaging failure — one missing exclusion in a config file exposed the entire architecture of a $2.5B AI product.

**The DMCA fallout:** Anthropic filed takedown notices that accidentally took down 8,100 legitimate GitHub repos. They retracted most of them, ultimately targeting only 1 repo and 96 forks with actual leaked code. Engineer Boris Cherny acknowledged the overbroad takedowns were unintentional.

When people compared the leaked architecture to OpenClaw, they saw the same pattern. Tools, permission gates, memory, subagent orchestration, audit logging. The convergence was now provable.

## Who's affected
Every organization using Claude Code (hundreds of thousands of developers). Every enterprise evaluating AI agent security. The leak exposed what the harness layer looks like — making governance discussions concrete rather than theoretical.

## Framework impact
- **SOC 2:** CC6.1 (Access), CC7.1 (Detection) — the leak itself is a textbook supply chain control failure. The harness architecture revealed that tool calls go through permission gates, which maps directly to access control criteria.
- **HITRUST:** None directly, but the supply chain failure demonstrates the kind of operational gap HITRUST 07.d should catch
- **HIPAA:** None directly
- **ISO 42001:** Section 8.2 — the leaked architecture shows tool-call side effects and subagent delegation that 8.2 doesn't require impact assessment for
- **NIST AI RMF:** MEASURE 2.6 — the audit logging visible in the leak (hook system, dispatch logs) is exactly what MEASURE 2.6 should require but doesn't specify

## Key links
- [Leaked source (DMCA in progress)](https://github.com/codeaashu/claude-code)
- [Claurst — clean-room Rust rewrite](https://github.com/Kuberwastaken/claurst)
- [Collection of analysis and rewrites](https://github.com/chauncygu/collection-claude-code-source-code)
- [Full leak analysis](https://claudefa.st/blog/guide/mechanics/claude-code-source-leak)

---

*Added: 2026-04-08*
