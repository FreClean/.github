# FreClean

Professional cleaning services, cleaning products, fragrance solutions,
entrepreneurship, and digital commerce.

**Founded in Haiti. Rooted in Léogâne, Ouest. Building toward the Caribbean.**

## About FreClean

FreClean is a Haitian cleaning and consumer-products business founded by
Johnny Dubic on April 16, 2025. The business focuses on professional cleaning
services, locally developed products, fragrance and scented products,
hospitality and commercial solutions, and practical entrepreneurship
opportunities.

## What We Do

- Residential cleaning
- Commercial cleaning
- Hospitality and Airbnb cleaning
- Specialized cleaning
- Cleaning products
- Fragrance and scented products
- Entrepreneurship and business opportunities

## Official CeloHT Partnership

**Official CeloHT Partner**

FreClean is an official CeloHT partner.

FreClean is an independent Haitian cleaning and consumer-products business and
an official CeloHT partner. The organizations remain independent while
collaborating on relevant digital-payment, entrepreneurship, technology, and
community-impact initiatives. CeloHT does not own or control FreClean, and
FreClean does not own or control CeloHT.

- [CeloHT website](https://celoht.com/)
- [CeloHT GitHub organization](https://github.com/Celo-HaiTi/CeloHT)
- [CeloHT dApp](https://app.celoht.com/)

## Digital Payments

FreClean's public website currently displays manual USDT payment instructions
for supported networks, including Celo. This is not an authenticated online
checkout, and a button click, dApp redirect, or customer-submitted transaction
hash does not confirm payment.

FreClean Core contains server-side USDT verification for its supported
networks. The Core payment documentation requires production RPC, token,
receiving-address, and wallet-ownership checks before enabling automated
payments. The live production configuration is not available in this
organization repository, and the website does not yet implement the complete
checkout flow.

The CeloHT dApp handoff is a separate payment route, not a USDT payment
rail. Core has no CeloHT settlement callback or verifier, so a handoff remains
pending until a server-side settlement integration is implemented. The
current public CeloHT dApp repository documents a Celo Sepolia testnet pilot;
it does not establish a production USDT route for FreClean.

When Core verifies a supported USDT payment, confirmation must come from the
server after checking the selected network, transaction hash, recipient,
asset, amount, transaction status, and required confirmations. A hash alone is
not proof of payment.

Traditional payment arrangements may include cash for eligible transactions
and card arrangements where available; confirm availability directly with
FreClean. Online card checkout is not confirmed.

FreClean does not issue its own cryptocurrency or native token.

## Technology

| Repository | Purpose |
|---|---|
| [FreClean](https://github.com/FreClean/FreClean) | Canonical Core backend, API, database, and business logic |
| [freclean-website](https://github.com/FreClean/freclean-website) | Official public website |
| [freclean-app](https://github.com/FreClean/freclean-app) | Customer, staff, and admin application |
| [.github](https://github.com/FreClean/.github) | Organization policies, templates, workflows, security configuration, and public documentation |

The architecture is **Core API → App → Website → CI/CD**. Core owns business
rules, data writes, authorization, and authoritative payment states.

## Security

FreClean's engineering standards include:

- Server-side authorization and role-based access control (RBAC)
- Secure authentication and secret management
- Server-side payment verification and fail-closed validation
- Production configuration validation
- Protected CI/CD workflows
- Responsible vulnerability disclosure

Never publish private keys, wallet credentials, API keys, database credentials,
JWT secrets, or production environment variables.

## Transparency

FreClean does not present unverified revenue, user counts, transaction
volumes, impact statistics, testimonials, certifications, or partnerships as
facts. Plans and pending work should be distinguished from verified current
capabilities.

## Legal & Business Development

FreClean is continuing to formalize its legal, tax, regulatory, banking,
insurance, and contractual infrastructure as the business grows. This does
not represent a claim that any pending registration or approval is complete.

## Location

- Founded in Haiti.
- Rooted in Léogâne, Ouest.
- Building toward the Caribbean.

## Contact

- Website: [freclean.com](https://freclean.com/)
- Email: [freclean7@gmail.com](mailto:freclean7@gmail.com)
- GitHub: [FreClean](https://github.com/FreClean)
- Phone: [+50946128022](tel:+50946128022)
- Founder: Johnny Dubic

For contribution guidance, see [CONTRIBUTING.md](../CONTRIBUTING.md),
[CODE_OF_CONDUCT.md](../CODE_OF_CONDUCT.md), and [SECURITY.md](../SECURITY.md).
