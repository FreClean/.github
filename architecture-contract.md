# FreClean Architecture Contract

Version: 1.1.0

This document is the shared contract for the four active repositories. A pull request that changes an interface must update this document and the affected repository tests in the same change.

## Ownership

| Repository | Owns | Must not do |
| --- | --- | --- |
| `FreClean/FreClean` | API, authentication, authorization, product/service catalog, booking/order/payment rules, PostgreSQL writes, audit logs, compliance state, and tax/jurisdiction evaluation | Expose database credentials to clients or authoritatively trust a frontend-supplied value |
| `FreClean/freclean-app` | Customer, staff, manager, admin, and owner user experience, API client integration, workflows, and UI state | Enforce business rules locally, perform direct database access, or bypass core authorization |
| `FreClean/freclean-website` | Public content, public discovery, legal center, consent management, and approved public API consumption | Direct database access, private API access, or bypass server-side business rules |
| `FreClean/.github` | Organization policy, reusable CI, issue/PR templates, security governance, architecture controls, and release gates | Product or business logic |

## Core authority

`FreClean/FreClean` is the authoritative business and data layer. Only Core may:

- write production database data
- enforce business rules
- verify payments and issue authoritative payment/order states
- authorize privileged operations
- determine product and country eligibility
- determine tax/compliance state
- maintain audit records

The website and app must never bypass Core.

## Database boundary

Only Core communicates directly with PostgreSQL. The website must never connect directly to PostgreSQL. The app must never connect directly to PostgreSQL.

## API contract

The Core API is the only integration boundary. Versioned routes use `/api/v1` and may only evolve with a coordinated major-version change.

Requirements:

- Request validation and response schemas are required
- Authentication is bearer JWT and must be validated server-side by Core
- Authorization decisions are server-side only
- Client-supplied role, payment status, totals, or permissions are never authoritative
- Public web pages may call only explicitly public read-only endpoints
- The app must call Core for catalog, orders, bookings, payments, and auth flows
- Error payloads must be consistent and non-leaky

## Payments

There are exactly three payment methods: `CRYPTO`, `CARD`, and `CASH`.

- Crypto assets are `CELO` and `USDm` and require server-side verification against chain state, recipient, amount, currency, and confirmations
- Card payment status must come from processor verification and signed replay-protected webhook events
- Cash can be recorded only by authorized staff and must include reconciliation and audit records
- Client-side `paid`, totals, order state, or transaction status are never authoritative

## Configuration and deployment

- Secrets are supplied through the deployment environment or secret manager
- Only `.env.example` files may be committed to source control
- Production uses PostgreSQL and validated migrations before rollout
- Health and readiness endpoints must exist in services that expose network traffic
- Development/test seed data must never run in production
- Required production configuration must fail fast at startup

## Compatibility and releases

- API changes are additive within a major version
- Breaking changes require a new `/api/vN` contract, migration guidance, contract tests, and coordinated release timing
- Repository versions follow semantic versioning
- The Core API is released before clients that consume a new contract
- Cross-repository compatibility must be validated through contract tests before release

## Security and compliance

- Frontend code is untrusted
- Authorization must be enforced server-side
- Payment and compliance logic must be fail-closed
- Security incidents, privacy incidents, and payment anomalies must be auditable and tracked
- Legal, tax, customs, and payment-provider approvals remain external review items until verified by qualified professionals

## Status labels

Use only the statuses below:

- `IMPLEMENTED`
- `VERIFIED-INTERNAL`
- `EXTERNAL-REVIEW-REQUIRED`
- `EXTERNAL-ACTION-REQUIRED`

A repo may not claim a legal, compliance, tax, or payment status beyond what an external qualified professional has verified.
