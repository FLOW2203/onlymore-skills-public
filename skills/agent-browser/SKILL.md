---
name: agent-browser
description: "Browser automation for web testing, form filling, screenshots, and UI verification using Playwright. Use for E2E testing, onboarding flow verification, visual regression, or any task requiring browser interaction."
visibility: public
requires_body_cleanup: true
---
# Agent Browser — Automation Navigateur

## Stack
Playwright (préféré) ou Puppeteer pour les cas simples.

## Setup
```bash
npm install -D @playwright/test
npx playwright install chromium
```

## Core Patterns
```typescript
import { chromium, Page } from 'playwright'

const browser = await chromium.launch({ headless: true })
const page = await browser.newPage()

// Navigation
await page.goto('https://colhybri.fr')

// Interactions
await page.click('button[data-testid="signup"]')
await page.fill('input[name="email"]', 'test@test.com')
await page.fill('input[name="password"]', 'securePass123')
await page.click('button[type="submit"]')

// Assertions
await page.waitForSelector('.dashboard', { timeout: 5000 })
const title = await page.title()

// Screenshot
await page.screenshot({ path: 'screenshots/dashboard.png', fullPage: true })

await browser.close()
```

## Visual Regression
```bash
npx playwright test --update-snapshots  # create baseline
npx playwright test                      # compare vs baseline
```

## Parallel Execution
```typescript
// playwright.config.ts
export default { workers: 4, retries: 2 }
```

## Rules
- Run E2E tests against staging — never production
- Use `data-testid` attributes — don't rely on CSS classes
- Screenshot on failure: `screenshot: 'only-on-failure'`
- Max timeout per test: 30s
- Mock external APIs (Stripe, Supabase) in E2E test environment
