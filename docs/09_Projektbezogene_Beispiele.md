# Projektbezogene Playwright Beispiele

Dieses Kapitel beschreibt typische Muster aus der praktischen Testautomatisierung.

## Login mit Redirect

Eine Anwendung kann nach erfolgreichem Login direkt auf ein Dashboard weiterleiten.

Beispiel:

```typescript
await Promise.all([
  page.waitForURL(/.*dashboard/),
  page.getByRole('button', { name: /anmelden/i }).click()
]);
```

Die Prüfung sollte nicht nur die URL betrachten, sondern auch den Zustand der Zielseite:

```typescript
await expect(page.getByText(/Dashboard/i)).toBeVisible();
```

## Dynamische Inhalte

Zeitstempel oder generierte IDs sollten nicht als feste Zeichenkette geprüft werden.

Beispiel:

```typescript
await expect(page.getByText(/Anke Mühlsam/)).toBeVisible();
```

oder mit regulären Ausdrücken:

```typescript
expect(text).toMatch(/\d{2}\.\d{2}\.\d{4}/);
```

## Grundsatz

Tests prüfen Verhalten, nicht zufällige Details der Darstellung.
