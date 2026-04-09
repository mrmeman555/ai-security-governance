# System Card Workpaper: Defender Recommendations

> Workpaper analyzing the [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD].
> Part of the [system card workpaper series](.). See the [workpaper index](README.md) for the full list.

## Summary

The system card includes six recommendations for defenders, plus guidance on automating incident response. These are Anthropic's own prescriptions for what security teams should do now — before Mythos-class capabilities become broadly available. The recommendations range from immediate ("deploy current frontier models for vulnerability discovery today") to structural ("modernize software distribution practices").

## Source material
- **System card section(s):** "Suggestions for defenders today"
- **PDF page range:** See 244-page PDF [GLASSWING-CARD-PDF]

## Findings

### 1. Leverage current frontier models now

Organizations should deploy existing models like Claude Opus 4.6 to strengthen defenses immediately, rather than waiting for Mythos-class access. The system card notes that *"current frontier models remain extremely competent at finding vulnerabilities,"* discovering *"high- and critical-severity vulnerabilities almost everywhere"* tested.

The argument: early adoption with current models prepares infrastructure and workflows for future capabilities. Organizations that start now will have the scaffolding, processes, and institutional knowledge to absorb more powerful models as they become available.

### 2. Expand model applications beyond vulnerability finding

Models should assist with the full security lifecycle, not just bug-finding:

- **Triage:** Evaluating bug report correctness and severity
- **Deduplication:** Identifying when multiple reports describe the same underlying issue
- **Reproduction:** Generating reproduction steps and proof-of-concept exploits
- **Patching:** Writing initial patch proposals
- **Cloud configuration:** Analyzing misconfigurations
- **Code review:** Pull request security review support
- **Migration:** Accelerating legacy system modernization

The system card argues: *"it is worth experimenting with language models for all security tasks you are doing manually today."*

### 3. Accelerate patch cycles

N-day exploits can now be weaponized *"much faster, cheaper, and without intervention."* Organizations must:

- Compress deployment windows through tighter enforcement
- Enable auto-updates wherever feasible
- Treat CVE-related dependency updates as **urgent** rather than routine

The window between CVE publication and weaponization has compressed from weeks/months to hours (see [WP-03: Exploit Development](exploit-development.md) for the N-day case studies).

### 4. Modernize software distribution practices

Current distribution cycles reserve out-of-band releases for active exploits, delaying others until standard release cycles. This approach may become untenable when thousands of critical vulnerabilities enter the disclosure pipeline simultaneously. Seamless patching without restarts becomes increasingly critical.

### 5. Update vulnerability disclosure policies

Companies should refresh existing vulnerability handling procedures to account for the **scale** of bugs language models will reveal. Current policies assume human-speed discovery rates. AI-speed discovery creates volume that existing processes cannot absorb.

### 6. Expedite mitigation for legacy systems

Organizations responsible for critical but unsupported software must prepare contingencies now — outlining how to surge resources for unexpected vulnerabilities in acquired but no-longer-maintained applications.

This is especially relevant for healthcare, financial services, and government — sectors with large installed bases of legacy systems that cannot be easily replaced.

### Additional: Automate incident response

Detection teams face unprecedented alert volumes. Models should handle:

- **Triage:** Technical alert classification and prioritization
- **Summarization:** Event summarization for human review
- **Proactive hunting:** Model-driven threat hunting
- **Incident support:** Note-taking, artifact capture, investigation thread management, postmortem drafting

## Governance implications

These recommendations provide **Anthropic's own baseline** for what "reasonable security" looks like in the post-Glasswing environment. This has direct implications for how frameworks should evolve:

- **HITRUST 07.d (Technical Vulnerability Management):** Anthropic's recommendation to use AI-augmented discovery as standard practice provides evidence for what 07.d should require. See [frameworks/hitrust.md](../frameworks/hitrust.md).
- **SOC 2 CC4.1 (Monitoring):** Recommendation 1 (use frontier models now) and the incident response automation guidance directly inform what "effective" monitoring means. See [frameworks/soc2.md](../frameworks/soc2.md).
- **SOC 2 CC7.1 (Vulnerability Management):** Recommendations 3–5 (accelerate patches, modernize distribution, update disclosure policies) describe the new operational baseline for vulnerability management. See [frameworks/soc2.md](../frameworks/soc2.md).
- **Reasonable security standard:** These recommendations from the discoverer of the vulnerabilities may inform what courts and regulators consider "reasonable" in future enforcement actions. See [analysis/reasonable-security-baseline.md](../analysis/reasonable-security-baseline.md).

## Key data points

- 6 recommendations + incident response guidance
- "Experiment with language models for all security tasks you are doing manually today"
- Current frontier models find "high- and critical-severity vulnerabilities almost everywhere"
- Patch cycle compression: CVE-to-exploit window now measured in hours
- Legacy system contingency planning explicitly called out
- Alert volume will require automated triage and response

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
