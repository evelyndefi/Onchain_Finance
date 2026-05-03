# Security Policy

## Reporting a Vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

If you believe you've discovered a security vulnerability in Pharos Network — including the core node, smart contracts, SPNs, SDK, or any other component — please report it privately via our responsible disclosure program.

**Contact:** security@pharos.xyz  
**PGP Key:** Available at [pharos.xyz/pgp](https://pharos.xyz/pgp)  
**Bug Bounty:** [pharos.xyz/security](https://pharos.xyz/security)

### What to Include

- A clear description of the vulnerability
- The affected component and version
- Steps to reproduce
- Your assessment of the potential impact
- Proof-of-concept code or exploit (if available)

### Response Timeline

| Action | Target |
|--------|--------|
| Initial acknowledgement | 48 hours |
| Severity assessment | 5 business days |
| Fix for critical issues | 7 days |
| Fix for high severity | 14 days |
| Fix for medium/low | 30 days |
| Public disclosure | After fix is deployed |

We credit all responsible disclosures in our release notes (with your permission).

## Scope

### In Scope

- Pharos core node (consensus, execution, networking)
- Pharos Virtual Machine (PVM) — EVM and WASM runtimes
- Smart contract vulnerabilities in official Pharos contracts
- SPN SDK and protocol-level SPN interactions
- zkKYC and zkDID identity infrastructure
- Pharos CLI and official SDKs
- RPC API endpoints

### Out of Scope

- Third-party applications built on Pharos
- Phishing attacks
- Social engineering
- DoS attacks without demonstrated impact
- Issues already publicly known or previously reported

## Supported Versions

| Version | Supported |
|---------|-----------|
| Mainnet (latest) | ✅ |
| Testnet (latest) | ✅ |
| Older releases | ❌ — please upgrade |
