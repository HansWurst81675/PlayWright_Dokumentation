# playwright.config.ts

## Bedeutung

Die Datei `playwright.config.ts` steuert das Verhalten der Testausführung.

Typische Einstellungen:

- Testverzeichnis
- Browser-Projekte
- Timeout-Werte
- Reporter
- Screenshots
- Videos
- Tracing

Beispiel:

```typescript
import { defineConfig } from '@playwright/test';

export default defineConfig({
  testDir: './tests',
  use: {
    trace: 'on-first-retry',
    screenshot: 'only-on-failure'
  }
});
```

## Empfehlung

Die Konfiguration sollte versioniert werden und für alle Entwickler identisch sein.
