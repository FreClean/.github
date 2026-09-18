# FreClean Architecture Contract

Version: 1.0.0

This document is the shared contract for the four active repositories. A pull
request that changes an interface must update this document and the affected
repository tests in the same change.

## Ownership

| Repository | Owns | Must not do |
| --- | --- | --- |
| `FreClean/FreClean` | API, authentication, authorization, product/service catalog, booking/order/payment rules, PostgreSQL writes, audit logs | Expose database credentials to clients |
| `FreClean/freclean-app` | Customer, staff, manager, admin, and owner user experience | Authoritative business rules or direct database access |
| `FreClean/freclean-website` | Public content and approved public API consumption | Direct database access or private API access |
| `FreClean/.github` | Organization policy, reusable CI, issue/PR templates, security governance | Product or business logic |

## API

The core API is the only integration boundary. Versioned routes use `/api/v1`.
Authentication uses bearer JWTs issued and validated by the core API. Clients
must treat authorization failures as authoritative and must not infer access
from UI state or client-supplied roles.

The public website may call explicitly public, read-only endpoints. The app
must call core endpoints for catalog, bookings, orders, and payments.

## Payments

There are exactly three methods: `CRYPTO`, `CARD`, and `CASH`.

- Crypto assets are `CELO` and `USDm`. Verification is server-side and
  fail-closed against chain data, recipient, amount, chain, and confirmations.
- Card payment status comes only from processor verification and a verified,
  replay-protected, idempotent signed webhook.
- Cash can be recorded only by authorized staff and requires reconciliation.
- Client payment status is never authoritative.

## Configuration and deployment

Secrets are supplied through the deployment environment or secret manager.
Only `.env.example` files may be committed. Production uses PostgreSQL, runs
validated migrations before application rollout, exposes a health check, and
supports graceful shutdown. Development/test seed data must never run in
production.

## Compatibility and releases

API changes are additive within a major version. Breaking changes require a
new `/api/vN` version, migration guidance, contract tests, and a coordinated
release. Repository versions follow semantic versioning. The core API is
released before clients that consume a new contract.