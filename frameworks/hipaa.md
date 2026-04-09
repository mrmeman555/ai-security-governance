# HIPAA — AI Agent Impact Tracker

Living document tracking how AI agent developments affect HIPAA Security Rule [HIPAA-SEC] compliance.

---

## §164.308(a)(1) — Risk Analysis

**Triggered by:** [Project Glasswing](../events/2026-04--project-glasswing.md) (April 2026)

**Current language:** Requires covered entities to "conduct an accurate and thorough assessment of the potential risks and vulnerabilities to the confidentiality, integrity, and availability of electronic protected health information."

**Gap/finding:** If AI can find zero-day vulnerabilities in the software that stores and transmits ePHI — and those vulnerabilities have existed for decades undetected — then a HIPAA risk analysis that doesn't account for this class of risk is arguably incomplete.

**Healthcare-specific concern:** Healthcare organizations are the #1 target for ransomware. The software they depend on (OS kernels, browsers, media processing libraries like FFmpeg) is exactly where Mythos found its most critical vulnerabilities. A dental clinic running unpatched FFmpeg for imaging software now has a named, documented risk that didn't exist in any database last week. See [WP-02: Zero-Day Discovery](../system-card/zero-day-discovery.md) for the FFmpeg and other foundational software findings.

This seems like the kind of thing that comes up in the next risk assessment cycle — not as a scare tactic, but as a genuine update to the threat landscape.

---

## BAA Requirements for Managed Harnesses

**Triggered by:** [Managed Agents Beta](../events/2026-04--managed-agents-beta.md) (April 2026)

**Gap/finding:** If a managed AI agent harness processes ePHI, Business Associate Agreement requirements apply to the harness provider's infrastructure. This is a new consideration for organizations deploying AI agents in healthcare contexts — the harness provider (not just the model provider) needs to be covered under a BAA.

---

*Last updated: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
