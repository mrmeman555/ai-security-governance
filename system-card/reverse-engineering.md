# System Card Workpaper: Reverse Engineering

> Workpaper analyzing the [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD].
> Part of the [system card workpaper series](.). See the [workpaper index](README.md) for the full list.

## Summary

Mythos Preview can analyze closed-source, stripped binaries — reconstructing plausible source code and then finding vulnerabilities in the reconstruction. It has identified exploitable flaws in proprietary browsers, operating systems, and firmware. This capability fundamentally undermines the assumption that closed-source code is harder to attack than open-source code.

## Source material
- **System card section(s):** "Reverse engineering"
- **PDF page range:** See 244-page PDF [GLASSWING-CARD-PDF]

## Findings

### Capability

Mythos Preview takes closed-source stripped binaries, **reconstructs plausible source code**, then combines the reconstructed code with the original binary to identify vulnerabilities. The system card states: *"We've used these capabilities to find vulnerabilities and exploits in closed-source browsers and operating systems."*

### Verified results

- **Remote denial-of-service attacks** capable of remotely disabling servers
- **Firmware vulnerabilities** enabling smartphone rooting
- **Local privilege escalation** exploit chains on desktop operating systems

### Testing conditions

All testing occurred **offline**, following corresponding bug bounty programs. None of the discovered vulnerabilities have been patched or made public at time of publication.

### Significance

This is not just "better fuzzing." The model is performing **semantic analysis of machine code** — understanding what the binary does, inferring what it was meant to do, and finding where the two diverge. This is work that previously required elite reverse engineers working for weeks or months per target.

For organizations that rely on proprietary software — which is most enterprises — the security assumption has been that closed-source code has a higher barrier to attack. That assumption is no longer valid when an AI can reconstruct the source and find bugs in it overnight.

## Governance implications

- **All frameworks — "security through obscurity" assumption:** Organizations cannot rely on code being closed-source as a security factor in risk assessments. This affects how vendor risk is evaluated across SOC 2, HITRUST, and ISO 42001.
- **SOC 2 CC3.2 (Risk Assessment):** Vendor risk assessments that rate proprietary software as "lower risk" because it's closed-source need re-evaluation. See [frameworks/soc2.md](../frameworks/soc2.md).
- **HITRUST 01.v (Information Access Restriction):** The assumption that firmware and embedded systems are harder to attack informs access restriction risk calculus. That assumption is weakened. See [frameworks/hitrust.md](../frameworks/hitrust.md).
- **Supply chain risk:** Firmware rooting capability means the model can attack the hardware layer, not just the software layer. This extends the threat surface below the operating system.

## Key data points

- Can reconstruct source code from stripped, closed-source binaries
- Found exploitable vulnerabilities in proprietary browsers, OSes, and firmware
- Results include remote DoS, firmware rooting, and local privilege escalation chains
- All testing performed offline, following bug bounty programs
- None of the discovered vulnerabilities patched at publication

## SHA-3 commitment hashes

| Target | Hash |
|--------|------|
| Closed-source OS / remote DoS | `d4f233395dc386ef722be4d7d4803f2802885abc4f1b45d370dc9f97` |
| Smartphone firmware / rooting | `f4adbc142bf534b9c514b5fe88d532124842f1dfb40032c982781650` |

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
