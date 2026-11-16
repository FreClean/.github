# Security Policy

## Report privately

Report suspected vulnerabilities privately to **freclean7@gmail.com**. Do not
open a public issue or pull request with vulnerability details. GitHub's
private vulnerability reporting may also be used if it is enabled for the
affected repository.

Include the affected repository and component, a concise description, impact,
and safe reproduction guidance. Use a test account and sanitized data where
possible. FreClean will coordinate follow-up and responsible disclosure.

Do not include passwords, private keys, seed phrases, access tokens, session
cookies, production credentials, or personal customer data in a report. If
evidence requires sensitive data, describe what is available and request a
secure way to provide it instead of sending it in plain text.

## Sensitive reports

- **Payment vulnerabilities:** Report the affected flow, network, and observed
  behavior privately. Do not include customer payment data, credentials, or
  unredacted logs. A transaction hash or redirect by itself does not establish
  that a payment is valid.
- **Authentication vulnerabilities:** Never share live passwords, JWTs,
  cookies, recovery codes, or session tokens. Explain the issue using
  synthetic accounts and redacted requests.
- **Exposed secrets:** Do not copy the secret into an issue, email, log, or
  patch. Revoke or rotate it through the responsible service, then privately
  report where it was exposed. Removing it from the latest commit does not
  remove it from repository history.
- **Production incidents:** Report the affected service, approximate time and
  time zone, observed impact, and containment already taken. Keep customer
  identities, credentials, and sensitive operational details out of public
  channels.

For an active production risk, contact FreClean privately at the address above
with a concise, non-sensitive subject line. Do not attempt to access data,
accounts, or systems beyond what is necessary to validate the report.

## Required security posture

All FreClean repositories must implement and maintain the following baseline controls:

- No secrets committed to source control
- No hardcoded credentials or tokens; production endpoints must be explicit,
  validated, and appropriate for the environment
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
- payment processor approval and webhook verification
- product compliance and safety review for regulated or physical goods
- security audit and penetration testing by an independent team

## Security incident handling

Security-relevant findings and production security incidents must be tracked
through remediation. Incident records should include, where applicable:

- affected system
- severity
- owner
- sanitized evidence
- containment action
- remediation status
- customer or legal impact assessment where required

## Scope

This policy applies to the FreClean organization repositories and all associated infrastructure, workflows, application code, and external service integrations.
