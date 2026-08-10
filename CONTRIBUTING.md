# Contributing to FreClean

Thanks for your interest in contributing to a FreClean repository.

## Before you start

1. Check existing issues and open PRs to avoid duplicate work.
2. For a significant change, open an issue first to discuss the approach before writing code.
3. Read the specific repository's `README.md` for its setup, architecture, and any repo-specific conventions.

## The one rule that applies everywhere

FreClean repositories never present a status as more advanced than it actually is — no invented figures, no feature described as live before it's real. See `freclean-docs/whitepaper/24-legal-policy-framework.md` for the full principle. A contribution that violates this (e.g. marking a product "available" without real backing data, or claiming a partnership isn't confirmed) will be asked to change before merge, regardless of how small the change otherwise is.

## Development workflow

1. Fork or branch from `main`.
2. Make your change, following the target repo's existing patterns (e.g. `freclean-api`'s CRUD factory pattern, `freclean-admin`'s config-driven resource pages) rather than introducing a new one for a single case.
3. Add or update tests where the repo has a test suite.
4. Run the repo's lint/typecheck/test scripts locally before opening a PR — they also run in CI, but catching issues locally is faster.
5. Fill out `PULL_REQUEST_TEMPLATE.md` completely.

## Code style

Each repo's linter config (`.eslintrc.json` or equivalent) is the source of truth — run it rather than guessing at style. No repository uses a technology "because it sounds impressive" — see `freclean-payment`'s hand-written Celo client for an example of preferring a small, direct solution over a heavier dependency. Apply the same judgment to new dependencies.

## Security

Do not open a public issue or PR that discloses a security vulnerability. See `SUPPORT.md` and `freclean-security/SECURITY.md`.

## Questions

freclean7@gmail.com
