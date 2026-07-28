# Stabile Tests und Fehlersuche

## Grundprinzipien

Stabile Tests verwenden:

- eindeutige Locators
- klare Assertions
- reproduzierbare Testdaten
- keine unnötigen Wartezeiten

## Vermeiden

```typescript
await page.waitForTimeout(5000);
```

Feste Wartezeiten machen Tests langsam und trotzdem instabil.

Besser:

```typescript
await expect(element).toBeVisible();
```

## Typische Fehler

### Timeout

Prüfen:

- Element vorhanden?
- richtige Seite geladen?
- falscher Locator?

### Flaky Tests

Ursachen:

- Abhängigkeiten zwischen Tests
- dynamische Daten
- Race Conditions
