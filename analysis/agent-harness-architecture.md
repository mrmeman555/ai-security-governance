# Agent Harness Architecture

## What it is

The leaked Claude Code source (513,000 lines exposed via npm misconfiguration [CLAUDE-LEAK-TECHCRUNCH]) revealed the architecture of a production agent harness. Analysis of the source [CLAUDE-LEAK-ANALYSIS] described a tool system that manages file access, command execution, web search, permission gates, context windows, memory persistence, subagent orchestration, and audit logging.

Every agent harness converges on the same core components:

| Component | What it does |
|-----------|-------------|
| **Tool system** | Defines what the agent can do — read files, run commands, search the web, call APIs |
| **Permission layer** | Controls what the agent is allowed to do — sandboxing, deny lists, approval gates |
| **Context management** | Decides what the agent knows on each turn — file contents, conversation history |
| **Memory / persistence** | What survives between sessions — auto-memory, project notes, preferences |
| **Orchestration** | Multi-step planning, subagent dispatch, task decomposition |
| **Audit / logging** | What gets recorded — tool calls, decisions, outputs, provenance |

## The convergence

Between January and April 2026, three independent implementations emerged — different teams, different languages, no shared code. All converged on the same pattern.

| Harness | Origin | Language | Stars | Source |
|---------|--------|----------|-------|--------|
| Claude Code | Anthropic (proprietary, leaked March 31) | TypeScript | — | ~40 tools, permission gates, subagent orchestration, hook system [CLAUDE-LEAK-TECHCRUNCH] |
| OpenClaw | Open source (Peter Steinberger, late January) | Multi-language | 210K in 10 days [OPENCLAW-MEDIUM-210K], 250K in 60 days [OPENCLAW-MEDIUM-REACT] | Multi-model proxy, SOUL.md identity files, 162+ agent templates [OPENCLAW] |
| Claw Code | Clean-room rewrite (Sigrid Jin, March 31) | Python/Rust | 50K in 2 hours | Independently audited, no proprietary code [CLAW-CODE] |

## Managed Agents — Anthropic productizes the pattern

On April 1, 2026, Anthropic launched Claude Managed Agents in beta [MANAGED-AGENTS]. From the documentation:

> "Claude Managed Agents provides the harness and infrastructure for running Claude as an autonomous agent. Instead of building your own agent loop, tool execution, and runtime, you get a fully managed environment where Claude can read files, run commands, browse the web, and execute code securely." [MANAGED-AGENTS]

The four core concepts map directly to the architecture table above:

| Concept | Description (from Anthropic docs) |
|---------|-----------------------------------|
| **Agent** | "The model, system prompt, tools, MCP servers, and skills" |
| **Environment** | "A configured container template (packages, network access)" |
| **Session** | "A running agent instance within an environment, performing a specific task and generating outputs" |
| **Events** | "Messages exchanged between your application and the agent (user turns, tool results, status updates)" |

[MANAGED-AGENTS]

---

*Added: 2026-04-08. Rewritten 2026-04-09 — verbatim sources only.*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
