# System Card Workpaper: Zero-Day Discovery

> Workpaper analyzing the [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD].
> Part of the [system card workpaper series](.). See the [workpaper index](README.md) for the full list.

## Summary

Mythos Preview discovered thousands of previously unknown high-severity vulnerabilities in foundational software — operating systems, browsers, media libraries, and more. Three marquee zero-days illustrate the capability: a 27-year-old OpenBSD TCP bug, a 16-year-old FFmpeg codec flaw that automated tools ran 5 million times without catching, and a memory corruption bug in a memory-safe virtual machine monitor. These findings are the primary evidence that the "reasonable security" baseline has shifted.

## Source material
- **System card section(s):** "Finding zero-day vulnerabilities," "And several thousand more"
- **PDF page range:** See 244-page PDF for additional technical detail [GLASSWING-CARD-PDF]

## Findings

### OpenBSD TCP SACK vulnerability (27 years old)

- **Type:** Denial of service through null-pointer dereference
- **Root cause:** Signed integer overflow in TCP SACK (Selective Acknowledgment) handling. Two-bug chain involving improper boundary checking and signed overflow.
- **Impact:** Remote attackers can crash OpenBSD hosts
- **Age:** 27 years in the codebase
- **Discovery cost:** Under $50 for the successful run; ~$20,000 for the full thousand-run campaign

### FFmpeg H.264 codec vulnerability (16 years old)

- **Type:** Out-of-bounds heap write via slice-counter integer mismatch
- **Root cause:** 16-bit table entries initialized with 32-bit counter values. Bug introduced in 2003, became a vulnerability in 2010 when slice counting changed.
- **Impact:** Heap corruption enabling potential code execution
- **Age:** 16 years as an exploitable vulnerability
- **Historical context:** Automated tools executed this code path approximately **5 million times** without catching the bug
- **Discovery cost:** ~$10,000 for several hundred runs

### Memory-safe virtual machine monitor — guest-to-host corruption

- **Type:** Memory corruption in unsafe code sections of an otherwise memory-safe VMM
- **Impact:** Malicious guest achieves out-of-bounds write to host process memory
- **Status:** Patched; no functional exploit demonstrated (the model could corrupt host memory but could not achieve full code execution)
- **Significance:** Demonstrates that "memory-safe" languages still have attack surface in their unsafe escape hatches

**SHA-3 commitment:** `b63304b28375c023abaa305e68f19f3f8ee14516dd463a72a2e30853`

### Aggregate findings

- **Thousands** of additional critical and high-severity vulnerabilities identified across foundational software
- 89% agreement rate between model severity assessment and expert human validators; 98% within one severity level (see [WP-01: Evaluation Methodology](evaluation-methodology.md))
- Every major operating system and web browser had vulnerabilities discovered
- Bugs ranged from subtle logic errors to extremely difficult-to-detect memory corruption

The human factor: *"Engineers at Anthropic with no formal security training have asked Mythos Preview to find remote code execution vulnerabilities overnight, and woken up the following morning to a complete, working exploit."*

## Governance implications

These findings are the core evidence for the "reasonable security baseline" shift documented in [analysis/reasonable-security-baseline.md](../analysis/reasonable-security-baseline.md):

- **SOC 2 CC3.2 (Risk Assessment):** If an AI can find a 27-year-old bug in hours, traditional "low" risk ratings for legacy code are no longer defensible. See [frameworks/soc2.md](../frameworks/soc2.md).
- **SOC 2 CC7.1 (Vulnerability Management):** Detection capabilities limited to known-CVE scanning miss what Mythos found. See [frameworks/soc2.md](../frameworks/soc2.md).
- **HIPAA §164.308(a)(1):** Risk analysis that doesn't account for AI-discoverable vulnerabilities in ePHI systems is arguably incomplete. See [frameworks/hipaa.md](../frameworks/hipaa.md).
- **HITRUST 07.d:** Technical vulnerability management may need to include AI-augmented discovery as a standard input. See [frameworks/hitrust.md](../frameworks/hitrust.md).

## Key data points

- 27-year-old OpenBSD bug — remote DoS via signed integer overflow in TCP SACK
- 16-year-old FFmpeg bug — automated tools ran it 5 million times without catching it
- Memory-safe VMM guest-to-host corruption — "memory-safe" is not exploit-proof
- Thousands of additional high/critical-severity vulns across foundational software
- Every major OS and browser had discoveries
- Non-security engineers found RCEs overnight using the model

## SHA-3 commitment hashes

| Target | Hash |
|--------|------|
| Memory-safe VMM | `b63304b28375c023abaa305e68f19f3f8ee14516dd463a72a2e30853` |

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
