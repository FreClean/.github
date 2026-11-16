# Security Policy

## Reporting a vulnerability

If you discover a security vulnerability in any FreClean repository, please report it privately to **freclean7@gmail.com** rather than opening a public issue. Include steps to reproduce, the affected repository, and, if possible, an assessment of impact and potential blast radius.

We aim to acknowledge reports within 5 business days. We may request additional details and will coordinate remediation and disclosure responsibly.

## Required security posture

All FreClean repositories must implement and maintain the following baseline controls:

- No secrets committed to source control
- No hardcoded credentials, tokens, or production URLs
- Server-side validation and server-side authorization for all privileged actions
- Rate limiting and abuse protections for authentication, payment, and public-facing write endpoints
- Safe dependency management with regular updates and automated scanning
- Secret scanning and workflow validation in CI
- Secure defaults for sessions, cookies, JWTs, and webhooks
- Protection against injection, XSS, CSRF, SSRF, IDOR, privilege escalation, and replay attacks
- Fail-closed handling for payment, product eligibility, and compliance decisions

## External review requirements

The following remain external actions until verified by qualified professionals:

- legal review for jurisdiction-specific terms and consumer protection compliance
- tax and VAT/GST treatment by registered advisors or providers
- independent review of payment verification and reconciliation controls
- product compliance and safety review for regulated or physical goods
- security audit and penetration testing by an independent team

## Security incident handling

Security-relevant findings must be treated as operational incidents and must be recorded with at least:

- affected system
- severity
- owner
- evidence
- containment action
- remediation status
- customer or legal impact assessment where required

## Scope

This policy applies to the FreClean organization repositories and all associated infrastructure, workflows, application code, and external service integrations.
