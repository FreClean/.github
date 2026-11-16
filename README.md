# FreClean Organization Governance

This repository is the governing control plane for the FreClean organization.
It defines the production architecture, repository boundaries, release gates,
security policy, and operational standards for the four active repositories.

FreClean is an independent Haitian cleaning and consumer-products business and
an official CeloHT partner. The organizations remain independent.

## Active repository architecture

| Repository | Production role | Must not do |
|---|---|---|
| [FreClean/FreClean](https://github.com/FreClean/FreClean) | Core backend, API, PostgreSQL, auth, authorization, orders, payments, compliance, audit | Bypass business rules, write database data from the frontend, or expose secrets |
| [FreClean/freclean-app](https://github.com/FreClean/freclean-app) | Customer, staff, manager, admin, and owner application experience | Direct PostgreSQL access or authoritative business logic |
| [FreClean/freclean-website](https://github.com/FreClean/freclean-website) | Public website, public discovery, and approved public API consumers | Direct PostgreSQL access or private core internals |
| [FreClean/.github](https://github.com/FreClean/.github) | Shared governance, CI/CD, security, templates, and architecture controls | Product runtime logic |

See [architecture-contract.md](architecture-contract.md) for the authoritative contract.

The public organization profile is available at [profile/README.md](profile/README.md).

## Production controls in this repository

- Shared CI workflow standards for lint, typecheck, tests, build, and audit gates
- Security reporting and disclosure guidance
- Secret-scanning and repository policy enforcement
- Architecture and compatibility policy for Core/API boundaries
- Required external-review status handling for legal, tax, payment, and regulatory requirements

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md), and [SECURITY.md](SECURITY.md) for contribution and disclosure requirements.

## External dependencies and blockers

This repository does not contain the product runtimes or production infrastructure for the other three repositories. Any runtime implementation remains in the dedicated repositories and requires their own production-ready pass before a full platform launch.
