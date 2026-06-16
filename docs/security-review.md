
# `docs/security-review.md`

```markdown
# Security Review

## Summary

This repository contains a frontend chatbot embed. The main security risks are not model attacks or backend exploits. The main risks are configuration leakage, domain misuse, weak content governance, and accidental exposure of support data.

## Reviewed Areas

| Area | Status | Notes |
|---|---|---|
| HTML structure | Reviewed | Clean semantic structure added |
| External scripts | Reviewed | Botpress CDN scripts are required |
| Secrets handling | Reviewed | No private credentials should be committed |
| Botpress IDs | Accepted | Public frontend identifiers may be visible |
| Allowed origins | Needs production hardening | Restrict domains before release |
| Customer data | Must be excluded | No real logs or customer data in repo |
| FAQ data | Anonymized only | Sample data provided for portfolio use |

## Production Checklist

- Restrict `allowedOrigins` to production domains.
- Keep Botpress admin credentials out of the repository.
- Do not commit exported customer conversations.
- Review the FAQ knowledge base before publishing.
- Add monitoring for repeated fallback queries.
- Review any files before committing screenshots.
- Remove private company URLs if required by policy.

## OWASP-Oriented Notes

Although this is not a traditional backend app, the following web security principles still apply:

- Use HTTPS for all scripts and assets.
- Minimize third-party script exposure.
- Use Content Security Policy if the hosting environment allows it.
- Avoid storing sensitive data in session storage.
- Do not expose internal support workflows through chatbot messages.
- Keep dependency and platform access tightly controlled.
