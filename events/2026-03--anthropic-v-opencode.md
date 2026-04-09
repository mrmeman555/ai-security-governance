# Event: Anthropic Takes Legal Action Against OpenCode

## Date
2026-03 (weeks before March 31 leak)

## Source
- [Hacker News discussion](https://news.ycombinator.com/item?id=47444748)

## What happened
Anthropic threatened legal action against OpenCode, a third-party coding agent that let users route their Claude subscription through OpenCode's harness instead of Claude Code. OpenCode had built plugins allowing Claude subscription holders to use their paid access through an alternative interface.

Anthropic's Terms of Service explicitly prohibit this. The message was clear: the harness is the product, and Anthropic would litigate to protect it. You can use their model — but only through their orchestration layer. OpenCode complied and removed the plugins as of version 1.3.0.

The business logic: Claude Code subscriptions offer significantly cheaper per-token rates than the public API. By restricting subscription access to their official harness, Anthropic maintains control over user experience, token consumption patterns, telemetry data collection, and customer lock-in.

## Who's affected
Any third-party tool that integrates with Claude through unofficial channels. Establishes that Anthropic considers the harness a core product boundary, not just a convenience layer.

## Framework impact
- **SOC 2:** None directly
- **HITRUST:** None directly
- **HIPAA:** None directly
- **ISO 42001:** Highlights vendor dependency risk — organizations relying on third-party harnesses face supply chain disruption if the model provider enforces harness exclusivity
- **NIST AI RMF:** MAP 3.1 (Third-party AI risks) — vendor lock-in at the harness layer is a risk that should be documented

## Key links
- [Hacker News — Anthropic takes legal action against OpenCode](https://news.ycombinator.com/item?id=47444748)

---

*Added: 2026-04-08*
