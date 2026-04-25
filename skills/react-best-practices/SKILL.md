---
name: react-best-practices
description: "React + TypeScript best practices for component design, state management, performance, and accessibility. Use when building React components or reviewing frontend code."
visibility: public
requires_body_cleanup: true
---
# React Best Practices

## Component Design
- Prefer functional components + hooks
- Keep components small and single-purpose
- Co-locate state as close to where it's used as possible
- Separate UI (presentational) from logic (container/hooks)

## Performance
- Use `React.memo` for expensive pure components
- `useMemo` for expensive computations, `useCallback` for stable callbacks
- Avoid creating objects/arrays inline in JSX (causes re-renders)
- Use React Query / SWR for server state — don't put server data in Redux

## TypeScript
- Type all props with interfaces, not `any`
- Use discriminated unions for component variants
- Export prop types for reuse: `export type ButtonProps = {...}`

## Accessibility
- All interactive elements need keyboard support
- Use semantic HTML (`button`, not `div` with onClick)
- Add `aria-label` for icon-only buttons
- Test with screen reader before shipping

