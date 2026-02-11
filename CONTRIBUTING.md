# Contributing to Awesome Solidity Skills

Thank you for your interest in contributing! This list curates Claude Code skills for Solidity and EVM smart contract development.

## How to Submit a Skill

1. **Open an issue** using the [Add a Skill](https://github.com/gonzaloetjo/awesome-solidity-skills/issues/new?template=add-skill.yml) template, or
2. **Submit a pull request** directly using the [PR template](https://github.com/gonzaloetjo/awesome-solidity-skills/compare).

## Entry Format

Each skill entry must follow this format:

```markdown
- [Skill Name](url) - Short description of what the skill does. `Author: @githubhandle`
```

- **Name** — clear, descriptive title.
- **URL** — link to the skill page (Skillfish) or GitHub repository.
- **Description** — one sentence, ending with a period.
- **Author** — GitHub handle prefixed with `@`.

## Quality Checklist

Before submitting, please verify:

- [ ] The skill is related to Solidity or EVM smart contract development.
- [ ] The install command works (`npx add-skill <Name>` or manual install).
- [ ] The description accurately reflects the skill's capabilities.
- [ ] The entry is placed in the correct category.
- [ ] The entry follows the format above.
- [ ] There are no duplicate entries in the list.

## Categories

| Category | Scope |
|----------|-------|
| Security & Auditing | Vulnerability detection, audit workflows, secure patterns |
| Development & Architecture | Architecture, best practices, Solidity workflows |
| Testing | Testing strategies, frameworks, coverage |
| DeFi & Tokens | DeFi protocols, token standards, NFTs |
| Deployment & Tooling | Deployment, migrations, dev infrastructure |
| Related Tools | MCP servers and complementary tools |

If your skill doesn't fit an existing category, suggest a new one in your PR.

## Guidelines

- Search existing entries to avoid duplicates.
- One skill per pull request.
- Keep descriptions concise and objective.
- Do not use promotional language.
