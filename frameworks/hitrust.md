# HITRUST — AI Agent Impact Tracker

Living document tracking how AI agent developments affect HITRUST controls [HITRUST-CSF] and assessments [HITRUST-AI].

---

## 07.d — Technical Vulnerability Management

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026)

**Current language:** Requires regular scanning and patching of known vulnerabilities.

**Gap/finding:** Currently satisfied by regular scanning and patching. Post-Glasswing, assessors may need to ask whether the organization has evaluated AI-augmented discovery tools or documented a risk acceptance for not using them. HITRUST updates its control framework regularly, and the next revision will likely reference AI-augmented vulnerability management. See [WP-07: Defender Recommendations](../system-card/defender-recommendations.md) for Anthropic's own guidance on AI-augmented scanning as standard practice.

---

## 01.v — Information Access Restriction

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026)

**Current language:** Restricts access to information and application system functions.

**Gap/finding:** Zero-day exposure in foundational software (operating systems, browsers, media libraries) affects the risk calculus for access controls built on top of that software. If the foundation has unknown vulnerabilities, the access controls layered on it carry inherited risk.

---

## HITRUST AI Security Assessment

**Triggered by:** [Agent harness architecture](../analysis/agent-harness-architecture.md) (ongoing)

**Context:** Introduced in late 2024 with 51 AI-specific controls. While prescriptive, it relies on "Inheritance" from providers (like OpenAI/Google) rather than explicit harness-level requirements for custom-built orchestrators.

**Gap/finding:** The inheritance model becomes directly relevant for managed harnesses like [Claude Managed Agents](../events/2026-04--managed-agents-beta.md) — what controls do you inherit from the managed harness provider? For self-built harnesses, the 51 controls don't address tool-call permission gates, subagent delegation, or memory persistence at the orchestration layer.

**Source:** [HITRUST AI Security Assessment](https://hitrustalliance.net/assessments-and-certifications/aisecurityassessment) | [Schellman — HITRUST AI to ISO 42001 mapping](https://www.schellman.com/blog/ai-services/hitrust-ai-security-assessment-path-to-iso-42001)

---

*Last updated: 2026-04-08*
