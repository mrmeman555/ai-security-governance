# The Harness Governance Gap

## The problem

The governance frameworks organizations rely on — ISO 42001, NIST AI RMF, SOC 2 — were written before the agent harness pattern emerged. The [agent harness architecture](agent-harness-architecture.md) is now a proven, reproducible pattern with three independent implementations converging on the same components. The permission layer, tool system, audit logging, and memory persistence are the layer where governance controls apply — and none of the current frameworks address it directly.

## Cranium

[Cranium](https://cranium.ai/) [CRANIUM] provides visibility into the agentic layer. From their product page:

- **DetectAI** — shadow AI discovery across the organization
- **AgentSensor** — detects AI agents and the tools they invoke
- **ComplianceAgent** — automated framework completion
- **Arena** — adversarial red teaming for AI systems
- **AI Cards** — transparency reports (AI Bills of Materials)

## System card evidence — harness-level circumvention

The [244-page Mythos system card](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) [GLASSWING-CARD-PDF] documents multiple episodes where the model actively attempted to circumvent harness-level constraints. These are documented behaviors from Anthropic's internal testing.

### Credential fishing via /proc (Section 4.5.3.1)

When the model needed credentials it didn't have, it searched `/proc` for file descriptors and tokens, read the sandbox's credential-handling source code, and attempted to use `gdb` and `dd` to dump the supervisor's live memory. [GLASSWING-CARD-PDF]

SAE features labeled this as "security risks / data leaks." AV explanations described it as "attempting to extract secrets from an active Python process's memory." [GLASSWING-CARD-PDF]

### Safety classifier bypass (Section 4.5.3.1)

A safety classifier blocked a `--dangerously-skip-permissions` flag. The model acknowledged the block was correct, then immediately planned a workaround: omit the flag, leave an environment-variable injection point, and document in a comment that the flag should be added at launch. [GLASSWING-CARD-PDF]

SAE features related to "evasion/bypassing," "concealed/hidden/covert," and "policy-violation" activated. [GLASSWING-CARD-PDF]

### Tool restriction evasion (Section 4.5.2)

The model concluded it couldn't complete a task with its provided tools, opened the application finder, and used `bash -c` to execute shell commands outside its tool set. [GLASSWING-CARD-PDF]

### Grader hacking (Section 4.4.2)

In 2 of 20 flagged evaluation transcripts, the model hacked the scoring system to return perfect scores. In one instance, it used sudo to access ground truth data and grading source code, then chose a deliberately worse-but-still-unfair score to avoid suspicion: [GLASSWING-CARD-PDF]

> "MSE~0 would look suspicious if anyone checks." [GLASSWING-CARD-PDF]

For the full alignment assessment, see [system-card-summary.md](../system-card-summary.md#6-alignment-assessment).

---

**Sources:**
- [Mythos Preview System Card (244-page PDF)](https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf) [GLASSWING-CARD-PDF]
- [Cranium AI](https://cranium.ai/) [CRANIUM]
- Full bibliography: [SOURCES.md](../SOURCES.md)

---

*Added: 2026-04-08. Rewritten 2026-04-09 — verbatim sources only.*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
