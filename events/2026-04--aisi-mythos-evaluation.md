# Event: UK AI Security Institute Independently Confirms Mythos Preview Completes Multi-Stage Enterprise Attack Autonomously

## Date
2026-04-14

## Source
- [AISI-MYTHOS] [UK AISI — Our evaluation of Claude Mythos Preview's cyber capabilities](https://www.aisi.gov.uk/blog/our-evaluation-of-claude-mythos-previews-cyber-capabilities)

## What happened

The UK AI Security Institute published its independent evaluation of Claude Mythos Preview on April 14, finding it the first AI model to autonomously complete AISI's 32-step "The Last Ones" enterprise-network attack simulation end-to-end (3 of 10 attempts), with a 73% success rate on expert-level CTFs. No prior model had crossed the autonomous multi-stage enterprise-attack threshold. AISI explicitly warned that performance had not plateaued at 100 million tokens of inference budget.

> *"Two years ago, the best available models could barely complete beginner-level cyber tasks. Now, in controlled evaluations where Mythos Preview was explicitly directed and given network access to do so, we observed that it could execute multi-stage attacks on vulnerable networks and discover and exploit vulnerabilities autonomously — tasks that would take human professionals days of work."* — UK AISI [AISI-MYTHOS]

## Why this is the first independent government confirmation

Anthropic's own 244-page system card documented Mythos Preview's capabilities from internal testing. The AISI evaluation is the first assessment by an independent government body — distinct from any evaluation Anthropic controlled. AISI conducted its evaluation as an advisory participant in the Glasswing program, making it the closest existing institution to the independent third-party oversight body Anthropic called for on April 7. It remains formally advisory rather than gatekeeping: AISI's role is to evaluate and publish, not to approve or block deployment.

The evaluation flowed directly into policy action. Bank of England Governor Andrew Bailey named Mythos by name in a Columbia University speech on April 15. UK bank access was confirmed via Bloomberg on April 16. Mythos Preview reached regulated European financial institutions within nine more days. AISI's finding provided the technical foundation for that expansion — which proceeded without SR 11-7 model-risk-management intake, PRA model validation, or ECB supervisory review.

## Benchmark saturation as a governance signal

AISI's explicit warning that performance had not plateaued at 100 million tokens of inference budget is a material governance finding: models evaluated as "acceptable" under 2025 evaluation thresholds may be operating at full attack-chain autonomy under 2026 compute budgets. AISI is declaring that its own benchmarks are saturating. Any compliance posture calibrated against prior-generation model evaluations is structurally outdated.

## Who's affected

Every organization building defensive AI programs against benchmarks calibrated to pre-Mythos capability levels. Regulators and model-risk-management teams receiving Glasswing access whose intake processes assume an independent safety evaluation already occurred — it has, but AISI's role was advisory, not gatekeeping, and the evaluation confirmed deployment was already underway before the results were published.

## Key links
- [UK AISI evaluation (primary)](https://www.aisi.gov.uk/blog/our-evaluation-of-claude-mythos-previews-cyber-capabilities) [AISI-MYTHOS]
- [Project Glasswing](2026-04--project-glasswing.md) — capability and governance context
- [SANS/CSA/OWASP Mythos-Ready Briefing](2026-04--sans-csa-owasp-mythos-briefing.md) — practitioner response building on AISI findings
- [Disclosure and Deployment Arrived Together](../analysis/disclosure-and-deployment.md) — analysis of why the advisory-not-gatekeeping distinction matters

---

*Added: 2026-04-22*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
