# Playwright Config Referenz

## Überblick

Die Datei `playwright.config.ts` definiert die zentrale Testumgebung.

## Beispiel einer produktiven Konfiguration

```typescript
import { defineConfig, devices } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  timeout: 30000,
  expect: {
    timeout: 5000
  },
  use: {
    baseURL: 'https://localhost:8443',
    trace: 'on-first-retry',
    screenshot: 'only-on-failure',
    video: 'retain-on-failure'
  },
  projects: [
    {
      name: 'chromium',
      use: { ...devices['Desktop Chrome'] }
    }
  ]
});
```

## Wichtige Einstellungen

### timeout

Maximale Laufzeit eines Tests.

### expect.timeout

Zeit für Assertions.

### baseURL

Erlaubt relative Navigation:

```typescript
await page.goto('/login');
```

### trace

Hilft bei Fehleranalyse.

## Empfehlung

Die Konfiguration sollte bewusst klein bleiben und mit dem Projekt wachsen.
