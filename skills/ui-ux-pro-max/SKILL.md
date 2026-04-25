---
name: ui-ux-pro-max
description: "Professional UI/UX design system with 50+ styles, 97 color palettes, 57 font pairings, and advanced component patterns. Use when designing interfaces, selecting visual styles, creating design systems, or generating component code."
visibility: public
requires_body_cleanup: true
---
# UI/UX Pro Max

## Design Style Catalogue (50+ styles)
Select one per project:
- **Glassmorphism** — frosted glass, blur backdrop, semi-transparent
- **Neumorphism** — soft shadows, embossed depth, monochromatic
- **Brutalism** — raw borders, high contrast, no-nonsense typography
- **Bento Grid** — modular cards, varied sizes, dashboard layout
- **Aurora** — gradient backgrounds, glowing accents, dark mode
- **Corporate Clean** — whitespace, system fonts, conservative
- **Editorial** — magazine layout, large typography, asymmetric
- **Retro/Y2K** — pixel fonts, neon, saturated colors
- **Organic/Blob** — curved shapes, earthy tones, nature-inspired
- **Minimal Zen** — maximum whitespace, monochrome, micro-interactions

## Color Palette System (97 palettes)
Structure: primary / secondary / accent / surface / text

## Font Pairings (57 pairings)
Format: [Display / Body] — personality

- **Playfair Display / Inter** — elegant, trustworthy (COLHYBRI)
- **Bebas Neue / Inter** — bold, energetic (CROWNIUM)
- **Nunito / Inter** — friendly, approachable (DOJUKU)
- **Syne / DM Sans** — modern, tech-forward
- **Space Grotesk / Manrope** — startup, innovative
- **Fraunces / Source Sans 3** — premium, editorial

## Component Patterns
### Card Variants
```tsx
// Bento card
<div className="rounded-3xl bg-gradient-to-br from-emerald-900 to-emerald-700 p-6 shadow-xl">

// Glass card
<div className="rounded-2xl backdrop-blur-md bg-white/10 border border-white/20 p-6">

// Minimal card
<div className="rounded-xl border border-gray-100 bg-white p-6 hover:shadow-md transition-shadow">
```

### Button Hierarchy
```tsx
// Primary CTA
<button className="bg-emerald-800 hover:bg-emerald-700 text-amber-100 font-semibold px-8 py-3 rounded-xl transition-all">

// Secondary
<button className="border-2 border-emerald-800 text-emerald-800 hover:bg-emerald-50 font-semibold px-8 py-3 rounded-xl">

// Ghost
<button className="text-emerald-800 hover:bg-emerald-50 px-6 py-2 rounded-lg">
```

## Micro-interactions
- Hover: `transition-all duration-200`
- Press: `active:scale-95`
- Loading: skeleton with `animate-pulse`
- Success: `animate-bounce` for 1s then stop
- Error: `animate-shake` (custom keyframe)

## Rules
- Mobile-first always
- 8px base spacing grid (Tailwind default)
- Minimum 44px touch targets
- Consistent border-radius per project (rounded-xl or rounded-2xl, not mixed)
