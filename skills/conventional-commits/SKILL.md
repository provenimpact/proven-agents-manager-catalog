---
name: conventional-commits
description: Guides agents to write Conventional Commits messages with the correct type, optional scope, and optional breaking-change indicators. Use when drafting or validating commit messages for projects that rely on Conventional Commits for release automation or changelogs.
license: MIT
---

## Purpose
Help agents produce commit messages that conform to the Conventional Commits 1.0.0 spec.

## When to use
- User asks for a commit message
- Agent needs to validate or correct a commit message format
- Project follows Conventional Commits and commit types impact release automation

## Core format
Use: `<type>[optional scope][!]: <description>`

## Body guidance
Prefer a body when it adds clarity. Size the body to the change: small changes can be brief, larger changes can be more detailed. The body should explain the why/impact, not restate the title.

## Breaking changes
Indicate breaking changes with either:
- `!` before the colon in the header, or
- A `BREAKING CHANGE:` footer

## Types
- Required: `feat`, `fix`
- Common optional: `docs`, `chore`, `refactor`, `test`, `perf`, `ci`, `build`, `style`, `revert`

## Examples
- `feat(parser): add array support`
- `fix: handle empty input`
- `feat!: drop legacy config format`
- `chore!: remove Node 6 support`

## References
See `references/conventional-commits-1.0.0.md` for the full specification details.
