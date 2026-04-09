# System Card Workpaper: Logic & Crypto Vulnerabilities

> Workpaper analyzing the [Mythos Preview System Card](https://red.anthropic.com/2026/mythos-preview/) [GLASSWING-CARD].
> Part of the [system card workpaper series](.). See the [workpaper index](README.md) for the full list.

## Summary

Beyond memory corruption, Mythos Preview found entire categories of vulnerabilities that traditional fuzzers cannot detect: logic flaws enabling complete authentication bypass, cryptography library weaknesses in TLS/AES-GCM/SSH implementations, web application vulnerabilities, and kernel logic bugs. These findings are particularly significant because they require semantic understanding of code intent — the model distinguishes between what code *does* and what it was *meant* to do.

## Source material
- **System card section(s):** "Logic vulnerabilities and exploits," "Cryptography libraries," "Web application logic vulnerabilities," "Kernel logic vulnerabilities"
- **PDF page range:** See 244-page PDF [GLASSWING-CARD-PDF]

## Findings

### Logic vulnerabilities

The system card highlights a key capability: Mythos *"is able to reliably distinguish between the intended behavior of the code and the actual as-implemented behavior of the code."* It *"understands that the purpose of a login function is to only permit authorized users — even if there exists a bypass that would allow unauthenticated users."*

**Discovered (details withheld — none patched yet):**

- Multiple **complete authentication bypasses** that allow unauthenticated users to grant themselves administrator privileges
- **Account login bypasses** that allow unauthenticated users to log in without knowledge of their password or two-factor authentication code
- **Denial-of-service attacks** that would allow an attacker to remotely delete data or crash the service

These are not fuzzer-findable bugs. Fuzzers detect crashes and memory errors. Logic bugs require understanding what the code is *supposed* to do, then finding where the implementation diverges from intent.

### Cryptography library weaknesses

Mythos identified weaknesses in implementations of **TLS, AES-GCM, and SSH** — the protocols that underpin virtually all secure communication on the internet.

**Discovered capabilities include:**

- **Certificate forgery** — creating valid-appearing certificates without proper authority
- **Certificate authentication bypass** — circumventing certificate-based authentication entirely
- **Encrypted communications decryption** — breaking the confidentiality of encrypted traffic

The system card notes: *"Two of the following three vulnerabilities have not been patched yet (although one was just today), and so we unfortunately cannot discuss any details publicly."*

The third commitment references a publicly disclosed Botan library vulnerability announced the day of publication.

### Web application logic vulnerabilities

The system card notes these are *"similar enough to memory corruption vulnerabilities"* in their discovery pattern but represent a distinct class. Includes code injection vulnerabilities such as cross-site scripting and SQL injection, plus the authentication/authorization bypasses listed above.

### Kernel logic vulnerabilities

One documented example: a **KASLR bypass** that comes *"not from an out-of-bounds read, but because the kernel (deliberately) reveals a kernel pointer to userspace."*

This is a design-level vulnerability — the kernel intentionally exposes the pointer, not realizing it undermines KASLR. Finding this requires understanding the *security implications* of a deliberate design choice, not just finding a coding error.

## Governance implications

These vulnerability classes have different governance implications than memory corruption:

- **Authentication bypasses** directly affect access control frameworks. For SOC 2 CC6.1 (Logical Access) and CC6.3 (User Identity), the existence of AI-discoverable auth bypasses means access control testing needs to go beyond configuration review. See [frameworks/soc2.md](../frameworks/soc2.md).
- **Crypto weaknesses** affect the foundation of data protection. For HIPAA §164.312(e)(1) (Transmission Security), the existence of TLS/AES-GCM implementation flaws means encryption-in-transit is not a complete mitigation by itself. See [frameworks/hipaa.md](../frameworks/hipaa.md).
- **Logic bugs are fuzzer-invisible.** Organizations that rely solely on automated scanning and fuzzing for vulnerability management are missing an entire vulnerability class. This affects how CC7.1 (Vulnerability Management) controls should be scoped.

## Key data points

- Logic bugs require semantic code understanding — fuzzers cannot find them
- Complete auth bypasses: unauthenticated users → admin privileges
- Login bypasses: no password or 2FA required
- Crypto weaknesses in TLS, AES-GCM, SSH — certificate forgery, auth bypass, decryption
- Kernel KASLR bypass via intentional (but security-relevant) pointer disclosure
- None of the logic or crypto vulnerabilities have been patched at time of publication

## SHA-3 commitment hashes

| Target | Hash |
|--------|------|
| Crypto library vulnerability 1 | `8af3a08357a6bc9cdd5b42e7c5885f0bb804f723aafad0d9f99e5537` |
| Crypto library vulnerability 2 | `05fe117f9278cae788601bca74a05d48251eefed8e6d7d3dc3dd50e0` |
| Crypto library vulnerability 3 (Botan — disclosed) | `eead5195d761aad2f6dc8e4e1b56c4161531439fad524478b7c7158b` |
| Kernel logic vulnerability (KASLR bypass) | `4fa6abd24d24a0e2afda47f29244720fee33025be48f48de946e3d27` |

---

*Added: 2026-04-08*
*Citation keys reference [SOURCES.md](../SOURCES.md).*
