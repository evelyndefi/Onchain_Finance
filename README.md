# Pharos Network

<p align="center">
  <img src="https://img.shields.io/badge/Network-Mainnet-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
  <img src="https://img.shields.io/badge/EVM-Compatible-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
  <img src="https://img.shields.io/badge/TPS-130%2C000%2B-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
  <img src="https://img.shields.io/badge/Finality-Sub--second-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
  <img src="https://img.shields.io/badge/License-Apache_2.0-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
  <img src="https://img.shields.io/badge/PRs-Welcome-gold?style=flat-square&labelColor=0d0d18&color=C9A84C" />
</p>

<p align="center">
  <b>The fastest EVM-compatible Layer-1 blockchain for real-world assets and cross-chain liquidity.</b><br/>
  Built to unify Web2, Web3, and Traditional Finance at internet scale.
</p>

<p align="center">
  <a href="https://pharos.xyz">Website</a> ·
  <a href="https://docs.pharos.xyz">Docs</a> ·
  <a href="https://pharosscan.xyz">Explorer</a> ·
  <a href="https://discord.gg/pharos">Discord</a> ·
  <a href="https://twitter.com/PharosNetwork">Twitter</a>
</p>

---

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Key Features](#key-features)
- [Performance](#performance)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Connecting to Mainnet](#connecting-to-mainnet)
  - [Running a Local Node](#running-a-local-node)
- [Deploying Contracts](#deploying-contracts)
- [Special Processing Networks (SPNs)](#special-processing-networks-spns)
- [Token — $PROS](#token--pros)
- [Ecosystem](#ecosystem)
- [Security](#security)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

Pharos Network is a high-performance, modular Layer-1 blockchain purpose-built for **Real-World Asset (RWA) tokenization**, **institutional-grade DeFi**, and **decentralized payments**. While most Layer-1s are general-purpose, Pharos is engineered specifically to meet the performance, compliance, and scalability demands of real-world financial infrastructure.

Pharos bridges the gap between Traditional Finance (TradFi) and decentralized finance by delivering:

- **Payment-grade throughput** — 130,000+ TPS demonstrated in 100-node testbed conditions
- **Sub-second finality** — AsyncBFT consensus with speculative parallel execution
- **Compliance-native infrastructure** — zkDID, zkKYC, and programmable AML at the protocol layer
- **Modular extensibility** — Special Processing Networks (SPNs) for domain-specific financial workloads
- **Full EVM compatibility** — Deploy Solidity contracts with zero friction; WASM support available via SPNs

> Pharos private mainnet launched **December 12, 2025**. Public mainnet rollout is ongoing.

---

## Architecture

Pharos operates on a three-layer modular stack designed for maximum parallelism and financial specialization:

```
┌──────────────────────────────────────────────────────────┐
│                     L1-Extension                         │
│   Special Processing Networks (SPNs)                     │
│   Independent validator sets · Native restaking          │
│   Cross-SPN interoperability · Domain-specific execution │
├──────────────────────────────────────────────────────────┤
│                       L1-Core                            │
│   AsyncBFT Consensus · Dual VM (EVM + WASM)              │
│   Speculative Parallel Execution · Sub-second Finality   │
├──────────────────────────────────────────────────────────┤
│                       L1-Base                            │
│   High-Performance Data Availability                     │
│   Hardware Acceleration · 80% Lower Storage Overhead     │
│   Delta-Encoded Multi-Version Merkle Tree                │
└──────────────────────────────────────────────────────────┘
                     Pharos VM (PVM)
         Parallel Merklization · Async Pipelining
         Full Lifecycle Transaction Processing
```

### Degree of Parallelism

Pharos is built on a five-tier **Degree of Parallelism (DP)** model:

| Level | Capability | Status |
|-------|-----------|--------|
| DP1 | Scalable consensus | ✅ Live |
| DP2 | Parallel transaction execution | ✅ Live |
| DP3 | Full-lifecycle async pipelining | ✅ Live |
| DP4 | High-performance authenticated storage | ✅ Live |
| DP5 | Heterogeneous computing via SPNs | 🔄 Roadmap |

---

## Key Features

### Real-World Asset (RWA) Native
Pharos is designed from the ground up for tokenizing and trading real-world assets — bonds, funds, private credit, real estate, energy projects, and commodities. It provides the issuance, circulation, and settlement infrastructure that institutions require.

### Special Processing Networks (SPNs)
SPNs are application-specific sub-networks that operate independently while maintaining shared security with the Pharos mainnet. Each SPN has its own:
- Execution engine and VM environment
- Independent validator set with native restaking
- Governance parameters
- Cross-SPN atomic communication

Use SPNs to build high-frequency trading engines, AI inference layers, DePIN infrastructure, or any specialized financial workload — without congesting the main chain.

### Compliance-First Design
Pharos embeds compliance infrastructure at the protocol layer:
- **zkDID** — decentralized digital identity with zero-knowledge proofs
- **zkKYC** — privacy-preserving identity verification
- **Programmable AML** — on-chain anti-money-laundering logic
- **Audit Trails** — transparent and verifiable transaction history for institutional requirements

### Dual VM — EVM + WASM
- Deploy existing Solidity and Vyper smart contracts with no modifications
- Access WASM execution for performance-critical or language-diverse applications
- Shared state and atomic cross-VM interactions

### Cross-Chain Liquidity
Native cross-SPN and cross-chain communication enables atomic execution across networks, shared global state, and multi-VM interactions — creating a truly interconnected financial ecosystem.

---

## Performance

| Metric | Pharos | Solana | Ethereum |
|--------|--------|--------|----------|
| Peak TPS | **130,000+** | ~65,000 | ~15 |
| Finality | **< 1 second** | ~0.4s | ~15 min |
| Storage Overhead | **−80%** (vs. standard) | Standard | Standard |
| VM Support | **EVM + WASM** | SVM | EVM |
| RWA Native | **✅** | ❌ | Partial |
| zkKYC Protocol Layer | **✅** | ❌ | ❌ |

> Benchmark figures from the Pharos 100-node prototype testbed. Production figures may vary.

---

## Getting Started

### Prerequisites

- Node.js `>= 18.x`
- Git
- A Web3 wallet (MetaMask, Rabby, or compatible EVM wallet)
- `pharos-cli` (see installation below)

### Installation

```bash
# Clone the repository
git clone https://github.com/PharosNetwork/pharos-node.git
cd pharos-node

# Install dependencies
npm install

# Copy environment config
cp .env.example .env
```

### Connecting to Mainnet

Add Pharos Network to your wallet or development environment:

```
Network Name:   Pharos Network
RPC URL:        https://rpc.pharos.xyz
Chain ID:       17000
Currency:       PROS
Explorer:       https://pharosscan.xyz
```

Or via code:

```javascript
import { ethers } from "ethers";

const provider = new ethers.JsonRpcProvider("https://rpc.pharos.xyz");
const network = await provider.getNetwork();
console.log(`Connected to Pharos — Chain ID: ${network.chainId}`);
```

### Running a Local Node

```bash
# Pull the Pharos node image
docker pull pharosnetwork/node:latest

# Start a local development node
docker run -p 8545:8545 -p 30303:30303 \
  --name pharos-local \
  pharosnetwork/node:latest \
  --dev \
  --rpc \
  --rpc-addr 0.0.0.0:8545

# Verify the node is running
curl -X POST http://localhost:8545 \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":1}'
```

---

## Deploying Contracts

Pharos is fully EVM-compatible. Use any standard Ethereum toolchain:

### Hardhat

```javascript
// hardhat.config.js
module.exports = {
  networks: {
    pharos: {
      url: "https://rpc.pharos.xyz",
      chainId: 17000,
      accounts: [process.env.PRIVATE_KEY],
    },
    pharosTestnet: {
      url: "https://testnet-rpc.pharos.xyz",
      chainId: 17001,
      accounts: [process.env.PRIVATE_KEY],
    },
  },
  solidity: "0.8.24",
};
```

```bash
npx hardhat run scripts/deploy.js --network pharos
```

### Foundry

```bash
forge create --rpc-url https://rpc.pharos.xyz \
  --private-key $PRIVATE_KEY \
  src/MyContract.sol:MyContract
```

### Example: Deploy an RWA Token

```solidity
// SPDX-License-Identifier: Apache-2.0
pragma solidity ^0.8.24;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@pharos/compliance/zkKYC.sol";

contract RWAToken is ERC20, PharoszkKYC {
    constructor(string memory name, string memory symbol)
        ERC20(name, symbol)
    {}

    function mint(address to, uint256 amount)
        external
        onlyVerified(to)   // zkKYC gate — only verified wallets can receive
    {
        _mint(to, amount);
    }
}
```

---

## Special Processing Networks (SPNs)

SPNs extend Pharos with domain-specific execution environments. To register and launch an SPN:

```bash
# Install the Pharos CLI
npm install -g @pharos/cli

# Initialize a new SPN project
pharos spn init my-trading-spn

# Configure your SPN (execution engine, validator set, restaking params)
cd my-trading-spn
nano spn.config.json

# Deploy to Pharos mainnet
pharos spn deploy --network mainnet
```

Example SPN configuration:

```json
{
  "name": "HighFrequencyTrading-SPN",
  "execution_engine": "EVM",
  "validator_count": 21,
  "restaking_asset": "PROS",
  "min_stake": "100000",
  "finality_mode": "instant",
  "cross_spn_enabled": true,
  "compliance": {
    "zkkyc_required": true,
    "aml_enabled": true
  }
}
```

---

## Token — $PROS

`$PROS` is the native utility token of Pharos Network.

| Property | Detail |
|----------|--------|
| Genesis Supply | 1,000,000,000 PROS (fixed) |
| Token Standard | Native L1 (EVM-compatible) |
| Vesting | 12-month cliff for team & investor allocations |
| Exchange | MEXC (spot + futures) |

**Token Utilities:**

| Use Case | Description |
|----------|-------------|
| Gas Fees | Powers all on-chain transactions on Pharos mainnet and SPNs |
| Staking | Validators stake PROS to secure the network and earn block rewards |
| Governance | PROS holders vote on protocol upgrades and parameter changes |
| SPN Incentives | Reward specialized SPN operators via native restaking |
| Collateral | Used as collateral in native lending protocols (e.g. Morpho integration) |

---

## Ecosystem

| Partner | Category | Integration |
|---------|----------|-------------|
| Chainlink | Oracle | Native price feeds and cross-chain messaging |
| Morpho | Lending | Native RWA lending infrastructure |
| GCL Energy | RWA | Solar-backed tokenized assets |
| Sumitomo | TradFi | Institutional asset bridge |
| Flow Traders | Market Making | On-chain liquidity provision |
| Goldsky | Indexing | Real-time blockchain data streaming |

**Builder Programs:**
- [Pharos Builder Base Camp](https://buildonpharos.com) — Global accelerator for RWA and DeFi builders
- Grants Program — Up to $500K for qualifying projects
- SPN Incubator — Technical and go-to-market support for SPN teams

---

## Security

Security is a top priority for Pharos Network. If you believe you have found a security vulnerability, please **do not** open a public GitHub issue.

Report vulnerabilities via our responsible disclosure program:

- **Email:** security@pharos.xyz
- **Bug Bounty:** [pharos.xyz/security](https://pharos.xyz/security)

Please include:
- A clear description of the vulnerability
- Steps to reproduce
- Potential impact assessment
- Any proof-of-concept code (if applicable)

We will acknowledge your report within **48 hours** and aim to resolve critical issues within **7 days**.

See [SECURITY.md](./SECURITY.md) for our full disclosure policy.

---

## Contributing

Pharos is an open protocol. Contributions from the community are welcome and encouraged.

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before submitting a pull request.

**Quick start for contributors:**

```bash
git clone https://github.com/PharosNetwork/pharos-node.git
cd pharos-node
git checkout -b feat/your-feature-name
# Make your changes
git commit -m "feat: describe your change"
git push origin feat/your-feature-name
# Open a Pull Request on GitHub
```

See [CONTRIBUTING.md](./CONTRIBUTING.md) for branch naming conventions, commit standards, and the full review process.

---

## License

Copyright 2025–2026 Pharos Network Contributors.

Licensed under the **Apache License, Version 2.0**. You may not use this project except in compliance with the License. A copy of the License is included at [LICENSE](./LICENSE).

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.

---

<p align="center">
  Built with precision for the financial internet.<br/>
  <a href="https://pharos.xyz">pharos.xyz</a> · <a href="https://twitter.com/PharosNetwork">@PharosNetwork</a>
</p>
