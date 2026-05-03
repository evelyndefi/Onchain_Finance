# Contributing to Pharos Network

Thank you for your interest in contributing to Pharos Network. Pharos is an open protocol — built in public, improved by the community. Whether you're fixing a bug, adding a feature, improving documentation, or proposing architectural changes, your contribution matters.

Please take a few minutes to read this guide before submitting anything. It keeps the process smooth for everyone.

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [What We're Looking For](#what-were-looking-for)
- [How to Report a Bug](#how-to-report-a-bug)
- [How to Request a Feature](#how-to-request-a-feature)
- [Development Setup](#development-setup)
- [Branch Naming Conventions](#branch-naming-conventions)
- [Commit Message Standard](#commit-message-standard)
- [Pull Request Process](#pull-request-process)
- [Code Style](#code-style)
- [Testing Requirements](#testing-requirements)
- [Documentation](#documentation)
- [Review Criteria](#review-criteria)
- [Community & Support](#community--support)

---

## Code of Conduct

All contributors are expected to uphold our [Code of Conduct](./CODE_OF_CONDUCT.md). We are committed to maintaining a welcoming, inclusive, and respectful environment for builders of all backgrounds.

Violations may be reported to **conduct@pharos.xyz**.

---

## What We're Looking For

We actively welcome contributions in the following areas:

**Core Protocol**
- Performance improvements to the parallel execution engine
- Consensus layer enhancements (AsyncBFT, validator coordination)
- Storage optimization (Merkle tree, state management)
- P2P networking and node communication

**EVM / WASM Compatibility**
- Bug fixes and edge cases in EVM execution
- WASM runtime improvements
- Cross-VM interaction utilities

**Special Processing Networks (SPNs)**
- SPN SDK improvements
- New SPN templates (DeFi, AI, DePIN, payments)
- Cross-SPN messaging protocols

**Compliance & Identity**
- zkKYC and zkDID protocol improvements
- Programmable AML tooling
- Privacy-preserving identity primitives

**Developer Tooling**
- CLI improvements (`@pharos/cli`)
- SDK updates (JS/TS, Python, Rust)
- Hardhat / Foundry plugins
- Block explorer contributions

**Documentation**
- Technical guides and tutorials
- API reference improvements
- Translated documentation

---

## How to Report a Bug

> ⚠️ **Security vulnerabilities must never be reported as public GitHub issues.**
> See [SECURITY.md](./SECURITY.md) for the responsible disclosure process.

For non-security bugs:

1. Check [existing issues](https://github.com/PharosNetwork/pharos-node/issues) to avoid duplicates.
2. Open a new issue using the **Bug Report** template.
3. Include:
   - A clear, descriptive title
   - Steps to reproduce the issue
   - Expected vs. actual behavior
   - Node version, OS, and relevant environment details
   - Any relevant logs or error output

---

## How to Request a Feature

1. Check [existing discussions](https://github.com/PharosNetwork/pharos-node/discussions) and open issues.
2. Open a new issue using the **Feature Request** template.
3. Describe:
   - The problem you're solving or the improvement you're proposing
   - Your proposed solution or approach
   - Any alternatives you've considered
   - Relevant context (ecosystem, use case, partners)

For significant protocol changes, open a **Pharos Improvement Proposal (PIP)** discussion before writing code. This saves everyone time.

---

## Development Setup

### Prerequisites

- **Node.js** >= 18.x
- **Rust** >= 1.75 (for core node components)
- **Go** >= 1.21 (for networking layer)
- **Docker** >= 24.x (for local testnet)
- **Git**

### Clone and Bootstrap

```bash
git clone https://github.com/PharosNetwork/pharos-node.git
cd pharos-node

# Install Node.js dependencies
npm install

# Build core Rust components
cargo build --workspace

# Start a local development network
docker-compose -f docker/dev.yml up -d

# Run the test suite
npm test
```

### Environment Configuration

```bash
cp .env.example .env
# Edit .env with your local settings
```

Key environment variables:

| Variable | Description | Default |
|----------|-------------|---------|
| `PHAROS_RPC_PORT` | Local RPC port | `8545` |
| `PHAROS_P2P_PORT` | P2P networking port | `30303` |
| `PHAROS_CHAIN_ID` | Chain ID for local dev | `31337` |
| `PHAROS_LOG_LEVEL` | Logging verbosity | `info` |
| `PHAROS_DEV_MODE` | Enable dev shortcuts | `true` |

---

## Branch Naming Conventions

Use the following prefixes when creating branches:

| Prefix | Use For |
|--------|---------|
| `feat/` | New features |
| `fix/` | Bug fixes |
| `docs/` | Documentation only |
| `refactor/` | Code restructuring, no behavior change |
| `test/` | Adding or improving tests |
| `chore/` | Build system, CI, dependency updates |
| `spn/` | SPN-specific changes |
| `pip/` | Pharos Improvement Proposals |

**Examples:**
```
feat/spn-cross-chain-messaging
fix/evm-gas-estimation-overflow
docs/update-rwa-tutorial
refactor/merkle-tree-storage
```

---

## Commit Message Standard

We follow the **Conventional Commits** specification.

**Format:**
```
<type>(<scope>): <short description>

[optional body]

[optional footer(s)]
```

**Types:**

| Type | When to Use |
|------|-------------|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation changes only |
| `style` | Formatting, no logic changes |
| `refactor` | Code change with no feature/fix |
| `perf` | Performance improvement |
| `test` | Adding or fixing tests |
| `chore` | Maintenance tasks |
| `revert` | Reverting a previous commit |

**Examples:**

```
feat(spn): add cross-SPN atomic message passing

Implements the cross-SPN message protocol as specified in PIP-007.
Supports atomic execution across up to 8 SPNs in a single transaction.

Closes #412
```

```
fix(evm): correct gas estimation for DELEGATECALL edge case

Gas was being under-estimated when DELEGATECALL was used inside a
nested call stack deeper than 4 levels. Fixes incorrect refunds.

Fixes #389
```

```
docs(rwa): add tutorial for tokenizing real estate assets
```

---

## Pull Request Process

1. **Fork** the repository and create your branch from `main`.
2. **Write or update tests** for any changed functionality.
3. **Ensure all tests pass** before opening a PR:
   ```bash
   npm run test
   npm run lint
   cargo test --workspace
   ```
4. **Open a Pull Request** using the provided PR template.
5. **Link relevant issues** using GitHub keywords (`Closes #123`, `Fixes #456`).
6. **Request review** from at least one core maintainer.
7. **Address all review comments** before merging.

### PR Checklist

Before submitting, confirm:

- [ ] My branch is up to date with `main`
- [ ] All existing tests pass
- [ ] I have added tests for new functionality
- [ ] I have updated relevant documentation
- [ ] Commit messages follow the Conventional Commits standard
- [ ] No sensitive keys, credentials, or private data in the diff
- [ ] Security implications have been considered
- [ ] For consensus/execution changes: benchmarks are included

### Review Timeline

| PR Type | Expected First Review |
|---------|----------------------|
| Documentation | 2–3 business days |
| Bug Fix (non-critical) | 3–5 business days |
| Feature (small) | 5–7 business days |
| Feature (large / protocol) | 7–14 business days + PIP discussion |
| Security Fix | 24–48 hours |

---

## Code Style

### Solidity

- Follow the [Solidity Style Guide](https://docs.soliditylang.org/en/latest/style-guide.html)
- Use `^0.8.24` or higher
- All public functions must have NatSpec documentation
- Run `npx solhint` before committing

```solidity
/// @notice Transfers `amount` of PROS tokens to `recipient`
/// @dev Applies zkKYC verification before transfer
/// @param recipient The address receiving the tokens
/// @param amount The amount of PROS to transfer (18 decimals)
function transfer(address recipient, uint256 amount)
    external
    override
    onlyVerified(recipient)
    returns (bool)
{
    // implementation
}
```

### Rust

- Follow standard Rust conventions (`rustfmt`, `clippy`)
- Run `cargo fmt` and `cargo clippy` before committing
- All public APIs must have doc comments

### TypeScript / JavaScript

- ESLint + Prettier enforced
- Run `npm run lint` and `npm run format`
- Prefer `async/await` over raw Promises

---

## Testing Requirements

All contributions involving code must include tests.

### Test Structure

```
tests/
├── unit/          # Unit tests for individual functions/modules
├── integration/   # Integration tests (multi-component, local node required)
├── e2e/           # End-to-end tests against testnet
└── benchmarks/    # Performance benchmarks (required for core changes)
```

### Running Tests

```bash
# All tests
npm test

# Unit tests only
npm run test:unit

# Integration tests (requires local node)
npm run test:integration

# Solidity tests via Foundry
forge test -vvv

# Rust tests
cargo test --workspace

# Benchmarks
npm run bench
```

### Coverage Requirements

| Layer | Minimum Coverage |
|-------|-----------------|
| Smart Contracts | 90% |
| Core Node (Rust) | 80% |
| SDK (TypeScript) | 85% |
| CLI | 75% |

---

## Documentation

If your contribution changes user-facing behavior, update the relevant documentation in the `/docs` directory or at [docs.pharos.xyz](https://docs.pharos.xyz).

For significant new features, please include:
- A technical explanation in the PR description
- Updated or new documentation in `/docs`
- Inline code comments for non-obvious logic
- An entry in [CHANGELOG.md](./CHANGELOG.md) under `[Unreleased]`

---

## Review Criteria

Core maintainers evaluate PRs against the following criteria:

1. **Correctness** — Does the code do what it claims? Are edge cases handled?
2. **Performance** — Does it maintain or improve Pharos's performance characteristics?
3. **Security** — Are there any attack vectors introduced?
4. **Compatibility** — Does it preserve EVM compatibility and existing API contracts?
5. **Test Coverage** — Is the functionality adequately tested?
6. **Code Quality** — Is the code readable, maintainable, and idiomatic?
7. **Documentation** — Is the change appropriately documented?

---

## Community & Support

- **Discord:** [discord.gg/pharos](https://discord.gg/pharos) — `#dev-contributors` channel for questions
- **Discussions:** [GitHub Discussions](https://github.com/PharosNetwork/pharos-node/discussions) for proposals and RFCs
- **Twitter:** [@PharosNetwork](https://twitter.com/PharosNetwork)
- **Builder Base Camp:** [buildonpharos.com](https://buildonpharos.com)

For contribution-related questions not answered here, open a GitHub Discussion or reach out in Discord.

---

*Thank you for building the financial internet with us.*
