# Changelog

All notable changes to Pharos Network are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).  
Versioning follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### In Progress
- DP5 heterogeneous computing support via SPNs
- Cross-chain bridge to Ethereum mainnet (general availability)
- Morpho native lending protocol integration
- Expanded zkKYC provider network

---

## [1.0.0] — 2025-12-12 — Private Mainnet Launch

### Added
- Pharos mainnet genesis block
- AsyncBFT consensus with sub-second finality
- Parallel transaction execution (DP4)
- EVM compatibility layer (Solidity 0.8.x support)
- Pharos Virtual Machine (PVM) with async pipelining
- Delta-Encoded Multi-Version Merkle Tree (80% storage reduction)
- L1-Base high-performance data availability layer
- L1-Core decentralized validator network
- L1-Extension SPN framework (alpha)
- zkDID and zkKYC identity primitives at protocol layer
- Native PROS token issuance and gas system
- `pharos-cli` v0.1.0
- JSON-RPC API (Ethereum-compatible)
- Pharos Block Explorer (pharosscan.xyz)
- Goldsky indexer integration

### Performance (100-node testbed)
- 130,000+ transactions per second peak throughput
- Sub-second finality under full load
- 80% reduction in state storage vs. standard Merkle Patricia Trie

---

## [0.9.0] — 2025-09-01 — Public Testnet

### Added
- Public testnet launch with faucet
- SPN SDK v0.1 (beta)
- WASM execution environment (beta)
- Cross-SPN messaging protocol (alpha)
- Developer documentation site (docs.pharos.xyz)
- Hardhat and Foundry plugins
- TypeScript SDK v0.1.0
- Python SDK v0.1.0

### Fixed
- Gas estimation rounding error for complex multi-call transactions
- P2P peer discovery stability on high-latency connections
- EVM DELEGATECALL nesting edge case

---

## [0.5.0] — 2025-03-10 — Builder Base Camp Launch

### Added
- Pharos Builder Base Camp program launch
- Initial SPN specification (PIP-001)
- zkKYC integration spec (PIP-002)
- Reference SPN implementation (high-frequency trading template)
- Internal testnet for Builder Base Camp participants

---

## [0.1.0] — 2024-12-01 — Seed Round / Internal Devnet

### Added
- Initial protocol design and architecture
- Internal devnet deployment
- Core team formation (ex-AntChain, Microsoft Research, Stanford)
- $8M seed round closed

---

[Unreleased]: https://github.com/PharosNetwork/pharos-node/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/PharosNetwork/pharos-node/releases/tag/v1.0.0
[0.9.0]: https://github.com/PharosNetwork/pharos-node/releases/tag/v0.9.0
[0.5.0]: https://github.com/PharosNetwork/pharos-node/releases/tag/v0.5.0
[0.1.0]: https://github.com/PharosNetwork/pharos-node/releases/tag/v0.1.0
