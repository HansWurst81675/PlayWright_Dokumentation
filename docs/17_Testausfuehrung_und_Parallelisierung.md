# Testausführung und Parallelisierung

## Übersicht

Playwright kann Tests parallel ausführen. Das reduziert die Laufzeit großer Test-Suiten, erfordert aber eine saubere Testarchitektur.

## Worker

Worker sind unabhängige Prozesse, die Tests ausführen.

Konfiguration:

```typescript
export default defineConfig({
  workers: 4
});
```

## Parallele Tests

Vorteile:

- kürzere Laufzeit
- bessere Nutzung von CI-Systemen

Voraussetzungen:

- Tests dürfen sich nicht gegenseitig beeinflussen
- Testdaten müssen getrennt sein
- keine gemeinsamen veränderbaren Zustände

## Serialisierung

Manche Tests müssen bewusst nacheinander laufen:

```typescript
test.describe.configure({ mode: 'serial' });
```

Dies sollte nur selten verwendet werden.

## Empfehlung

Tests so schreiben, dass jeder Test alleine ausführbar ist.
