# Login Tests mit Playwright

## Ziel

Ein Login-Test prüft den erfolgreichen und den fehlgeschlagenen Anmeldevorgang.

## Erfolgreicher Login

Beispiel:

```typescript
await page.goto('/login');
await page.getByPlaceholder('Benutzername').fill('tester');
await page.getByRole('button', { name: /anmelden/i }).click();

await expect(page).toHaveURL(/dashboard/);
```

## Fehlgeschlagener Login

Negative Tests prüfen, ob eine verständliche Fehlermeldung erscheint:

```typescript
await expect(page.getByText(/login war nicht erfolgreich/i)).toBeVisible();
```

## Hinweise

Bei Weiterleitungen sollte nicht nur auf eine URL gewartet werden. Die Navigation kann schneller erfolgen als die Assertion.

Bewährt:

- auf sichtbare Seitenelemente prüfen
- stabile Locators verwenden
- Wartezeiten nicht künstlich mit sleep() verlängern
