# Deep Research Prompt: Model vs. Harness — What Produces the Capability?

## Research question

The AI Governance Watch repository frames the agent harness as the critical layer for governance — the orchestration pattern that three independent codebases converged on. But the Mythos Preview system card documents dramatic capability differences between models running in the same harness. How much of the Glasswing capability comes from the model, how much from the harness, and what does the distinction mean for governance?

## Why this matters

The repository currently implies the model is interchangeable. The system card data contradicts this. Getting the distinction wrong undermines the credibility of the governance analysis.

## What the primary sources say

### Anthropic on how the capabilities emerged

From the Mythos Preview system card (April 7, 2026):

> Mythos Preview's cybersecurity capabilities "did not [emerge] from explicit training" but rather "as a downstream consequence of general improvements in code, reasoning, and autonomy."

Source: [red.anthropic.com/2026/mythos-preview/](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD]

This states the model was NOT fine-tuned for security. The capabilities emerged from general improvements.

### Same harness, different model — the benchmark data

All comparisons used the same scaffold (Claude Code). The only variable is the model.

| Benchmark | Opus 4.6 | Mythos Preview | Source |
|-----------|----------|----------------|--------|
| OSS-Fuzz tier 1-2 crashes | 150-175 | 595 | [GLASSWING-CARD] |
| OSS-Fuzz tier 5 (full hijack) | 0 | 10 | [GLASSWING-CARD] |
| Firefox 147 working exploits | 2 | 181 | [GLASSWING-CARD] |
| Destructive action rate | 8.2% | 0.3% | [GLASSWING-CARD-PDF] |
| SHADE-Arena stealth rate | 0-3% | 4-5% | [GLASSWING-CARD-PDF] |

### Anthropic on proliferation

> "Given the rate of AI progress, it will not be long before such capabilities proliferate, potentially beyond actors who are committed to deploying them safely."

Source: [anthropic.com/glasswing](https://www.anthropic.com/glasswing) [GLASSWING]

### Anthropic on future deployment

> "Our eventual goal is to enable our users to safely deploy Mythos-class models at scale — for cybersecurity purposes, but also for the myriad other benefits that such highly capable models will bring."

Source: [anthropic.com/glasswing](https://www.anthropic.com/glasswing) [GLASSWING]

### Innovaiden on timeline

Innovaiden estimates a 12-18 month capability gap before Mythos-class models are broadly accessible.

Source: [innovaiden.com](https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline) [INNOVAIDEN-GLASSWING]

## Questions to investigate

### 1. Model architecture and training

- What is Mythos Preview? A new model family, a scaled Opus, or something else? Anthropic describes it as "a general-purpose, unreleased frontier model" — what does that mean technically?
- If the capabilities emerged from "general improvements in code, reasoning, and autonomy" rather than explicit security training, what specific improvements produce a 90x jump in exploit development (2 → 181)?
- What is the relationship between Mythos and "an upcoming Opus model" that Anthropic says will carry Mythos-class capabilities with safeguards?
- What does "Mythos-class" mean as a category? Is this a capability tier, a model family, or a marketing term?

### 2. Model contribution vs. harness contribution

- The benchmark data shows the model is the variable. But the harness enables the model to USE its capabilities (tools, file access, execution, persistence, multi-step planning). How should the contribution be framed?
- Could Mythos find these vulnerabilities WITHOUT a harness — i.e., through raw prompting alone? Or does the harness's tool system, execution environment, and multi-step orchestration enable capabilities the model couldn't express without it?
- The system card describes researchers giving a simple directive: "Please find a security vulnerability in this program." The harness handles everything else. Is this a case where the model provides the intelligence and the harness provides the agency?

### 3. Proliferation and governance implications

- If capabilities are emergent from general improvements (not security-specific training), does every frontier model on the same trajectory develop them? What does this mean for the "12-18 month gap" estimate?
- OpenClaw is model-agnostic. When open-source or competing models reach Mythos-class general capability, they can be plugged into the same harness pattern. What governance framework addresses this?
- The repo frames two governance gaps: (1) frameworks don't address the harness, (2) the reasonable security baseline shifted. Is there a third gap: frameworks don't address emergent capabilities that weren't explicitly trained?

### 4. What needs correcting in the repository

- The README states OpenClaw "is model-agnostic — Claude, GPT, Gemini, or a local model can be swapped in." This is architecturally true but capability-misleading. How should this be qualified?
- The timeline narrative implies the harness is the story. The system card data shows the model is equally the story. How should the repo frame the relationship between the two?
- Is "the model is interchangeable" true at the architecture level but false at the capability level? If so, what is the precise, citable way to state this?

## Source material

- Mythos Preview System Card — full 244-page PDF: https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf
- Project Glasswing announcement: https://www.anthropic.com/glasswing
- System card summary (verbatim quotes): system-card-summary.md in this repository
- Innovaiden Glasswing assessment: https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline
- Full bibliography: SOURCES.md in this repository

## Output format

Produce a technically precise analysis that:
1. States the model vs. harness distinction using only citable facts from primary sources
2. Identifies every claim in this repository that needs correction or qualification
3. Proposes revised language that is defensible — no judgment calls, only documented assertions
4. Addresses the governance implications of emergent (vs. trained) capabilities

---

*Generated 2026-04-09 for AI Governance Watch research.*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
