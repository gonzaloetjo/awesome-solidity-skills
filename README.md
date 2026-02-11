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

- [Smart Contract Security](https://skillfish.dev/skills/pluginagentmarketplace/Smart-Contract-Security) - Comprehensive security auditing and vulnerability detection for Solidity smart contracts.
- [Solidity Security Patterns](https://skillfish.dev/skills/as4584/Solidity-Security-Patterns) - Security-first development patterns and anti-pattern detection for Solidity.
- [Software Crypto/Web3 Engineering](https://skillfish.dev/skills/vasilyu1983/Software-Crypto-Web3-Engineering) - Full-stack crypto engineering with security-focused Web3 development practices.
- [Solidity Audit Skills](https://github.com/gonzaloetjo/solidity-audit-skills) - Skill to audit Solidity contracts using Claude Code teams.

## Development & Architecture

> Skills for Solidity smart contract architecture, development workflows, and best practices.

- [Solidity Development Expert](https://skillfish.dev/skills/pluginagentmarketplace/Solidity-Development-Expert) - Expert-level Solidity architecture guidance and development best practices.
- [Ethereum Development](https://skillfish.dev/skills/pluginagentmarketplace/Ethereum-Development) - Full-stack Ethereum development including contracts, testing, and deployment.
- [Foundry Solidity Development](https://skillfish.dev/skills/tenequm/Foundry-Solidity-Development) - Modern Foundry 1.5.0 workflow for Solidity development and testing.

## Testing

> Skills for smart contract testing strategies, frameworks, and coverage tools.

- [Web3 Smart Contract Testing](https://skillfish.dev/skills/wshobson/Web3-Smart-Contract-Testing) - Comprehensive testing strategies and coverage analysis for Web3 smart contracts.

## DeFi & Tokens

> Skills for decentralized finance protocols, token standards, and NFT development.

- [DeFi Protocols Development](https://skillfish.dev/skills/pluginagentmarketplace/DeFi-Protocols-Development) - Development skills for DeFi protocol implementation and integration.
- [NFT Development](https://skillfish.dev/skills/pluginagentmarketplace/NFT-Development) - NFT smart contract development including ERC-721 and ERC-1155 standards.

## Deployment & Tooling

> Skills for smart contract deployment, migration tools, and development infrastructure.

- [Hardhat-Deploy Migration](https://skillfish.dev/skills/wighawag/Hardhat-Deploy-Migration) - Migration tooling and deployment management with hardhat-deploy.

## Related Tools

> MCP servers and complementary tools for Solidity development with Claude.

- [Slither MCP](https://github.com/trailofbits/slither-mcp) - Trail of Bits' Slither static analysis framework as an MCP server for Claude.
- [Foundry MCP Server](https://github.com/PraneshASP/foundry-mcp-server) - MCP server providing Foundry tool integration for Claude Code.
- [Blockchain Vulnerability Analyzer MCP](https://skillfish.dev/skills/anthropics/Blockchain-Vulnerability-Analyzer-MCP) - MCP server for automated blockchain vulnerability analysis.

## How to Install Skills

Claude Code skills extend your AI assistant with specialized knowledge for Solidity development. There are several ways to install them:

### Quick Install

The fastest way to add a skill is with the `npx add-skill` command:

```bash
npx add-skill Smart-Contract-Security
```

### Using Skillfish

You can also browse and install skills using [skillfish](https://skillfish.dev):

```bash
npx skillfish install Smart-Contract-Security
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
