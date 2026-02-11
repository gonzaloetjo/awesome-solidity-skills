# Security Audit Report

**Date:** 2026-02-11
**Scope:** All 52 skills/tools listed in the awesome-solidity-skills README
**Method:** Multi-agent review of SKILL.md / README.md from each repository via GitHub API
**Auditors:** 4 parallel agents (A–D), compiled by team lead

## Methodology

Each skill was evaluated against 8 security criteria:

1. **Arbitrary command execution** — runs shell commands, downloads scripts
2. **Private key / seed phrase handling** — touches wallets, signs transactions
3. **Network requests** — calls external APIs, sends data outbound
4. **Mainnet interaction** — deploys/transacts on mainnet vs testnet
5. **File system access** — reads/writes outside the project directory
6. **Dependency risk** — installs/requires unfamiliar external binaries
7. **Permission scope** — requests overly broad Claude Code permissions
8. **Transparency** — source fully readable and auditable

## Rating Scale

| Rating | Meaning |
|--------|---------|
| 5 | No concerns — read-only guidance, no commands or key handling |
| 4 | Low risk — executes standard dev tooling (forge, hardhat, npm) |
| 3 | Moderate — interacts with external APIs, requires API keys |
| 2 | Elevated — handles private keys, signs transactions, or accesses mainnet |
| 1 | Serious — executes arbitrary commands, downloads remote scripts, or could exfiltrate data |
| N/A | Unauditable — source not publicly inspectable |

---

## Security & Auditing

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [Smart Contract Security](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/smart-contract-security) | 4 | Read-only security guidance with code patterns for vulnerability detection; recommends running Slither, Mythril, and Foundry locally. No keys or external APIs. |
| [Solidity Audit Skills](https://github.com/gonzaloetjo/solidity-audit-skills) | 4 | Runs Slither/Forge (standard tools), multi-agent architecture. Outputs to `docs/audit/` within project. No network, no keys. |
| [Building Secure Contracts](https://github.com/trailofbits/skills/tree/main/plugins/building-secure-contracts) | 5 | Trail of Bits. 11 specialized security skills. Token integration analyzer may make read-only RPC calls. No keys, no deployment. |
| [Entry Point Analyzer](https://github.com/trailofbits/skills/tree/main/plugins/entry-point-analyzer) | 5 | Trail of Bits. Pure static code analysis. Reads source, generates classification report. No commands, no network, no keys. |
| [Spec-to-Code Compliance](https://github.com/trailofbits/skills/tree/main/plugins/spec-to-code-compliance) | 5 | Trail of Bits. Documentation-to-code analysis. Strong anti-hallucination rules. No external interactions. |
| [Audit Context Building](https://github.com/trailofbits/skills/tree/main/plugins/audit-context-building) | 5 | Trail of Bits. Pure reasoning methodology — reads code, builds mental model. No actions beyond reading. Safest skill type. |
| [Differential Review](https://github.com/trailofbits/skills/tree/main/plugins/differential-review) | 5 | Trail of Bits. Git history analysis with `git diff`/`git blame`. Standard read-only git commands only. |
| [Fix Review](https://github.com/trailofbits/skills/tree/main/plugins/fix-review) | 4 | Trail of Bits. Verifies audit fix remediation. Notable: Google Drive download feature (user-initiated, optional `gdrive` CLI). |
| [Variant Analysis](https://github.com/trailofbits/skills/tree/main/plugins/variant-analysis) | 4 | Trail of Bits. Runs ripgrep/Semgrep/CodeQL (standard security tools). CodeQL may download language packs. |
| [Static Analysis](https://github.com/trailofbits/skills/tree/main/plugins/static-analysis) | 4 | Trail of Bits. Runs CodeQL + Semgrep. Note: CodeQL database creation executes build commands (inherent to CodeQL). |
| [SCV Scan](https://github.com/kadenzipfel/scv-scan) | 5 | Self-contained vulnerability scanner. Uses only grep/ripgrep + bundled reference files. No dependencies, no network. |
| [Solidity Audit Skill](https://github.com/yolodolo42/solidity-audit-skill) | 4 | MCP server + install script. Install modifies `~/.claude/mcp.json`. MCP runs `forge build`/`forge test`. Code is auditable with CI. |
| [Solidity Security Audit Skill](https://github.com/mariano-aguero/solidity-security-audit-skill) | 5 | Comprehensive 5-phase audit with 14 reference files. Runs Slither/Forge/Aderyn when available, falls back to manual. No network, no keys. |

## Development & Architecture

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [Solidity Development Expert](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/solidity-development) | 4 | Development patterns and Foundry CLI guidance (forge build, test, fmt). Purely local dev tooling with no key handling or external API calls. |
| [Ethereum Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/ethereum-development) | 3 | Gas optimization and EVM internals. Includes code examples for sending EIP-1559 transactions via viem and reading mainnet storage via RPC environment variables. |
| [Foundry Solidity Development](https://github.com/tenequm/claude-plugins/tree/main/foundry-solidity) | 3 | Comprehensive Foundry guide covering forge, cast, anvil, and deploy scripts. Includes `--private-key $KEY` in cast examples and `--broadcast` deployment commands. Keys referenced via environment variables only. |
| [Arbitrum dApp Skill](https://github.com/hummusonrails/arbitrum-dapp-skill) | 3 | `bash <(curl -s ...)` install pattern is supply-chain risk. Uses `clawhub` third-party installer. Private key via env var for deployment. Mainnet path exists but not default. |
| [Ethereum Dev Skill](https://github.com/minimalsm/ethereum-dev-skill) | 4 | Purely instructional markdown with code patterns. References standard tools (viem, wagmi, Foundry). Good security practices (env vars, simulation-before-write). |
| [Solidity Agent Kit](https://github.com/0xlayerghost/solidity-agent-kit) | 3 | 7 skills with `[AUTO-INVOKE]` auto-activation. `npx skills` third-party installer. Good private key protection guidance but `--private-key $PRIVATE_KEY` in deploy templates. No explicit mainnet safeguards. |
| [ContractKit](https://github.com/HCS412/contractkit) | 3 | Claude Code plugin with deploy/test commands. Security disclaimer warns against mainnet without audit. Plugin implementation (`plugins/`, `tools/`) not fully inspected. |
| [EVM Agent Skills](https://github.com/SkandaBhat/evm-agent-skills) | **1** | **Defaults to Ethereum mainnet.** Python wrapper executes `cast` for broad RPC access including `eth_sendTransaction` and `eth_sendRawTransaction`. Transaction signing and broadcasting on mainnet. Very broad permissions. |
| [Onchain TypeScript Skills](https://github.com/0xSardius/onchain-typescript-skills) | 5 | Instructional TypeScript patterns for viem/wagmi. No commands executed. Emphasizes `as const` type safety and simulate-before-write. |
| [Ember Skills](https://github.com/emberdragonc/ember-skills) | 3 | Etherscan V2 API calls with user's API key. Creates custom verification scripts. References to unclear AI auditor bots (`@clawditor`, `@dragon_bot_z`). |
| [OP Stack Skills](https://github.com/pauldowman/op-claude-plugins) | 3 | Reads from `$OP_WORKBENCH_PATH` and `$K8S_REPO_PATH` (infrastructure repos outside project). 14 individual skill files not fully audited. Primarily read-only chain queries. |
| [EVM Foundry](https://github.com/celo-org/agent-skills/tree/main/skills/evm-foundry) | 4 | Celo-org. Standard Foundry guide. Mainnet deployment documented as default path (Celo forno.celo.org). Private key via env var. |
| [EVM Hardhat](https://github.com/celo-org/agent-skills/tree/main/skills/evm-hardhat) | 4 | Celo-org. Standard Hardhat guide. Same profile as EVM Foundry. Uses dotenv for key management. |
| [Viem](https://github.com/celo-org/agent-skills/tree/main/skills/viem) | 5 | Celo-org. Pure instructional TypeScript patterns. Uses `window.ethereum` (browser wallet), no raw private keys. |
| [Wagmi](https://github.com/celo-org/agent-skills/tree/main/skills/wagmi) | 5 | Celo-org. Pure instructional React hooks patterns. Browser wallet connection only, no key handling. |
| [EVM Wallet Integration](https://github.com/celo-org/agent-skills/tree/main/skills/evm-wallet-integration) | 4 | Celo-org. Wallet connection via RainbowKit/Dynamic. No raw key handling. Requires Reown/Dynamic project IDs. |

## Testing

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [Web3 Smart Contract Testing](https://github.com/wshobson/agents/tree/main/plugins/blockchain-web3/skills/web3-testing) | 3 | Hardhat and Foundry testing patterns. References `process.env.PRIVATE_KEY` in network config, mainnet RPC URLs for fork testing, and Etherscan/CoinMarketCap API keys via environment variables. |
| [Property-Based Testing](https://github.com/trailofbits/skills/tree/main/plugins/property-based-testing) | 5 | Trail of Bits. Knowledge-only skill providing testing patterns. No code execution, no network, no keys. |
| [EVM Transaction Debugger](https://github.com/nicofains1/evm-tx-debugger) | 4 | Read-only debugging with `cast` and `curl` to Blockscout APIs. All operations query blockchain state without modifying it. Dynamic command construction from user input. |

## DeFi & Tokens

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [DeFi Protocols Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/defi-protocols) | 4 | DeFi protocol development patterns (AMM math, Chainlink oracles, flash loans). Primarily read-only guidance. References mainnet addresses for read-only cast calls but no key handling. |
| [NFT Development](https://github.com/pluginagentmarketplace/custom-plugin-blockchain/tree/main/skills/nft-development) | 4 | NFT standards (ERC-721, ERC-721A, ERC-1155), metadata design, and on-chain SVG generation. Includes OpenSea API curl for metadata refresh but no key handling or transaction signing. |
| [Crypto Skills](https://github.com/kukapay/crypto-skills) | 2 | 6-skill collection. Token Minter deploys contracts (requires signing). EVM Swiss Knife performs write operations. Multiple external APIs (DexScreener, Binance, RSS feeds). No explicit testnet safeguards. Individual SKILL.md files not all inspected. |
| [NFT Mint Skill](https://github.com/consensus-hq/nft-mint-skill) | 3 | Deploys/mints/transfers NFTs via shell scripts. Good safeguards: no raw private keys (keystore only), mainnet requires `--yes-mainnet`, HTTPS-only RPCs. |
| [EVM Wallet Skill](https://github.com/surfer77/evm-wallet-skill) | **1** | **Generates and stores private key at `~/.evm-wallet.json`.** AI agent gets full hot wallet control. Mainnet-by-default across 6 chains. Arbitrary contract interaction via Odos aggregator. Highest financial risk in this category. |
| [8004 Skill](https://github.com/matteoscurati/8004skill) | 3 | WalletConnect v2 signing (never holds keys locally). Double confirmation for writes. Thorough security section with prompt injection warnings. IPFS credential handling noted. |
| [Bridging](https://github.com/celo-org/agent-skills/tree/main/skills/bridging) | 4 | Celo-org. Reference/documentation skill for cross-chain bridging. Provides code patterns and contract addresses. Uses `window.ethereum` browser wallet. |

## Deployment & Tooling

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [Solidity Contract Verification](https://github.com/bsmocovich/solidity-contract-verification) | 4 | Verification-only (no on-chain transactions). Calls Etherscan V2 API with user's API key. Well-documented with troubleshooting guide. |
| [Contract Verification](https://github.com/celo-org/agent-skills/tree/main/skills/contract-verification) | 4 | Celo-org. Multi-method verification (Hardhat, Foundry, Celoscan, Blockscout, Sourcify). Note: includes `forge create` example with `--private-key` flag. |

## Related Tools

| Skill | Rating | Key Findings |
|-------|--------|-------------|
| [Slither MCP](https://github.com/trailofbits/slither-mcp) | 4 | Trail of Bits. Wraps Slither as MCP server. Read-only analysis. Opt-out telemetry (does not collect project data). Writes cache to `artifacts/project_facts.json`. |
| [Foundry MCP Server](https://github.com/PraneshASP/foundry-mcp-server) | **1** | **Executes arbitrary Forge scripts, sends mainnet transactions with configured private key, creates Solidity files.** Workspace at `~/.mcp-foundry-workspace`. README warns about LLM hallucination risks but does not enforce testnet-only. |
| [Weasel](https://github.com/slvDev/weasel) | 3 | Rust static analyzer. `curl \| bash` install pattern (checksums provided). MCP tools are read-only. Skills generate PoC exploit files. |
| [Solodit API Skill](https://github.com/BowTiedSwan/solodit-api-skill) | 4 | Read-only MCP server querying Cyfrin Solodit vulnerability database. Narrow scope, rate-limited. No blockchain interaction. |
| [Foundry MCP (Rust)](https://github.com/0xClandestine/foundry-mcp-rs) | 3 | 170+ Foundry tools. **Notable: configurable security restrictions** — blocks `--private-key`, `--mnemonic`, `--broadcast` by default. Chisel REPL can execute arbitrary Solidity. Strongest default safety of Foundry MCP servers. |
| [EVM MCP Server](https://github.com/mcpdotdirect/evm-mcp-server) | **1** | **Private key/mnemonic via env vars. 60+ mainnet chains. Token transfers, contract writes, EIP-712 signing.** HTTP mode binds to `0.0.0.0` (network exposure). Very broad capabilities. |
| [EVM MCP Tools](https://github.com/0xGval/evm-mcp-tools) | 3 | Read-only blockchain analysis. Multiple third-party APIs (Moralis, Codex, RapidAPI). Includes Twitter search — unusual for EVM toolkit, potential data flow concern. |
| [EVM MCP](https://github.com/JamesANZ/evm-mcp) | 3 | JSON-RPC gateway with 20+ methods. `eth_sendRawTransaction` broadcasts pre-signed txns but does not handle keys directly. Primarily read-only. |
| [MCP Crypto Wallet EVM](https://github.com/dcSpark/mcp-cryptowallet-evm) | **1** | **Full wallet lifecycle management.** `wallet_get_private_key` and `wallet_get_mnemonic` expose secrets to LLM context. Creates wallets, signs/sends transactions. Highest key exposure risk in entire audit. |
| [Blockchain MCP](https://github.com/lienhage/blockchain-mcp) | **1** | **Private key passed as plaintext tool parameter** — flows through LLM context. Sends transactions on 7 mainnets. Vanity address generation creates keys visible to LLM. |
| [Arkham Intelligence Skill](https://github.com/Vyntral/arkham-intelligence-claude-skill) | 4 | Read-only Arkham Intelligence API integration. `Bash(curl:*)` permission broader than necessary but instructions are well-scoped. No keys, no transactions. |

---

## Summary Statistics

| Metric | Count |
|--------|-------|
| **Total entries audited** | **52** |
| GitHub-hosted (auditable) | 52 |

### Rating Distribution

| Rating | Count | Percentage |
|--------|-------|-----------|
| 5 — No concerns | 11 | 21% |
| 4 — Low risk | 20 | 38% |
| 3 — Moderate | 14 | 27% |
| 2 — Elevated | 1 | 2% |
| 1 — Serious | 6 | 12% |

### Highest-Risk Entries (Rating 1)

These 6 entries warrant careful review before installation:

1. **[EVM Agent Skills](https://github.com/SkandaBhat/evm-agent-skills)** — Defaults to Ethereum mainnet with transaction signing/broadcasting
2. **[EVM Wallet Skill](https://github.com/surfer77/evm-wallet-skill)** — AI-controlled hot wallet with private key stored at `~/.evm-wallet.json`
3. **[Foundry MCP Server](https://github.com/PraneshASP/foundry-mcp-server)** — Arbitrary Forge script execution with mainnet transaction capability
4. **[EVM MCP Server](https://github.com/mcpdotdirect/evm-mcp-server)** — Private key/mnemonic handling across 60+ mainnet chains, binds to 0.0.0.0
5. **[MCP Crypto Wallet EVM](https://github.com/dcSpark/mcp-cryptowallet-evm)** — Full wallet lifecycle; exposes private keys and mnemonics to LLM context
6. **[Blockchain MCP](https://github.com/lienhage/blockchain-mcp)** — Private key passed as plaintext tool parameter through LLM

### Key Observations

1. **Trail of Bits skills (9 entries)** are consistently the safest — all rated 4–5. Published by a top-tier security firm with transparent, well-scoped tooling.

2. **Celo-org skills (7 entries)** are also well-structured and low-risk (rated 4–5). Purely instructional patterns from a reputable organization.

3. **MCP servers carry the highest risk** — 4 of the 6 rating-1 entries are MCP servers. MCP servers run with elevated permissions and can handle private keys, sign transactions, and make network requests.

4. **Private key handling** is the primary differentiator between safe and dangerous skills. Skills that never touch keys (audit tools, instructional guides) are consistently safe. Skills that accept or generate private keys (wallet managers, deployment tools) carry serious risk.

5. **Common safe pattern:** Most low-risk skills run standard security tools (Slither, Forge, Echidna, CodeQL, Semgrep) when available and fall back to manual analysis when not.

6. **Common risk pattern:** `bash <(curl ...)` install scripts, `--private-key` CLI flags, and defaulting to mainnet rather than testnet.
