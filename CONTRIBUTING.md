# Contributing to FreClean

Thank you for your interest in contributing.

## Before opening a pull request

1. Work in the appropriate official repository:
   - [FreClean](https://github.com/FreClean/FreClean) — canonical Core backend,
     API, database, and business logic
   - [freclean-website](https://github.com/FreClean/freclean-website) — public
     website
   - [freclean-app](https://github.com/FreClean/freclean-app) — customer,
     staff, and admin application
   - [.github](https://github.com/FreClean/.github) — organization policies,
     workflows, templates, and public documentation
2. Create a focused branch and keep changes within that repository's
   responsibility.
3. Add or update relevant tests for behavior changes and run the checks
   provided by the repository.
4. Update directly related documentation, API contracts, and examples when
   behavior or public interfaces change.
5. Open a pull request with a clear summary, motivation, test results, and
   deployment impact. Changes require maintainer review before merge; do not
   merge your own change without review.

## Sensitive changes

- Request security review for changes to authentication, authorization,
  secrets, personal data, payment verification, CI/CD permissions, or
  production configuration.
- Document payment-method, asset, network, verification, status, and failure
  behavior changes. Never trust a client-side payment status or expose
  credentials.
- Database changes must use the repository's migration discipline. Keep
  migrations ordered and reviewable; test them against a clean schema and a
  production-like schema copy where applicable. Document compatibility and
  rollback considerations.
- Production changes require review before deployment. State the configuration
  changes, rollout and rollback plan, and any operational prerequisites in the
  pull request.
- Never include secrets, production environment values, private keys, or
  customer credentials in a commit, issue, or pull request.

Please review `CODE_OF_CONDUCT.md` and `SECURITY.md` before contributing.
