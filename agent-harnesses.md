# Agent Harnesses — What Makes AI Models Intelligent

## The Core Idea

A language model by itself is a brain in a jar. It can think, but it can't do anything. An **agent harness** is the orchestration layer that sits between the model and the outside world — it's the nervous system and body. The harness is what manages tool calls, file access, context windows, memory, permissions, multi-step reasoning, and interaction with external systems.

**The harness is what makes a model intelligent in practice.** Without it, GPT-4 or Claude are autocomplete engines. With it, they write code, manage infrastructure, run audits, and orchestrate other agents. The model provides reasoning. The harness provides agency.

## The Architecture

Every agent harness has the same core components:

| Component | What it does |
|-----------|-------------|
| **Tool system** | Defines what the agent can do — read files, run commands, search the web, call APIs |
| **Permission layer** | Controls what the agent is allowed to do — sandboxing, deny lists, approval gates |
| **Context management** | Decides what the agent knows on each turn — file contents, conversation history, memory |
| **Memory / persistence** | What survives between sessions — auto-memory, project notes, learned preferences |
| **Orchestration** | Multi-step planning, subagent dispatch, task decomposition |
| **Audit / logging** | What gets recorded — tool calls, decisions, outputs, provenance |

The permission layer and audit logging are where **governance** lives. This is the layer that ISO 42001, NIST AI RMF, and every future AI governance framework will need to address — and almost none of them do yet.

## Three Real Agent Harnesses

### Claude Code (Anthropic — proprietary, leaked March 31 2026)

Anthropic's official CLI agent for developers. On March 31, a misconfigured npm package exposed the full TypeScript source — 513,000 lines across 1,906 files. What the leak revealed:

- **~40 tools** — file read/write, bash execution, web search, notebook editing, subagent dispatch
- **Dynamic permission checking** — every tool call goes through a permission gate (allow, deny, ask user)
- **Memory consolidation** — a system called "autoDream" that summarizes and compresses context between sessions
- **Subagent orchestration** — spawns child agents with isolated contexts for parallel work
- **Undercover mode** — strips Anthropic branding from commits (for enterprise clients)
- **Feature flags for unreleased capabilities** — KAIROS (always-on proactive assistant), ULTRAPLAN (offloads planning to remote Opus sessions)
- **Hook system** — PreToolUse, PostToolUse, PreCompact, SubagentStart/Stop lifecycle events that let users inject custom governance

**The full leaked source (DMCA takedowns in progress):** https://github.com/codeaashu/claude-code

**Clean-room Rust reimplementation (legally clean):** https://github.com/Kuberwastaken/claurst

**Collection of analysis and rewrites:** https://github.com/chauncygu/collection-claude-code-source-code

The leak itself was a supply chain / packaging failure — a missing exclusion in a config file. Not a breach, not a hack. A single line of configuration exposed the entire architecture of a $2.5 billion AI product. This is exactly the kind of operational security gap that SOC 2 and ISO 27001 controls are supposed to prevent.

### OpenClaw (open source — 247K GitHub stars)

OpenClaw was the first popular open-source agent harness — and that's what made it such a big deal. Before OpenClaw, agent harnesses were proprietary black boxes locked inside Anthropic, OpenAI, and Google. OpenClaw cracked the pattern open. It proved that the harness — not the model — is the product. You could swap in Claude, GPT, Gemini, or a local model, and the agent still worked. The model was interchangeable. The harness was what gave it agency.

That's why it hit 247K GitHub stars in under four months. It wasn't just a tool — it was the first time the broader developer community could see, modify, and extend the orchestration layer that makes AI models actually do things.

- **Multi-model proxy** — drives Claude, GPT, Gemini, local models through a unified interface
- **SOUL.md** — OpenClaw's version of CLAUDE.md. A markdown file that defines the agent's identity, behavior rules, and capabilities. Same architectural pattern.
- **Agent-to-agent communication** — ACP (Agent Client Protocol) for stateful sessions between agents
- **162+ production-ready agent templates** across 19 categories
- **Plugin system** — openclaw-claude-code plugin turns Claude Code into a programmable headless coding engine

**Repo:** https://github.com/openclaw/openclaw

Then Claude Code's source leaked, and suddenly people could compare the proprietary harness to the open-source one side by side. Same architecture. Same components. Tools, permissions, context, memory, orchestration, logging. The governance questions are identical regardless of whether the harness is open or closed. That convergence is the signal — this is the standard pattern, and it's where controls need to go.

### Claw Code (clean-room Python/Rust rewrite)

A clean-room rewrite of the Claude Code agent harness architecture, built from scratch in Python and Rust after the leak. Not a copy — a reimplementation from the architectural specification.

**Site:** https://claw-code.codes/

This is significant because it proves the harness architecture is reproducible. The model is interchangeable. The harness is the product.

## Why This Matters for GRC

### The governance gap

ISO 42001 covers AI system lifecycle governance. NIST AI RMF covers risk management. Neither has deep guidance on **harness-level controls** — the permission layer, the tool system, the audit logging, the memory persistence. This is the layer where:

- An agent gets permission to read client data (or doesn't)
- Tool calls are logged for audit trails (or aren't)
- Subagents inherit parent permissions (or escalate)
- Memory persists sensitive information between sessions (or is wiped)
- Agents can modify their own behavior rules (or can't)

### Where the frameworks are silent — specifically

**ISO 42001:**
- **Section 8.2 (AI System Impact Assessment)** — focuses on broad societal and privacy impacts but lacks requirements for tool-call side effects or delegated subagent risk
- **Annex A.5 (Data & Information)** — addresses data lifecycle but is silent on memory persistence (long-term agent state) which can bypass standard session-clearing protocols
- **Annex A.7 (AI System Life Cycle)** — focuses on model development; does not mandate permission gates for autonomous execution of API calls by agents

**NIST AI RMF:**
- **GOVERN 2.1** — requires clear roles and responsibilities but lacks a definition for the accountability of autonomous subagents that act on behalf of a primary agent
- **MEASURE 2.6 (Security & Resilience)** — mentions robustness but provides no specific guidance on audit logging for tool use (e.g., recording every JSON payload sent to an external API by the agent)

**AICPA:** As of early 2026, the AICPA has not issued formal updates to the Trust Services Criteria specifically for agentic AI, leaving auditors to map these risks to the broad "Security" (CC series) and "Processing Integrity" criteria.

**HITRUST AI Security Assessment:** Introduced in late 2024 with 51 AI-specific controls. While prescriptive, it relies on "Inheritance" from providers (like OpenAI/Google) rather than explicit harness-level requirements for custom-built orchestrators.

### Real-world governance failure

In 2025-2026, attackers utilized Claude-based agents against Mexican government systems — highlighting a lack of harness-level guardrails preventing models from executing offensive security scripts even when the model itself has safety filters. The model had safeguards. The harness didn't. That's the gap.

Every enterprise deploying AI agent systems will need governance over this layer. Most don't even know it exists yet. The firms that can articulate "here's what an agent harness is, here's where the controls go, here's how to audit it" will own the AI governance consulting market.

### Harness Risk & Control Matrix (SOC 2 Mapping)

For a detailed control-by-control mapping of harness governance areas to SOC 2 Trust Services Criteria, see [harness-risk-matrix.md](harness-risk-matrix.md).

### The Cranium connection

Cranium's AgentSensor product does exactly this — it provides visibility into the agentic layer by detecting AI agents, the tools they invoke, and other agents in their networks. This is harness-level governance as a product. The consulting opportunity sits right next to it: help clients understand what they're looking at and what controls they need.

## The Bottom Line

> The model is the brain. The harness is everything else. The harness is where governance lives. The harness is where security controls go. The harness is what most people don't know exists. That's the gap.

---


