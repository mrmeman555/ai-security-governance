# AI Agent Harness — Risk & Control Matrix (SOC 2 Mapping)

> **Purpose:** Evaluate an AI agent harness (the orchestration layer) against SOC 2 Trust Services Criteria. Addresses the governance gap by auditing the middleware that manages tool execution and memory — not just the LLM itself.

---

| Control ID | Harness Governance Area | Risk Description | SOC 2 Mapping | Illustrative Control Activity |
|-----------|------------------------|------------------|---------------|-------------------------------|
| **AH-01** | Tool Execution Auth | Agent executes unauthorized API calls or system commands (e.g., `rm -rf`) without a human-in-the-loop gate. | CC6.1 (Access Utility) & CC7.2 (Security Monitoring) | The harness requires manual Approve/Deny flags for any tool call classified as "High Impact" (e.g., Write/Delete). |
| **AH-02** | Payload Logging | Agent-generated JSON payloads contain sensitive data or prompt injections that are executed but not audited. | CC2.1 (Communication) & CC7.1 (Detection) | The harness logs the full input/output of every tool call to a write-once, read-many (WORM) audit trail. |
| **AH-03** | Memory Persistence | Long-term vector memory stores PII/PHI across sessions, violating data retention or multi-tenant isolation. | CC6.1 (Logical Access) & CC3.2 (Risk Assessment) | Automated "Memory Scrubbing" routines identify and redact PII from the agent's vector database every 24 hours. |
| **AH-04** | Subagent Delegation | A primary agent spawns child agents with inherited permissions, bypassing original user identity context. | CC6.3 (User Identity) & CC4.1 (COSO Monitoring) | The harness enforces "Identity Propagation," ensuring subagents operate under the original user's least-privileged token. |
| **AH-05** | Rate / Cost Guardrails | Agent enters an infinite loop of tool calls, causing denial of service or extreme financial loss. | A1.2 (Availability - Capacity) | The harness implements a "Circuit Breaker" that kills agent processes exceeding a defined cost or token-per-minute threshold. |

---

## Notes

**Glasswing context:** Post-Glasswing, CC7.1 may need to account for whether a harness integrates AI-augmented scanning for the code the agent touches. See [glasswing-brief.md](glasswing-brief.md) for the full assessment impact.

**Inheritance vs. responsibility:** Organizations "inherit" model safety from Anthropic or OpenAI, but harness security is entirely on the deployer. A SOC 2 auditor would look for the code-level logic that restricts the agent environment — permission gates, deny lists, tool scoping.

**Prompt injection as input validation:** Prompt injection at the harness level maps to CC7.1 (System Operations). The harness needs to treat LLM output as untrusted input before passing it to a system shell or database — same principle as SQL injection prevention.

---

> *Research and analysis by Aaron Reveley. Writing assisted by Claude (Anthropic).*
