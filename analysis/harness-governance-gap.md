# The Harness Governance Gap — Where Frameworks Are Silent

## The Problem

ISO 42001 covers AI system lifecycle governance. NIST AI RMF covers risk management. Neither has deep guidance on **harness-level controls** — the permission layer, the tool system, the audit logging, the memory persistence. This is the layer where:

- An agent gets permission to read client data (or doesn't)
- Tool calls are logged for audit trails (or aren't)
- Subagents inherit parent permissions (or escalate)
- Memory persists sensitive information between sessions (or is wiped)
- Agents can modify their own behavior rules (or can't)

The [agent harness architecture](agent-harness-architecture.md) is now a proven, reproducible pattern. Three independent implementations have converged on the same components. But the governance frameworks haven't caught up.

## Where the Frameworks Are Silent — Specifically

### ISO 42001

- **Section 8.2 (AI System Impact Assessment)** — focuses on broad societal and privacy impacts but lacks requirements for tool-call side effects or delegated subagent risk
- **Annex A.5 (Data & Information)** — addresses data lifecycle but is silent on memory persistence (long-term agent state) which can bypass standard session-clearing protocols
- **Annex A.7 (AI System Life Cycle)** — focuses on model development; does not mandate permission gates for autonomous execution of API calls by agents

### NIST AI RMF

- **GOVERN 2.1** — requires clear roles and responsibilities but lacks a definition for the accountability of autonomous subagents that act on behalf of a primary agent
- **MEASURE 2.6 (Security & Resilience)** — mentions robustness but provides no specific guidance on audit logging for tool use (e.g., recording every JSON payload sent to an external API by the agent)

### AICPA / SOC 2

As of early 2026, the AICPA has not issued formal updates to the Trust Services Criteria specifically for agentic AI, leaving auditors to map these risks to the broad "Security" (CC series) and "Processing Integrity" criteria.

For a control-by-control mapping of harness risks to SOC 2 TSC, see the [harness risk matrix](../controls/harness-risk-matrix.md).

### HITRUST AI Security Assessment

Introduced in late 2024 with 51 AI-specific controls. While prescriptive, it relies on "Inheritance" from providers (like OpenAI/Google) rather than explicit harness-level requirements for custom-built orchestrators.

## Real-World Governance Failure

In 2025-2026, attackers utilized Claude-based agents against Mexican government systems — highlighting a lack of harness-level guardrails preventing models from executing offensive security scripts even when the model itself has safety filters. The model had safeguards. The harness didn't. That's the gap.

## The Cranium Connection

[Cranium](https://www.cranium.ai/) is one of the first products addressing this gap directly. Their platform provides visibility into the agentic layer:

- **DetectAI** — shadow AI discovery across the organization
- **AgentSensor** — detects AI agents and the tools they invoke
- **ComplianceAgent** — automated framework completion
- **Arena** — adversarial red teaming for AI systems
- **AI Cards** — transparency reports (AI Bills of Materials)

It's harness-level governance as a product — detection and compliance tooling for the orchestration layer that frameworks haven't addressed yet.

## The Bottom Line

Every enterprise deploying AI agent systems will need governance over this layer. Most don't even know it exists yet. The frameworks will catch up — ISO 42001 and NIST AI RMF are both under active revision. The question is whether organizations are mapping these risks now or waiting to be told.

---

*Added: 2026-04-08*
