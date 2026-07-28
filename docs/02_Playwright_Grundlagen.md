# Playwright Grundlagen

## Was ist Playwright?

Playwright ist ein Framework zur Browserautomatisierung. Es unterstützt Chromium, Firefox und WebKit und ermöglicht End-to-End-Tests von Webanwendungen.

## Grundstruktur eines Tests

```typescript
import { test, expect } from '@playwright/test';

test('Beispiel', async ({ page }) => {
  await page.goto('https://localhost:8443');
  await expect(page).toHaveTitle(/Anwendung/);
});
```

## Wichtige Konzepte

- Browser
- Context
- Page
- Locator
- Assertions
- Fixtures

Ein Test sollte möglichst unabhängig und reproduzierbar sein.
