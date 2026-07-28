# Typische Fehlermeldungen und Lösungen

## Timeout exceeded

### Ursache

Playwright findet ein Element nicht rechtzeitig oder eine Navigation ist noch nicht abgeschlossen.

### Analyse

Prüfen:

- Locator korrekt?
- Element sichtbar?
- Anwendung fertig geladen?
- falscher Zeitpunkt der Assertion?

## Strict mode violation

### Ursache

Ein Locator findet mehrere Elemente.

Beispiel:

```typescript
page.getByText('Löschen')
```

### Lösung

Einen eindeutigeren Locator verwenden.

## Navigation Timeout

### Ursachen

- Backend langsam
- falsche URL
- Weiterleitung nicht abgeschlossen

## Empfehlung

Nicht Symptome mit längeren Timeouts behandeln. Erst Ursache analysieren.
