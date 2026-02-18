# pram-catalog — Proven Agents Catalog

[![CI](https://github.com/provenimpact/proven-agents-manager-catalog/actions/workflows/ci.yaml/badge.svg)](https://github.com/provenimpact/proven-agents-manager-catalog/actions/workflows/ci.yaml)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](LICENSE)

Curated agent and skill definitions for [pram](https://github.com/provenimpact/proven-agents-manager). Pick a team, run `pram use <team>`, and the right agents and skills are deployed to your [OpenCode](https://github.com/opencode-ai/opencode) configuration.

## Teams

| Team | Default | Agents | Description |
|------|---------|--------|-------------|
| `openspec-dev` | yes | ada-spec-planner, kai-implementer | Spec-driven planning and development using [OpenSpec](https://openspec.dev/) |
| `peer-review` | | riley-review-lead, sam-security-analyst | Code quality, security, and compliance review |

Both teams share the `conventional-commits` skill.

## Catalog Structure

```
catalog.yaml              # Catalog metadata (api_version, name, version)
agents/
  ada-spec-planner.md     # OpenSpec planning lead (primary)
  kai-implementer.md      # Code implementer (subagent)
  riley-review-lead.md    # Code review lead (primary)
  sam-security-analyst.md # Security/quality analyst (subagent)
skills/
  conventional-commits/
    SKILL.md              # Conventional Commits guidance
    references/           # Full specification reference
teams/
  openspec-dev.yaml       # Default team
  peer-review.yaml
```

## Install

### Via Homebrew (with pram)

```sh
brew install provenimpact/tap/pram
```

This installs both `pram` and `pram-catalog` as a dependency.

### Local Development

Point `pram` at a local clone:

```sh
git clone https://github.com/provenimpact/proven-agents-manager-catalog.git
export PRAM_CATALOG_DIR=./proven-agents-manager-catalog
pram list
```

## Validation

The catalog is validated by `pram` on every CI run. To validate locally:

```sh
PRAM_CATALOG_DIR=. pram list --json
```

## Release

1. Update `version` in `catalog.yaml`
2. Commit and tag: `git tag v<version>`
3. Push the tag: `git push origin v<version>`
4. The release workflow validates the catalog, verifies the tag matches the catalog version, creates a versioned archive, and publishes a GitHub Release.

## License

[Apache 2.0](LICENSE)
