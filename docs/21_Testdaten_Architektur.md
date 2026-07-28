# Testdaten Architektur

## Ziel

Gute Testdaten machen Tests reproduzierbar und unabhängig.

## Varianten

### Statische Daten

Geeignet für stabile Referenzdaten.

### Dynamische Daten

Daten werden während des Tests erzeugt.

Beispiel:

```typescript
const user = `test_${Date.now()}`;
```

## Trennung von Testdaten

Tests sollten eigene Daten verwenden, damit parallele Ausführung möglich bleibt.

## Fixtures

Gemeinsame Testdaten können über Fixtures bereitgestellt werden.

## Empfehlung

Keine versteckten Abhängigkeiten zwischen Tests erzeugen.
