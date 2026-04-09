# Changelog

All notable updates to this repository.

---

## 2026-04-09 — Reground everything in verbatim sources

- Created `system-card-summary.md` — single document consolidating all 8 system card workpapers into verbatim quotes with `[GLASSWING-CARD]` citations
- Deleted 8 individual workpapers (`system-card/evaluation-methodology.md`, `zero-day-discovery.md`, `exploit-development.md`, `logic-and-crypto-vulns.md`, `reverse-engineering.md`, `alignment-assessment.md`, `defender-recommendations.md`, `strategic-context.md`) and `system-card/README.md`
- Deleted `templates/system-card-workpaper.md`
- Rewrote `analysis/agent-harness-architecture.md` — quote-driven: Claude Code leak source, convergence table with sourced star counts, Managed Agents concept table from Anthropic docs
- Rewrote `analysis/harness-governance-gap.md` — removed Mexico AI incident (unverified), removed "Bottom Line" editorial section, kept system card circumvention evidence as verbatim quotes
- Rewrote `analysis/reasonable-security-baseline.md` — quoted FTC v Wyndham holding, verbatim system card cost data, cited CISA budget numbers from MeriTalk/Cybersecurity Dive; removed unsourced cyber insurance and PCAOB/AICPA paragraphs, removed editorial predictions
- Updated `events/2026-04--project-glasswing.md` links to point to `system-card-summary.md`
- Updated README: replaced 8-link workpapers section with single link to `system-card-summary.md`
- Updated SOURCES.md: replaced workpaper paths in cited-in lines; marked MEXICO-AI-INCIDENT as removed
- Rationale: every claim should trace to a verbatim quote from a primary source — no editorial interpretation mixed with sourced facts

---

## 2026-04-09 — Simplify repo to index + analysis

- Deleted `controls/repo-governance.md` (aspirational controls the repo didn't enforce)
- Deleted `RISKS.md` (risk register referencing removed controls)
- Simplified README disclaimer and removed risk table, controls section
- Cleaned up SOURCES.md references to removed governance controls

---

## 2026-04-09 — Remove framework gap claims (cooling-off period)

- Deleted 5 framework trackers: `frameworks/soc2.md`, `frameworks/hitrust.md`, `frameworks/hipaa.md`, `frameworks/iso42001.md`, `frameworks/nist-ai-rmf.md`
- Deleted `controls/harness-risk-matrix.md` (SOC 2-mapped control matrix)
- Removed "Governance Implications" sections from all 8 system card workpapers
- Removed "Framework impact" sections from all 6 event briefs
- Removed specific clause/control references (CC3.2, CC4.1, CC6.1, CC7.1, A.7, MEASURE 2.6, §164.308, 07.d) from analysis pieces
- Kept narrative analysis (harness governance gap thesis, reasonable security baseline, FTC precedent, Cranium, Mythos evidence)
- Updated README, SOURCES.md, event brief template
- Rationale: honoring RR-10 (temporal compression bias) — framework gap claims were interpretive judgments written in a single session without cooling-off review

---

## 2026-04-08 — System card workpapers

- Created `system-card/` directory with 8 self-contained workpapers analyzing the Mythos Preview system card
- WP-01: Evaluation Methodology — scaffold, 5-tier severity ladder, ~7K entry points, cost data, responsible disclosure
- WP-02: Zero-Day Discovery — OpenBSD, FFmpeg, memory-safe VMM, aggregate findings
- WP-03: Exploit Development — FreeBSD NFS RCE, Linux kernel chains, Firefox 147, browser JIT, two detailed N-day case studies (CVE-2024-47711 one-bit write, one-byte read to root under HARDENED_USERCOPY)
- WP-04: Logic & Crypto Vulnerabilities — auth bypasses, TLS/AES-GCM/SSH weaknesses, web app vulns, kernel logic bugs
- WP-05: Reverse Engineering — closed-source binary analysis, firmware rooting, proprietary browser/OS analysis
- WP-06: Alignment Assessment — moved from Glasswing event brief; sandbox escape, credential fishing, grader hacking, SAE interpretability, SHADE-Arena, RSP v3.0
- WP-07: Defender Recommendations — Anthropic's 6 recommendations for security teams + incident response automation
- WP-08: Strategic Context — 20-year equilibrium disruption, SHA-3/post-quantum parallels, no plateau expected
- Created workpaper template at `templates/system-card-workpaper.md`
- Slimmed Glasswing event brief — moved alignment assessment and detailed vulnerability findings to workpapers; event brief now focuses on event context + governance impact with links to workpapers
- Updated `analysis/harness-governance-gap.md` to reference alignment workpaper (WP-06) instead of event brief
- Updated all 5 framework trackers (SOC 2, ISO 42001, NIST AI RMF, HIPAA, HITRUST) with workpaper cross-references
- Updated README with new System Card Workpapers section in Contents
- Updated SOURCES.md cited-in lines for GLASSWING-CARD and GLASSWING-CARD-PDF

---

## 2026-04-08 — System card deep integration (244-page PDF)

- Integrated full alignment assessment from Mythos system card PDF (Sections 4.1–4.5)
- Added alignment assessment section to Glasswing event brief: sandbox escape, /proc credential fishing, safety classifier circumvention, grader hacking, sandbagging, white-box interpretability findings, SHADE-Arena stealth rates, destructive action rates, Vending-Bench Arena aggressive behaviors, RSP v3.0 context
- Added "Model Itself Proved the Gap" section to harness-governance-gap.md with 4 documented harness-level circumvention episodes from the system card
- Updated ISO 42001 tracker: Annex A.7 alignment evidence (permission gate circumvention)
- Updated NIST AI RMF tracker: MEASURE 2.6 alignment evidence (white-box monitoring, grader hacking)
- Updated SOC 2 tracker: CC6.1 alignment evidence (/proc credential fishing, tool restriction evasion)
- Added system card PDF as source [GLASSWING-CARD-PDF] to SOURCES.md
- Added PDF link to README key links table

---

## 2026-04-08 — Glasswing day-after updates

- Added Linux kernel autonomous exploit chaining (from 244-page system card)
- Added day-after fallout: NBC/WIRED/ZDNET coverage, stock market surge, Section 702 FISA push
- Added Pentagon FY2027 budget: AI warfare expansion + $707M CISA cut
- Updated Glasswing event brief, SOC 2 framework tracker, reasonable-security-baseline analysis, README timeline
- Added Linux Foundation and Apache Software Foundation as named donation recipients

---

## 2026-04-08 — Restructure: ai-security-governance → ai-governance-watch

**What changed:**
- Restructured from 4 flat files into a professional intelligence tracker format
- Created `events/` directory with 6 templated event briefs
- Created `analysis/` directory with 3 synthesis pieces
- Created `frameworks/` directory with 5 living framework trackers (SOC 2, HITRUST, HIPAA, ISO 42001, NIST AI RMF)
- Created `controls/` directory (harness risk matrix moved here)
- Created `templates/` with standardized event-brief and framework-update templates
- Rewrote README with contents, methodology, and causal timeline
- Added CHANGELOG
- Renamed repo from `ai-security-governance` to `ai-governance-watch`
- Removed old flat files (`agent-harnesses.md`, `glasswing-brief.md`, `harness-risk-matrix.md` at root)

**Why:** The repo evolved from a one-time share into an ongoing research tracker. The flat structure couldn't scale. The new structure supports adding events and accumulating framework findings over time.

---

## 2026-04-08 — Content additions

- Added Claude Managed Agents (beta April 2026) as fourth harness example
- Added Anthropic v. OpenCode legal action to timeline
- Added DMCA fallout details (8,100 repos accidentally taken down)
- Added Claw Code with GitHub star numbers (50K in 2 hours)
- Added OpenClaw growth numbers (100K in 2 days, 250K in 60 days)
- Added Anthropic Glasswing quote with source attribution
- Rewrote timeline as causal narrative (events lead into each other)
- Integrated Google Deep Research findings: ISO 42001 gaps (8.2, A.5, A.7), NIST AI RMF gaps (GOVERN 2.1, MEASURE 2.6), Mexican government incident, FTC v. Wyndham precedent, cyber liability insurance trends, PCAOB/AICPA audit independence tension
- Created harness risk & control matrix (SOC 2 mapped)
- Softened prescriptive tone throughout
- Sourced every row of the timeline section

---

## 2026-04-08 — Initial publication

- Created repository with README, agent-harnesses.md, glasswing-brief.md
- Published as `ai-security-governance`
- Added attribution disclaimer
