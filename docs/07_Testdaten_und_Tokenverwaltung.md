# Testdaten und Tokenverwaltung

## Testdaten

Testdaten sollten nachvollziehbar und möglichst unabhängig voneinander sein.

Möglichkeiten:

- feste Testdaten
- Fixtures
- API-Vorbereitung
- Setup-Dateien

## Token zwischen Tests

Tests sollten normalerweise keine Abhängigkeit voneinander haben.

Wenn ein Token benötigt wird:

- im Test-Setup erzeugen
- über Fixtures bereitstellen
- oder Storage State verwenden

Beispiel Storage State:

```typescript
await page.context().storageState({ path: 'state.json' });
```

## Empfehlung

Ein Test, der einen anderen Test voraussetzt, ist schwer wartbar.

Besser: gemeinsame Vorbereitung zentral kapseln.
