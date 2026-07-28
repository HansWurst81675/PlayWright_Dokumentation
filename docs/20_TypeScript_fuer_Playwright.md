# TypeScript für Playwright

## Warum TypeScript?

Playwright wird häufig mit TypeScript eingesetzt. Typisierung hilft, Fehler früh zu erkennen und verbessert die Wartbarkeit.

## async und await

Browseraktionen sind asynchron:

```typescript
await page.goto('/login');
await page.getByRole('button').click();
```

Ohne `await` kann der Test zu früh weiterlaufen.

## Klassen in Page Objects

```typescript
export class LoginPage {
  constructor(private page: Page) {}
}
```

Die Klasse kapselt die Interaktion mit einer Seite.

## Typen verwenden

```typescript
interface User {
  username: string;
  password: string;
}
```

Dadurch werden falsche Aufrufe schneller erkannt.

## Empfehlung

TypeScript-Fehler früh beheben. Sie sind meist einfacher zu lösen als Laufzeitfehler im Test.
