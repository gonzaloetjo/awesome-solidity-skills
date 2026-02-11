# Awesome Solidity Skills [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

<div align="center">

<p>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC0--1.0-blue?style=flat-square" alt="License: CC0-1.0"></a>
  <a href="https://github.com/gonzaloetjo/awesome-solidity-skills/stargazers"><img src="https://img.shields.io/github/stars/gonzaloetjo/awesome-solidity-skills?style=flat-square" alt="GitHub Stars"></a>
  <a href="https://github.com/gonzaloetjo/awesome-solidity-skills/commits"><img src="https://img.shields.io/github/last-commit/gonzaloetjo/awesome-solidity-skills?style=flat-square" alt="Last Commit"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="PRs Welcome"></a>
  <a href="https://github.com/gonzaloetjo/awesome-solidity-skills/actions/workflows/links.yml"><img src="https://img.shields.io/github/actions/workflow/status/gonzaloetjo/awesome-solidity-skills/links.yml?label=links&style=flat-square" alt="Link Check"></a>
</p>

<sub>A curated list of Claude Code skills for Solidity and EVM smart contract development.</sub>

</div>

## Contents

- [Security & Auditing](#security--auditing)
- [Development & Architecture](#development--architecture)
- [Testing](#testing)
- [DeFi & Tokens](#defi--tokens)
- [Deployment & Tooling](#deployment--tooling)
- [Related Tools](#related-tools)
- [How to Install Skills](#how-to-install-skills)

## Security & Auditing

> Skills focused on smart contract security analysis, vulnerability detection, and secure coding patterns.

- [Smart Contract Security](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/smart-contract-security) - Comprehensive security auditing and vulnerability detection for Solidity smart contracts.
- [Solidity Audit Skills](https://github.com/gonzaloetjo/solidity-audit-skills) - Skill to audit Solidity contracts using Claude Code teams.
- [Building Secure Contracts](https://github.com/trailofbits/skills/tree/main/plugins/building-secure-contracts) - Smart contract security toolkit based on Trail of Bits' Building Secure Contracts framework.
- [Entry Point Analyzer](https://github.com/trailofbits/skills/tree/main/plugins/entry-point-analyzer) - Systematically identifies state-changing entry points in smart contract codebases to guide security audits.
- [Spec-to-Code Compliance](https://github.com/trailofbits/skills/tree/main/plugins/spec-to-code-compliance) - Specification-to-code compliance checker for blockchain audits with evidence-based alignment analysis.
- [Audit Context Building](https://github.com/trailofbits/skills/tree/main/plugins/audit-context-building) - Builds deep architectural context through ultra-granular code analysis before vulnerability hunting.
- [Differential Review](https://github.com/trailofbits/skills/tree/main/plugins/differential-review) - Security-focused differential review of code changes with git history analysis and blast radius estimation.
- [Fix Review](https://github.com/trailofbits/skills/tree/main/plugins/fix-review) - Verifies that code changes address security audit findings without introducing bugs.
- [Variant Analysis](https://github.com/trailofbits/skills/tree/main/plugins/variant-analysis) - Finds similar vulnerabilities and bugs across codebases using pattern-based analysis.
- [Static Analysis](https://github.com/trailofbits/skills/tree/main/plugins/static-analysis) - Comprehensive static analysis toolkit with CodeQL, Semgrep, and SARIF parsing for security vulnerability detection.
- [SCV Scan](https://github.com/kadenzipfel/scv-scan) - Scans Solidity codebases for security vulnerabilities by referencing 36 unique vulnerability types.
- [Solidity Audit Skill](https://github.com/yolodolo42/solidity-audit-skill) - Solidity smart contract security audits with MCP server for structured build, test, and audit tools.
- [Solidity Security Audit Skill](https://github.com/mariano-aguero/solidity-security-audit-skill) - AI agent skill for Solidity smart contract security auditing and vulnerability detection.

## Development & Architecture

> Skills for Solidity smart contract architecture, development workflows, and best practices.

- [Solidity Development Expert](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/solidity-development) - Expert-level Solidity architecture guidance and development best practices.
- [Ethereum Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/ethereum-development) - Full-stack Ethereum development including contracts, testing, and deployment.
- [Foundry Solidity Development](https://github.com/tenequm/claude-plugins/tree/main/foundry-solidity) - Modern Foundry 1.5.0 workflow for Solidity development and testing.
- [Arbitrum dApp Skill](https://github.com/hummusonrails/arbitrum-dapp-skill) - Building dApps on Arbitrum using Stylus and Solidity with Foundry integration.
- [Ethereum Dev Skill](https://github.com/minimalsm/ethereum-dev-skill) - Ethereum development with viem, wagmi, Foundry, and Solidity.
- [Solidity Agent Kit](https://github.com/0xlayerghost/solidity-agent-kit) - Agent skills for Solidity and DeFi development with Foundry covering security, testing, and deployment.
- [ContractKit](https://github.com/HCS412/contractkit) - Smart contract workspace with Claude Code integration for Ethereum and Foundry.
- [EVM Agent Skills](https://github.com/SkandaBhat/evm-agent-skills) - Ethereum JSON-RPC skill with cast-backed execution and workflows for block analysis.
- [Onchain TypeScript Skills](https://github.com/0xSardius/onchain-typescript-skills) - TypeScript blockchain development skills with Viem and Wagmi.
- [Ember Skills](https://github.com/emberdragonc/ember-skills) - Solidity, Web3, and deployment pattern skills extracted from real builds.
- [OP Stack Skills](https://github.com/pauldowman/op-claude-plugins) - Claude Code skills for working with OP Stack blockchains.
- [EVM Foundry](https://github.com/celo-org/agent-skills/tree/main/skills/evm-foundry) - Foundry development for EVM chains covering forge, cast, anvil, testing, and deployment.
- [EVM Hardhat](https://github.com/celo-org/agent-skills/tree/main/skills/evm-hardhat) - Hardhat development for EVM chains covering project setup, compilation, testing, and deployment.
- [Viem](https://github.com/celo-org/agent-skills/tree/main/skills/viem) - Using the viem TypeScript library for EVM development with fee currency support and transaction signing.
- [Wagmi](https://github.com/celo-org/agent-skills/tree/main/skills/wagmi) - Wagmi React hooks for EVM dApps with wallet connection and transaction patterns.
- [EVM Wallet Integration](https://github.com/celo-org/agent-skills/tree/main/skills/evm-wallet-integration) - Wallet integration for dApps using RainbowKit and Dynamic.

## Testing

> Skills for smart contract testing strategies, frameworks, and coverage tools.

- [Web3 Smart Contract Testing](https://github.com/wshobson/agents/tree/main/plugins/blockchain-web3/skills/web3-testing) - Comprehensive testing strategies and coverage analysis for Web3 smart contracts.
- [Property-Based Testing](https://github.com/trailofbits/skills/tree/main/plugins/property-based-testing) - Property-based testing guidance for multiple languages and smart contracts.
- [EVM Transaction Debugger](https://github.com/nicofains1/evm-tx-debugger) - Debug failed EVM transactions efficiently using Foundry.

## DeFi & Tokens

> Skills for decentralized finance protocols, token standards, and NFT development.

- [DeFi Protocols Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/defi-protocols) - Development skills for DeFi protocol implementation and integration.
- [NFT Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/nft-development) - NFT smart contract development including ERC-721 and ERC-1155 standards.
- [Crypto Skills](https://github.com/kukapay/crypto-skills) - Collection of cryptocurrency agent skills including EVM blockchain operations, ERC20 token generation, and DeFi yield research.
- [NFT Mint Skill](https://github.com/consensus-hq/nft-mint-skill) - ERC-721 NFT skill for deploying, minting, and transferring NFTs on Base and EVM chains.
- [EVM Wallet Skill](https://github.com/surfer77/evm-wallet-skill) - EVM wallet operations skill for AI agents.
- [8004 Skill](https://github.com/matteoscurati/8004skill) - ERC-8004 on-chain agent economy for registering agents and managing reputation across EVM chains.
- [Bridging](https://github.com/celo-org/agent-skills/tree/main/skills/bridging) - Cross-chain asset bridging between EVM chains covering native bridges and third-party solutions.

## Deployment & Tooling

> Skills for smart contract deployment, migration tools, and development infrastructure.

- [Solidity Contract Verification](https://github.com/bsmocovich/solidity-contract-verification) - Verifying smart contracts on Etherscan, Basescan, and other block explorers.
- [Contract Verification](https://github.com/celo-org/agent-skills/tree/main/skills/contract-verification) - Smart contract source code verification on block explorers using Hardhat and Foundry.

## Related Tools

> MCP servers and complementary tools for Solidity development with Claude.

- [Slither MCP](https://github.com/trailofbits/slither-mcp) - Trail of Bits' Slither static analysis framework as an MCP server for Claude.
- [Foundry MCP Server](https://github.com/PraneshASP/foundry-mcp-server) - MCP server providing Foundry tool integration for Claude Code.
- [Weasel](https://github.com/slvDev/weasel) - Solidity static analyzer with MCP integration for Claude Code, Cursor, and Windsurf.
- [Solodit API Skill](https://github.com/BowTiedSwan/solodit-api-skill) - MCP server for searching smart contract vulnerabilities from Cyfrin Solodit.
- [Foundry MCP (Rust)](https://github.com/0xClandestine/foundry-mcp-rs) - Rust MCP server exposing 170 Foundry tools with RPC discovery for 2400+ networks.
- [EVM MCP Server](https://github.com/mcpdotdirect/evm-mcp-server) - MCP server providing blockchain services across 60+ EVM networks with 22 tools and ENS resolution.
- [EVM MCP Tools](https://github.com/0xGval/evm-mcp-tools) - Blockchain analysis toolkit for smart contract auditing, wallet analysis, and on-chain data fetching.
- [EVM MCP](https://github.com/JamesANZ/evm-mcp) - MCP server providing 20+ EVM JSON-RPC tools for any EVM-compatible node provider.
- [MCP Crypto Wallet EVM](https://github.com/dcSpark/mcp-cryptowallet-evm) - MCP server for EVM wallet operations including creating wallets, checking balances, and sending transactions.
- [Blockchain MCP](https://github.com/lienhage/blockchain-mcp) - MCP server for Ethereum vanity addresses, Cast commands, 4byte lookup, and calldata decoding.
- [Arkham Intelligence Skill](https://github.com/Vyntral/arkham-intelligence-claude-skill) - Arkham Intelligence API integration for on-chain analytics, whale tracking, and smart money analysis.

## How to Install Skills

Claude Code skills extend your AI assistant with specialized knowledge for Solidity development. There are several ways to install them:

### Quick Install

The fastest way to add a skill is with the `npx add-skill` command:

```bash
npx add-skill Smart-Contract-Security
```

### Manual Installation

Clone the skill repository directly into your project's `.claude/skills/` directory:

```bash
git clone https://github.com/author/skill-repo .claude/skills/skill-name
```

### Scope

| Scope | Location | Effect |
|-------|----------|--------|
| Project | `.claude/skills/` | Available in the current project only |
| Global | `~/.claude/skills/` | Available across all projects |

## Contributing

Contributions are welcome! Please read the [contributing guidelines](CONTRIBUTING.md) first.
