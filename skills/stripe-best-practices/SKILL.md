---
name: stripe-best-practices
description: "Stripe integration best practices: webhooks, idempotency, error handling, subscriptions. Use when implementing payments, subscriptions, or any Stripe integration."
visibility: public
requires_body_cleanup: true
---
# Stripe Best Practices

## Core Principles
- Always use idempotency keys for POST requests
- Handle webhooks asynchronously — return 200 immediately, process in background
- Never trust client-side data for payment amounts — always compute server-side
- Use Stripe's test clock for subscription testing

## Webhooks
- Verify signature with `stripe.webhooks.constructEvent(payload, sig, secret)`
- Handle duplicate events (Stripe retries on failure)
- Store processed event IDs to prevent double-processing
- Critical events: `payment_intent.succeeded`, `checkout.session.completed`, `customer.subscription.*`

## Error Handling
- Catch `StripeCardError`, `StripeInvalidRequestError` separately
- Surface card errors to users; log others internally
- Implement exponential backoff for retriable errors

## Security
- Keys in environment variables only — never in code
- Restrict API key permissions to minimum needed
- Use Stripe Radar rules for fraud prevention
- Enable 3D Secure for EU customers (SCA compliance)

