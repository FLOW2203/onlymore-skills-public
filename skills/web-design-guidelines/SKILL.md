---
name: web-design-guidelines
description: "Audit UI code against 100+ rules covering accessibility, performance, and UX best practices. Use before deploying any frontend, when reviewing UI code, or when the user asks about accessibility, a11y, WCAG, or UX quality."
visibility: public
requires_body_cleanup: true
---
# Web Design Guidelines Audit

Systematically check code against every rule below. Output findings in `file:line — issue` format.

## Accessibility (a11y / WCAG 2.1 AA)
- [ ] ARIA attributes, roles, states used correctly
- [ ] Visible focus states on ALL interactive elements (outline, ring)
- [ ] Every input has an associated `<label>` (not just placeholder)
- [ ] Touch targets minimum 44×44px
- [ ] `@media (prefers-reduced-motion: reduce)` applied to animations
- [ ] Semantic HTML: `<nav>`, `<main>`, `<article>`, `<aside>`, `<footer>`
- [ ] Keyboard navigation: tab order logical, focus trap for modals
- [ ] Heading hierarchy: H1 → H2 → H3 (no skipping levels)
- [ ] Color contrast: ≥4.5:1 (text), ≥3:1 (large text/UI components)
- [ ] `alt` text on ALL images (empty `alt=""` for decorative)
- [ ] `lang` attribute on `<html>` element
- [ ] No color-only information (icons + color, not color alone)

## Performance
- [ ] Lazy loading for below-fold images (`loading="lazy"`)
- [ ] Responsive images (`srcset`, `sizes` attributes)
- [ ] Font loading strategy (`font-display: swap` or `optional`)
- [ ] Critical CSS inlined, rest deferred
- [ ] No unused CSS/JS in production bundle
- [ ] Images in WebP/AVIF format
- [ ] Preconnect hints for third-party origins

## UX Best Practices
- [ ] Loading states for ALL async operations (skeleton, spinner)
- [ ] Error states with recovery actions (not just "Error occurred")
- [ ] Empty states with guidance and CTA
- [ ] Consistent spacing scale (Tailwind spacing system)
- [ ] Mobile-first responsive design (no horizontal scroll)
- [ ] Form validation: inline, immediate, specific
- [ ] Confirmation for destructive actions (delete, cancel)
- [ ] Back navigation always available

## Code Quality
- [ ] No inline styles in JSX (use Tailwind classes)
- [ ] Components under 200 lines
- [ ] No magic numbers (use design tokens or constants)
- [ ] Consistent naming (kebab-case for CSS, camelCase for JS)

