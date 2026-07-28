# Fixtures und Hooks

## Fixtures

Fixtures stellen vorbereitete Testumgebungen bereit.

Beispiel:

```typescript
import { test } from '@playwright/test';

test('Beispiel', async ({ page }) => {
  await page.goto('/');
});
```

`page` ist bereits ein integriertes Fixture.

## Hooks

### beforeEach

Wird vor jedem Test ausgeführt:

```typescript
 test.beforeEach(async ({ page }) => {
   await page.goto('/login');
 });
```

### afterEach

Geeignet für Aufräumarbeiten.

## Empfehlung

Hooks nur für gemeinsame Vorbereitung verwenden. Testlogik gehört in den Test.
