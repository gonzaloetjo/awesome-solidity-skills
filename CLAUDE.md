# CLAUDE.md

## Repository Overview

This is **awesome-solidity-skills** — a curated [awesome list](https://awesome.re) of Claude Code skills for Solidity and EVM smart contract development.

- **Repository**: `gonzaloetjo/awesome-solidity-skills`
- **License**: CC0-1.0

## File Layout

| File | Role |
|------|------|
| `README.md` | The awesome list itself |
| `CONTRIBUTING.md` | Submission guidelines |
| `.github/workflows/ci.yml` | awesome-lint + markdownlint CI |
| `.github/workflows/links.yml` | Lychee link checker (monthly + on PRs) |
| `.github/ISSUE_TEMPLATE/add-skill.yml` | "Add a Skill" issue form |
| `.github/PULL_REQUEST_TEMPLATE.md` | PR checklist |
| `.lycheeignore` | Domains excluded from link checking |
| `.markdownlint-cli2.jsonc` | Markdownlint config (MD013, MD033, MD041 disabled) |

## README Conventions

- **Entry format**: `- [Name](url) - Description ending with period.`
- **Categories**: Security & Auditing, Development & Architecture, Testing, DeFi & Tokens, Deployment & Tooling, Related Tools
- No `Author:` backtick tags — awesome-lint rejects them as improper punctuation
- No duplicate links across sections (awesome-lint `double-link` rule)
- Table of Contents must **not** include the "Contributing" section
- Heading must be markdown `# Awesome Solidity Skills` (not HTML `<h1>`)

## Quality Checks

Run these before committing changes to `README.md`:

```bash
npx awesome-lint        # must pass
npx markdownlint-cli2 README.md  # must pass (0 errors)
```

## How to Search for New Skills

Proven strategies for discovering Solidity/EVM Claude Code skills, ranked by effectiveness.

### 1. Topic-based search (highest precision)

```bash
gh search repos --topic claude-code-skills --limit 20
gh search repos --topic agent-skills --limit 20
```

### 2. Keyword + domain filtering

```bash
gh search repos "solidity" "skill" --limit 20
gh search repos "evm" "skill" --limit 20
gh search repos "topic:claude-code" "solidity OR evm OR blockchain"
```

### 3. Multi-skill collection repos (high density)

These repos contain many skills in subdirectories — check for new additions:

- `trailofbits/skills` — `plugins/` directory, security-focused
- `celo-org/agent-skills` — `skills/` directory, EVM-focused (foundry, hardhat, wallet)
- `anthropics/skills` — official Anthropic skills (check for new Solidity additions)

### 4. Curated awesome lists to cross-reference

- `VoltAgent/awesome-agent-skills` — 300+ skills, has Solidity/EVM category
- `travisvn/awesome-claude-skills`
- `sickn33/antigravity-awesome-skills` — 700+ skills

### 5. Online registries

- mcpservers.org/claude-skills
- mcpmarket.com/tools/skills

### Skill structure patterns

Recognizing repo layouts helps quickly assess whether a repo contains skills:

- **Single-skill repos**: contain `SKILL.md` or `CLAUDE.md` at root
- **Multi-skill collections**: `plugins/` or `skills/` directory with subdirectories
- **Registry metadata**: `.claude-plugin/marketplace.json`
