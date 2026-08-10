# .github

FreClean's org-wide GitHub configuration: the organization profile page, issue/PR templates, contribution guidelines, code of conduct, support policy, and reusable starter workflows — all inherited by every `freclean-*` repository that doesn't define its own.

## Contents

| Path | Purpose |
|---|---|
| `profile/README.md` | Shown on the FreClean GitHub organization homepage |
| `ISSUE_TEMPLATE/` | Bug report and feature request forms; blank issues disabled in favor of these |
| `PULL_REQUEST_TEMPLATE.md` | Default PR checklist for every repo |
| `CONTRIBUTING.md` | How to propose a change, across any repo |
| `CODE_OF_CONDUCT.md` | Expected behavior for anyone interacting with FreClean's repositories |
| `SUPPORT.md` | Where to go for help vs. where to report a bug vs. a security issue |
| `workflow-templates/` | Reusable GitHub Actions starter workflows other repos can adopt from the Actions tab |

## How GitHub uses this repo

A `.github` repository at the organization level provides defaults automatically to every other repo in the org that doesn't define its own version of the same file — see [GitHub's documentation on `.github` repositories](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file-for-your-organization) for the mechanics. FreClean repos with their own `SECURITY.md` (e.g. `freclean-api`, `freclean-payment`, `freclean-dapp`) intentionally override this repo's org-wide security policy (`freclean-security`) with repo-specific detail — that's expected, not a duplication bug.

## License

Not provided.
