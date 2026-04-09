# NIST AI RMF — AI Agent Impact Tracker

Living document tracking how AI agent developments expose gaps in the NIST AI Risk Management Framework.

---

## GOVERN 2.1 — Roles and Responsibilities

**Triggered by:** [Agent harness architecture](../analysis/agent-harness-architecture.md) (ongoing), [Managed Agents Beta](../events/2026-04--managed-agents-beta.md) (April 2026)

**Current language:** Requires clear roles, responsibilities, and lines of communication for AI risk management.

**Gap/finding:** Lacks a definition for the accountability of autonomous subagents that act on behalf of a primary agent. When a harness spawns child agents with inherited permissions, who is accountable for the subagent's actions? The primary user? The harness operator? The model provider?

For managed harnesses (Managed Agents), accountability splits between the harness provider and the customer. GOVERN 2.1 should specify how this shared responsibility model works.

---

## MEASURE 2.6 — Security & Resilience

**Triggered by:** [Claude Code Leak](../events/2026-03--claude-code-leak.md) (March 2026), [Agent harness architecture](../analysis/agent-harness-architecture.md) (ongoing)

**Current language:** Mentions robustness and resilience of AI systems.

**Gap/finding:** Provides no specific guidance on audit logging for tool use — e.g., recording every JSON payload sent to an external API by the agent. The Claude Code leak revealed a full hook system (PreToolUse, PostToolUse, PreCompact, SubagentStart/Stop) for lifecycle events — exactly the kind of audit logging MEASURE 2.6 should require but doesn't specify.

---

## MAP 3.1 — Third-Party AI Risks

**Triggered by:** [Anthropic v. OpenCode](../events/2026-03--anthropic-v-opencode.md) (March 2026)

**Current language:** Addresses risks from third-party AI components.

**Gap/finding:** Vendor lock-in at the harness layer is a risk that should be documented. Anthropic's legal action against OpenCode demonstrated that model providers can enforce harness exclusivity — restricting how customers access the model. Organizations should document this dependency and have contingency plans.

---

*Last updated: 2026-04-08*
