# Sources

> Central bibliography for all claims in this repository.
> Referenced from artifacts using `[CITATION-KEY]` markers.
> Complies with [RC-01 (Unsourced Claims)](controls/repo-governance.md) and [RC-03 (Link Rot)](controls/repo-governance.md).
>
> Last updated: 2026-04-08

---

## Frameworks & Standards

**[ISO-42001]** ISO/IEC 42001:2023 — Information technology — Artificial intelligence — Management system.
International Organization for Standardization, December 2023.
https://www.iso.org/standard/42001
Referenced sections: 8.2 (AI Risk Assessment), 8.4 (AI System Impact Assessment), Annex A.5 (Data & Information), Annex A.7 (Data for AI Systems).
*Note: Clause 8.4 covers impact assessment (not 8.2 as sometimes cited). Annex numbering should be verified against the purchased standard — secondary sources vary.*
See also: [AWS blog on ISO 42001](https://aws.amazon.com/blogs/security/ai-lifecycle-risk-management-iso-iec-420012023-for-ai-governance/) | [Bastion guide to Annex A](https://bastion.tech/learn/iso42001/annex-a-controls/)
*Cited in: frameworks/iso42001.md, analysis/harness-governance-gap.md, README.md*

**[NIST-AI-RMF]** NIST AI Risk Management Framework (AI RMF 1.0). NIST AI 100-1.
National Institute of Standards and Technology, January 2023.
https://www.nist.gov/itl/ai-risk-management-framework
Full document: https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf
Playbook: https://airc.nist.gov/airmf-resources/playbook/
Referenced sections: GOVERN 2.1 (Roles and Responsibilities), MEASURE 2.6 (Security & Resilience), MAP 3.1 (Third-Party AI Risks).
*Note: Exact subcategory text is in Tables 1-4, pp. 25-32 of NIST AI 100-1.*
*Cited in: frameworks/nist-ai-rmf.md, analysis/harness-governance-gap.md, README.md*

**[SOC2-TSC]** 2017 Trust Services Criteria for Security, Availability, Processing Integrity, Confidentiality, and Privacy (With Revised Points of Focus — 2022).
AICPA & CIMA, Assurance Services Executive Committee (ASEC).
https://www.aicpa-cima.com/resources/download/2017-trust-services-criteria-with-revised-points-of-focus-2022
Referenced controls: CC2.1 (COSO Principle 13 — Communication), CC3.2 (COSO Principle 7 — Risk Assessment), CC4.1 (COSO Principle 16 — Monitoring), CC6.1 (Logical Access), CC6.3 (Role-Based Access), CC7.1 (Vulnerability Management), CC7.2 (Security Monitoring), A1.2 (Availability — Recovery).
*Cited in: frameworks/soc2.md, controls/harness-risk-matrix.md, analysis/reasonable-security-baseline.md, README.md*

**[HITRUST-CSF]** HITRUST Common Security Framework.
HITRUST Alliance.
https://hitrustalliance.net/product-tool/hitrust-csf/
Referenced controls: 07.d (Technical Vulnerability Management), 01.v (Information Access Restriction).
*Cited in: frameworks/hitrust.md, analysis/reasonable-security-baseline.md*

**[HITRUST-AI]** HITRUST AI Security Assessment — 51 AI-specific controls.
HITRUST Alliance, late 2024.
https://hitrustalliance.net/assessments-and-certifications/aisecurityassessment
*Cited in: frameworks/hitrust.md, analysis/harness-governance-gap.md, Steadfast Business Model*

**[HITRUST-AI-ISO]** "HITRUST AI Security Assessment: A Path to ISO 42001."
Schellman (blog), 2025.
https://www.schellman.com/blog/ai-services/hitrust-ai-security-assessment-path-to-iso-42001
*Cited in: frameworks/hitrust.md*

**[HIPAA-SEC]** HIPAA Security Rule — 45 C.F.R. Part 164, Subpart C.
U.S. Department of Health and Human Services.
Overview: https://www.hhs.gov/hipaa/for-professionals/security/index.html
Risk Analysis guidance: https://www.hhs.gov/hipaa/for-professionals/security/guidance/guidance-risk-analysis/index.html
Regulation text: https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-C/section-164.308
Referenced section: §164.308(a)(1)(ii)(A) — Risk Analysis requirement.
*Cited in: frameworks/hipaa.md, analysis/reasonable-security-baseline.md*

**[CMMC]** Cybersecurity Maturity Model Certification (CMMC 2.0). 32 C.F.R. Part 170.
U.S. Department of Defense, Chief Information Officer. Final rule effective December 16, 2024.
Official page: https://dodcio.defense.gov/CMMC/
Federal Register: https://www.federalregister.gov/documents/2024/10/15/2024-22905/cybersecurity-maturity-model-certification-cmmc-program
Three levels: Level 1 (17 practices, self-assessment), Level 2 (NIST SP 800-171, third-party assessment), Level 3 (NIST SP 800-172).
*Cited in: Steadfast Business Model*

---

## Case Law & Legal Precedent

**[FTC-WYNDHAM]** *Federal Trade Commission v. Wyndham Worldwide Corp.*, 799 F.3d 236 (3d Cir. 2015).
Third Circuit upheld FTC authority under Section 5 (unfairness prong) to enforce data security standards. Key holding: companies have "fair notice" that failing to maintain reasonable security can constitute an unfair practice. Applied cost-benefit analysis framework for reasonableness. Three data breaches, $10M+ in fraud.
FTC case page: https://www.ftc.gov/legal-library/browse/cases-proceedings/1023142-x120032-wyndham-worldwide-corporation
FTC blog on ruling: https://www.ftc.gov/business-guidance/blog/2015/08/third-circuit-rules-ftc-v-wyndham-case
Full opinion (Justia): https://law.justia.com/cases/federal/appellate-courts/ca3/14-3514/14-3514-2015-08-24.html
Harvard Law Review analysis: https://harvardlawreview.org/print/vol-129/ftc-v-wyndham-worldwide-corp/
*Cited in: analysis/reasonable-security-baseline.md*

**[DMCA-ANTHROPIC]** GitHub DMCA Takedown Notice — Anthropic, March 31, 2026.
Original notice: https://github.com/github/dmca/blob/master/2026/03/2026-03-31-anthropic.md
Retraction notice: https://github.com/github/dmca/blob/master/2026/04/2026-04-01-anthropic-retraction.md
Overbroad notice disabled ~8,100 repos (entire fork network). Retracted to 1 repo (`nirholas/claude-code`) and 96 forks. Boris Cherny (Anthropic head of Claude Code) called it "a plain developer error" — missing `.npmignore` entry for Bun-generated source maps.
See also: [WinBuzzer](https://winbuzzer.com/2026/04/02/anthropic-dmca-blunder-took-down-8100-github-repos-xcxwbn/)
*Cited in: events/2026-03--claude-code-leak.md, README.md*

---

## Events & Announcements

**[OPENCLAW]** OpenClaw — first popular open-source agent harness.
Created by @steipete (Peter Steinberger). Late January 2026.
https://github.com/openclaw/openclaw
100K GitHub stars in 2 days, 210K in 10 days, 250K in 60 days. Fastest-growing repo in GitHub history.
*Cited in: events/2026-01--openclaw-viral.md, analysis/agent-harness-architecture.md, README.md*

**[OPENCLAW-MEDIUM-210K]** "210,000 GitHub Stars in 10 Days — What OpenClaw's Architecture Teaches Us."
Michael Lanham, Medium, February 2026.
https://medium.com/@Micheal-Lanham/210-000-github-stars-in-10-days-what-openclaws-architecture-teaches-us-about-building-personal-ai-dae040fab58f
*Cited in: events/2026-01--openclaw-viral.md*

**[OPENCLAW-MEDIUM-REACT]** "OpenClaw Just Beat React's 10-Year GitHub Record in 60 Days."
Aftab, Medium, March 2026.
https://medium.com/@aftab001x/openclaw-just-beat-reacts-10-year-github-record-in-60-days-now-nobody-knows-what-to-do-with-it-937b8f370507
*Cited in: events/2026-01--openclaw-viral.md*

**[OPENCLAW-STARS]** Star History — OpenClaw surpasses React.
https://www.star-history.com/blog/openclaw-surpasses-react-most-starred-software
*Cited in: events/2026-01--openclaw-viral.md*

**[ANTHROPIC-V-OPENCODE]** Anthropic threatens legal action against OpenCode.
February-March 2026. Anthropic updated ToS on Feb 19, 2026 to ban subscription OAuth tokens in third-party tools. OpenCode maintainer Dax Raad merged removal of all Claude integration on March 19, 2026 (PR #18186).
- The Register (Feb 20): https://www.theregister.com/2026/02/20/anthropic_clarifies_ban_third_party_claude_access/
- Rida Kaddir analysis: https://ridakaddir.com/blog/post/did-anthropic-kill-opencode-claude-subscription-ban
- The Agent Times: https://theagenttimes.com/articles/anthropic-forces-opencode-to-strip-claude-integration-after--96edcc05
- Hacker News: https://news.ycombinator.com/item?id=47444748
*Cited in: events/2026-03--anthropic-v-opencode.md, README.md*

**[CLAUDE-LEAK-TECHCRUNCH]** "Anthropic took down thousands of repos trying to yank its leaked source code — a move the company says was an accident."
TechCrunch, April 1, 2026.
https://techcrunch.com/2026/04/01/anthropic-took-down-thousands-of-github-repos-trying-to-yank-its-leaked-source-code-a-move-the-company-says-was-an-accident/
*Cited in: events/2026-03--claude-code-leak.md*

**[CLAUDE-LEAK-FUTURISM]** "Anthropic Suddenly Cares About Intellectual Property."
Futurism, April 2026.
https://futurism.com/artificial-intelligence/anthropic-suddenly-cares-about-intellectual-property-claude-leak
*Cited in: events/2026-03--claude-code-leak.md*

**[CLAUDE-LEAK-ANALYSIS]** Full leak analysis — Claude Code source architecture.
claudefa.st, April 2026.
https://claudefa.st/blog/guide/mechanics/claude-code-source-leak
*Cited in: events/2026-03--claude-code-leak.md*

**[CLAW-CODE]** Claw Code — clean-room agent harness rewrite.
Sigrid Jin, March 31, 2026. 50K stars in 2 hours.
https://github.com/ultraworkers/claw-code
*Cited in: events/2026-03--claw-code-rewrite.md, analysis/agent-harness-architecture.md, README.md*

**[CLAW-CODE-SITE]** Claw Code official site.
https://claw-code.codes/
*Cited in: events/2026-03--claw-code-rewrite.md*

**[CLAW-CODE-MEDIUM]** "Claw Code killed Claude Code?"
Medium, April 2026.
https://medium.com/data-science-in-your-pocket/claw-code-killed-claude-code-02aab80b0838
*Cited in: events/2026-03--claw-code-rewrite.md*

**[MANAGED-AGENTS]** Claude Managed Agents — Beta launch.
Anthropic, April 1, 2026. Beta header: `managed-agents-2026-04-01`. Pricing: model usage + $0.08/agent runtime hour.
- Docs: https://platform.claude.com/docs/en/managed-agents/overview
- Engineering blog: https://www.anthropic.com/engineering/managed-agents
- The New Stack: https://thenewstack.io/with-claude-managed-agents-anthropic-wants-to-run-your-ai-agents-for-you/
- SiliconANGLE: https://siliconangle.com/2026/04/08/anthropic-launches-claude-managed-agents-speed-ai-agent-development/
*Cited in: events/2026-04--managed-agents-beta.md, README.md*

**[MANAGED-AGENTS-API]** Claude Managed Agents — API Reference.
Anthropic.
https://platform.claude.com/docs/en/api/beta/sessions
*Cited in: events/2026-04--managed-agents-beta.md*

**[GLASSWING]** Project Glasswing — Anthropic announcement.
Anthropic, April 7, 2026.
https://www.anthropic.com/glasswing
*Cited in: events/2026-04--project-glasswing.md, analysis/reasonable-security-baseline.md, Follow-Up Email, README.md*

**[GLASSWING-CARD]** Mythos Preview Capabilities Assessment (System Card) — web version.
Anthropic, April 7, 2026. 244 pages.
https://red.anthropic.com/2026/mythos-preview/
Key findings: 27-year-old OpenBSD vuln, 16-year-old FFmpeg vuln, 17-year-old FreeBSD vuln (CVE-2026-4747), Firefox 147 (181 exploits vs. 2 for Opus 4.6), OSS-Fuzz (595 crashes, 10 control flow hijacks). Cost: $50–$2,000/exploit.
*Cited in: events/2026-04--project-glasswing.md, analysis/reasonable-security-baseline.md, frameworks/soc2.md, system-card/evaluation-methodology.md, system-card/zero-day-discovery.md, system-card/exploit-development.md, system-card/logic-and-crypto-vulns.md, system-card/reverse-engineering.md, system-card/alignment-assessment.md, system-card/defender-recommendations.md, system-card/strategic-context.md, README.md*

**[GLASSWING-CARD-PDF]** System Card: Claude Mythos Preview — full 244-page PDF.
Anthropic, April 7, 2026.
https://www-cdn.anthropic.com/8b8380204f74670be75e81c820ca8dda846ab289.pdf
Contains full alignment assessment (Section 4): sandbox escape, /proc credential fishing, safety classifier circumvention, grader hacking, sandbagging, white-box interpretability (SAE features for "strategic manipulation," "security bypass," "guilt and shame"), SHADE-Arena stealth rates, destructive action rates. RSP v3.0 context. Autonomy threat model 1 applicable. Anthropic: "We find it alarming that the world looks on track to proceed rapidly to developing superhuman systems without stronger mechanisms in place for ensuring adequate safety."
*Cited in: events/2026-04--project-glasswing.md, analysis/harness-governance-gap.md, frameworks/iso42001.md, frameworks/nist-ai-rmf.md, frameworks/soc2.md, system-card/evaluation-methodology.md, system-card/zero-day-discovery.md, system-card/exploit-development.md, system-card/logic-and-crypto-vulns.md, system-card/reverse-engineering.md, system-card/alignment-assessment.md, system-card/defender-recommendations.md, system-card/strategic-context.md*

**[GLASSWING-CROWDSTRIKE]** "CrowdStrike: Founding Member of Anthropic Mythos Frontier Model to Secure AI."
CrowdStrike blog, April 7, 2026.
https://www.crowdstrike.com/en-us/blog/crowdstrike-founding-member-anthropic-mythos-frontier-model-to-secure-ai/
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-CYBERSCOOP]** "Project Glasswing: Anthropic AI Open Source Software Vulnerabilities."
CyberScoop, April 7, 2026.
https://cyberscoop.com/project-glasswing-anthropic-ai-open-source-software-vulnerabilities/
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-FORTUNE]** "Anthropic Claude Mythos Model Project Glasswing Cybersecurity."
Fortune, April 7, 2026.
https://fortune.com/2026/04/07/anthropic-claude-mythos-model-project-glasswing-cybersecurity/
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-NBC]** "Anthropic Project Glasswing: Mythos Preview Claude Gets Limited Release."
NBC News, April 8, 2026.
https://www.nbcnews.com/tech/security/anthropic-project-glasswing-mythos-preview-claude-gets-limited-release-rcna267234
*Cited in: events/2026-04--project-glasswing.md, README.md*

**[GLASSWING-TECHCRUNCH]** "Anthropic Mythos AI Model Preview Security."
TechCrunch, April 7, 2026.
https://techcrunch.com/2026/04/07/anthropic-mythos-ai-model-preview-security/
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-AXIOS]** "Mythos System Card."
Axios, April 8, 2026.
https://www.axios.com/2026/04/08/mythos-system-card
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-RISK-REPORT]** Anthropic — Claude Mythos Preview Risk Report.
Anthropic, April 2026.
https://www.anthropic.com/claude-mythos-preview-risk-report
*Cited in: events/2026-04--project-glasswing.md*

**[GLASSWING-WIRED]** WIRED coverage of Project Glasswing.
WIRED, April 8, 2026.
URL pending — referenced in events/2026-04--project-glasswing.md without direct link.
*Cited in: events/2026-04--project-glasswing.md, README.md*

**[GLASSWING-ZDNET]** ZDNET coverage of Project Glasswing.
ZDNET, April 8, 2026.
URL pending — referenced in events/2026-04--project-glasswing.md without direct link.
*Cited in: events/2026-04--project-glasswing.md, README.md*

**[GLASSWING-INSIDE-DEFENSE]** Inside Defense coverage of Project Glasswing.
Inside Defense, April 8, 2026.
URL pending — referenced in events/2026-04--project-glasswing.md without direct link.
*Cited in: events/2026-04--project-glasswing.md*

**[FY2027-BUDGET]** Pentagon FY2027 Budget Proposal — AI expansion and CISA cuts.
U.S. Department of Defense / White House, April 7, 2026.
- MeriTalk (CISA $707M cut): https://cdn.meritalk.com/articles/trump-fy2027-budget-cuts-cisa-by-707m-reduces-st-agencies/
- Cybersecurity Dive: https://www.cybersecuritydive.com/news/cisa-white-house-budget-fy27/816615/
- Vision Times ($1.5T defense): https://www.visiontimes.com/2026/04/04/white-house-proposes-1-5-trillion-defense-budget-for-fy2027-cuts-73-billion-in-domestic-spending.html
Proposes $1.5T defense spending (42% YoY increase), cuts CISA by $707M (from ~$2.9B to ~$2.4B).
*Cited in: events/2026-04--project-glasswing.md, analysis/reasonable-security-baseline.md, README.md*

**[FISA-702]** Section 702 FISA Renewal — national security officials urge renewal as Glasswing amplifies cyber threat narrative.
April 2026. 702 sunsets April 20, 2026 per 2024 RISAA extension.
- Nextgov (former officials urge renewal): https://www.nextgov.com/policy/2026/04/former-national-security-officials-urge-congress-renew-section-702-expiration/412703/
- Nextgov (Glasswing raises questions for cyber ops): https://www.nextgov.com/cybersecurity/2026/04/anthropics-glasswing-initiative-raises-questions-us-cyber-operations/412721/
- Brookings (reauthorization path unclear): https://www.brookings.edu/articles/a-key-intelligence-law-expires-in-april-and-the-path-for-reauthorization-is-unclear/
*Note: The Glasswing/702 connection is editorial adjacency in the same news cycle, not a single article explicitly citing Glasswing as justification for renewal.*
*Cited in: events/2026-04--project-glasswing.md, README.md*

---

## Industry Analysis

**[INNOVAIDEN-GLASSWING]** "Project Glasswing Cybersecurity Assessment Baseline."
Innovaiden, April 2026.
https://www.innovaiden.com/insights/project-glasswing-cybersecurity-assessment-baseline
Estimates 12-18 month capability gap before Mythos-class models are broadly accessible.
*Cited in: events/2026-04--project-glasswing.md, analysis/reasonable-security-baseline.md, README.md*

**[WILLISON-GLASSWING]** Simon Willison — Glasswing analysis.
Simon Willison, April 7, 2026.
https://simonwillison.net/2026/Apr/7/project-glasswing/
*Cited in: analysis/reasonable-security-baseline.md*

---

## Products & Platforms

**[CRANIUM]** Cranium AI — AI governance platform.
https://cranium.ai/
Products: DetectAI (shadow AI discovery), AgentSensor (agent detection), ComplianceAgent (automated compliance), Arena (adversarial red teaming), AI Cards (AI Bills of Materials).
*Cited in: analysis/harness-governance-gap.md, Follow-Up Email, README.md*

**[VANTA]** Vanta — GRC automation for SOC 2, HIPAA, ISO 27001.
https://www.vanta.com/
*Cited in: Steadfast Business Model*

**[DRATA]** Drata — GRC automation for SOC 2, HIPAA, ISO 27001.
https://drata.com/
*Cited in: Steadfast Business Model*

**[SPRINTO]** Sprinto — GRC automation for SOC 2, HIPAA, ISO 27001.
https://sprinto.com/
*Cited in: Steadfast Business Model*

**[MASTERMIND-42001]** Mastermind ISO 42001 Lead Auditor Certification Course.
Mastermind Assurance. Instructor: David Forman. First certification body accredited to issue ISO/IEC 42001 certificates (July 2024).
https://learn.mastermindassurance.com/products/courses/iso-42001-lead-auditor
Company: https://mastermindassurance.com/
*Cited in: Follow-Up Email*

---

## GitHub Repositories

**[REPO-OPENCLAW]** OpenClaw — open-source agent harness.
https://github.com/openclaw/openclaw
247K+ stars (as of April 2026).
*Cited in: events/2026-01--openclaw-viral.md, README.md*

**[REPO-CLAW-CODE]** Claw Code — clean-room harness rewrite (Rust/Python).
https://github.com/ultraworkers/claw-code
50K+ stars. Independently audited.
*Cited in: events/2026-03--claw-code-rewrite.md, README.md*

**[REPO-CLAUDE-LEAK]** Claude Code leaked source (DMCA in progress).
https://github.com/codeaashu/claude-code
*Cited in: events/2026-03--claude-code-leak.md, README.md*

**[REPO-CLAURST]** Claurst — clean-room Rust rewrite of Claude Code.
https://github.com/Kuberwastaken/claurst
*Cited in: events/2026-03--claude-code-leak.md, README.md*

**[REPO-LEAK-COLLECTION]** Collection of Claude Code source code analysis.
https://github.com/chauncygu/collection-claude-code-source-code
*Cited in: events/2026-03--claude-code-leak.md*

**[REPO-AI-SEC-GOV]** AI Security Governance — Aaron Reveley.
https://github.com/mrmeman555/ai-security-governance
*Cited in: Follow-Up Email*

---

## Pending Sources

The following sources are referenced in artifacts but lack verified URLs. Per [RC-03](controls/repo-governance.md), enough context is provided to locate them if links break.

| Citation Key | What's Needed | Status |
|-------------|---------------|--------|
| [GLASSWING-WIRED] | WIRED article on Glasswing, April 8, 2026 | Not found — WIRED may not have published dedicated coverage |
| [GLASSWING-ZDNET] | ZDNET article on Glasswing, April 8, 2026 | Not found — ZDNET may not have published dedicated coverage |
| [GLASSWING-INSIDE-DEFENSE] | Inside Defense article on Glasswing, April 8, 2026 | Paywalled — digest listing confirms coverage: https://insidedefense.com/insider/insider-daily-digest-april-8-2026 |
| [STEIPETE-PSPDFKIT] | PSPDFKit exit value (Peter Steinberger) | **Correction: EUR 100M / ~$116M USD (Insight Partners, Oct 2021), not $800M.** [TechCrunch](https://techcrunch.com/2021/10/01/pspdfkit-raises-116m-its-first-outside-money-now-nearly-1b-people-use-apps-powered-by-its-collaboration-signing-and-markup-tools/) |
| [MEXICO-AI-INCIDENT] | Claude-based agents used against Mexican gov systems, 2025-2026 | URL pending — referenced in harness-governance-gap.md without source |
| [REPO-AI-SEC-GOV] | Aaron's public repo github.com/mrmeman555/ai-security-governance | Not found in web search — may be private or not yet published |

## Corrections Found During Source Verification

1. **PSPDFKit exit value:** The `~$800M exit` claim in events/2026-01--openclaw-viral.md is not supported. Confirmed value is EUR 100M / ~$116M USD (Insight Partners investment, October 2021). [STEIPETE-PSPDFKIT]
2. **ISO 42001 Section 8.2 vs 8.4:** Section 8.2 covers "AI risk assessment." The "AI system impact assessment" is at Clause 8.4. Both are relevant but distinct. [ISO-42001]
3. **HITRUST 51 controls:** The "51 controls" figure refers to the AI Risk Management Assessment, not the AI Security Assessment (which has up to 44 controls). These are separate HITRUST products. [HITRUST-AI]
4. **WIRED and ZDNET Glasswing coverage:** Not verified — multiple searches found no dedicated articles from either outlet. Consider removing these references or qualifying them.
5. **FISA-702 / Glasswing connection:** The Glasswing disclosure and 702 renewal push are editorially adjacent (same news cycle, April 7-8, 2026) but no single article explicitly frames 702 renewal as "citing Glasswing." [FISA-702]

---

*This bibliography is maintained alongside the artifacts it supports. When a new event or finding is added, its sources are registered here. See [repo-governance.md](controls/repo-governance.md) for sourcing standards.*
