# Vollständige Beispiel-Test-Suite

## Ziel

Eine produktive Testsuite besteht aus mehreren Ebenen und klarer Trennung der Verantwortlichkeiten.

## Beispielstruktur

```text
 tests/
 ├── login.spec.ts
 ├── user-management.spec.ts
 └── dashboard.spec.ts

 pages/
 ├── LoginPage.ts
 ├── DashboardPage.ts
 └── UserPage.ts
```

## Beispiel Login Test

```typescript
import { test, expect } from '@playwright/test';

test('Benutzer kann sich anmelden', async ({ page }) => {
  await page.goto('/login');
  await page.getByPlaceholder('Benutzername').fill('tester');
  await page.getByRole('button', { name: /anmelden/i }).click();

  await expect(page).toHaveURL(/dashboard/);
});
```

## Qualitätsmerkmale

- unabhängige Tests
- klare Assertions
- wiederverwendbare Komponenten
- nachvollziehbare Fehler
