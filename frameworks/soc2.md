# SOC 2 — AI Agent Impact Tracker

Living document tracking how AI agent developments affect SOC 2 Trust Services Criteria [SOC2-TSC].

---

## CC3.2 — Risk Assessment

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026)

**Current language:** Requires organizations to identify and assess risks to the achievement of objectives.

**Gap/finding:** Must now account for accelerated exploitation windows. If an AI can find a 27-year-old bug in hours — and autonomously chain multiple Linux kernel vulnerabilities to gain full machine control — traditional "low" risk ratings for legacy code are no longer defensible. Anthropic published a 244-page system card documenting these capabilities. Risk assessments should consider: "What is our exposure to zero-day vulnerabilities in foundational software, and what is our detection capability for vulnerabilities that don't appear in known databases?" See [WP-02: Zero-Day Discovery](../system-card/zero-day-discovery.md) for the evidence.

---

## CC4.1 — Monitoring

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026)

**Current language:** Requires the entity to select, develop, and perform ongoing and/or separate evaluations.

**Gap/finding:** Language needs to shift from "periodic" to near-continuous automated scanning. Manual quarterly pentests may no longer meet the "effective" threshold given the scale of AI-driven discovery. See [WP-01: Evaluation Methodology](../system-card/evaluation-methodology.md) for the cost and scale data.

---

## CC6.1 — Logical and Physical Access

**Triggered by:** [Claude Code Leak](../events/2026-03--claude-code-leak.md) (March 2026), [Managed Agents Beta](../events/2026-04--managed-agents-beta.md) (April 2026)

**Current language:** Requires the entity to implement logical access security over protected information assets.

**Gap/finding:** The leaked Claude Code architecture revealed that tool calls go through permission gates — this maps directly to access control criteria. For managed harnesses (Managed Agents), shared responsibility becomes the question: who controls tool permissions, the customer or Anthropic? SOC 2 auditors would look for the code-level logic restricting the agent environment — permission gates, deny lists, tool scoping.

---

## CC7.1 — Vulnerability Management / Detection

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026), [Claude Code Leak](../events/2026-03--claude-code-leak.md) (March 2026)

**Current language:** Requires identification and remediation of known vulnerabilities.

**Gap/finding:** Language must expand from "remediation of known vulnerabilities" to include preemptive discovery using AI-native tools that operate at machine speed. The residual risk statement should acknowledge whether detection capabilities extend beyond known-CVE scanning. This becomes a finding if the risk isn't acknowledged. Control narratives for vulnerability management may need to address whether detection capabilities extend beyond known-CVE scanning, now that AI tools can demonstrably find what scanners can't. See [WP-03: Exploit Development](../system-card/exploit-development.md) for the N-day case studies showing how public CVEs become full exploits in hours.

**Harness context:** Post-Glasswing, CC7.1 may also need to account for whether a harness integrates AI-augmented scanning for the code the agent touches.

---

## CC2.1 — Communication

**Triggered by:** [Managed Agents Beta](../events/2026-04--managed-agents-beta.md) (April 2026)

**Current language:** Requires communication of internal and external information necessary to support the functioning of internal control.

**Gap/finding:** Managed harness event streaming and server-side persistence create new data handling obligations. Full input/output of every tool call should be logged to a write-once audit trail.

---

## CC6.3 — User Identity

**Triggered by:** [Agent harness architecture](../analysis/agent-harness-architecture.md) (ongoing)

**Current language:** Requires the entity to register and authorize new users.

**Gap/finding:** When a primary agent spawns subagents with inherited permissions, the original user identity context may be lost. Harnesses need identity propagation ensuring subagents operate under the original user's least-privileged token.

---

## CC6.1 — Logical and Physical Access (Alignment Evidence)

**Triggered by:** [Mythos System Card](../events/2026-04--project-glasswing.md) (April 2026) [GLASSWING-CARD-PDF]

**Gap/finding:** The system card documents the model actively searching for credentials via `/proc` inspection, attempting to dump supervisor process memory with `gdb` and `dd`, and bypassing tool restrictions by opening the application finder to access `bash -c`. These are access control failures at the harness layer — the model found ways around logical access boundaries. For organizations deploying AI agents, CC6.1 control narratives should address whether the agent's execution environment prevents process inspection, memory access, and alternative execution paths. Permission gates at the tool-call level are insufficient if the agent can access the underlying operating system. See [WP-06: Alignment Assessment](../system-card/alignment-assessment.md) for the full evidence.

---

## Harness Risk Matrix

For a detailed control-by-control mapping, see [harness-risk-matrix.md](../controls/harness-risk-matrix.md).

---

*Last updated: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
