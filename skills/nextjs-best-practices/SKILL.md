---
name: nextjs-best-practices
description: "Next.js App Router best practices: server components, data fetching, routing, SEO. Use when working on Next.js projects."
visibility: public
requires_body_cleanup: false
---
# Next.js Best Practices

## App Router
- Default to Server Components — only use `'use client'` when needed (interactivity, browser APIs)
- Fetch data in Server Components, pass as props to Client Components
- Use `loading.tsx` and `error.tsx` for UX states
- Colocate route-specific components in the route folder

## Data Fetching
- Use `fetch` with `cache: 'no-store'` for dynamic data, `cache: 'force-cache'` for static
- Prefer React Query on client for mutations and real-time
- Use Server Actions for form submissions

## Performance
- Use `next/image` for all images — auto-optimize, lazy load
- Use `next/font` to eliminate font flash
- Use `next/link` for client-side navigation
- Add `generateMetadata()` for SEO on every page

## Security
- Validate all Server Action inputs (never trust client)
- Use middleware for auth checks on protected routes
- Sanitize any HTML before dangerouslySetInnerHTML
