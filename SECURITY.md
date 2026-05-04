# Security Policy

## Supported Versions

| Version | Supported |
| --- | --- |
| 0.3.x (latest) | yes |
| < 0.3.0 | no |

## Reporting a Vulnerability

Do not open a public issue for security vulnerabilities.

Email `ramprakashdhulipudi@gmail.com` with:

1. A clear description of the vulnerability.
2. Steps to reproduce or a proof-of-concept.
3. The potential impact you see.

Expected response: acknowledgement within 5 business days. A fix or mitigation plan will be communicated within 14 business days.

## Security Considerations

### Backend API

1. CORS is restricted to an explicit allow-list via `CORS_ORIGINS`. Do not set `*` in production.
2. All third-party proxy routes (GitHub, Medium, Anthropic, EmailJS) validate input before forwarding.
3. Rate limiting is applied to the chat and contact endpoints.
4. Helmet middleware sets secure HTTP headers on every response.
5. No secrets are committed; all sensitive values are loaded from environment variables.

### Anthropic / Chat Proxy

1. The chat system prompt is fixed server-side; client-supplied messages are not injected into the system role.
2. Chat history is capped by `CHAT_HISTORY_CHAR_BUDGET` to limit token exfiltration surface.
3. Requests exceeding the fast-model threshold are routed to the configured model; no user control over model selection.

### Dependency Management

Dependency updates follow `DEPENDENCY_POLICY.md`. Dependabot is configured for weekly npm audits.

## Known Residual Risk

| Item | Mitigation |
| --- | --- |
| Public GitHub token in `.env` | Token is optional and read-only. Use least-privilege scopes. |
| Anthropic key exposure | Stored server-side only; never sent to the frontend. |
