---
name: owasp-security
description: "OWASP Top 10 security checklist for web applications. Use before shipping any feature that handles user input, authentication, payments, or sensitive data."
visibility: public
requires_body_cleanup: false
---
# OWASP Security Checklist

## A01 — Broken Access Control
- Verify RLS policies on all Supabase tables
- Server-side authorization checks — never trust client
- Test with unauthorized roles before shipping

## A02 — Cryptographic Failures
- HTTPS everywhere (Vercel enforces this)
- No sensitive data in localStorage — use httpOnly cookies
- Hash passwords with bcrypt/argon2 (Supabase Auth handles this)

## A03 — Injection
- Use parameterized queries — never concatenate SQL
- Sanitize HTML with DOMPurify before rendering
- Validate all inputs server-side

## A05 — Security Misconfiguration
- Remove debug endpoints before production
- Never commit .env files
- Restrict CORS to known origins

## A07 — Auth Failures
- Implement rate limiting on auth endpoints
- Invalidate sessions on logout
- Use Supabase Auth — don't roll your own

## A09 — Logging Failures
- Log auth failures and suspicious patterns
- Don't log passwords, tokens, or PII
- Set up alerts for anomalous patterns

## Quick Checklist Before Ship
- [ ] RLS enabled on all tables
- [ ] No secrets in client code
- [ ] Input validation on all forms
- [ ] HTTPS + security headers configured
- [ ] Auth tokens expire appropriately
