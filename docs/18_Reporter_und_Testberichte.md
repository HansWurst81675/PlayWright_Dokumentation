# Reporter und Testberichte

## Zweck

Reporter zeigen Ergebnisse der Testausführung und unterstützen die Fehleranalyse.

## HTML Reporter

Standardmäßig erzeugt Playwright einen interaktiven HTML-Bericht.

```bash
npx playwright show-report
```

## Konfiguration

```typescript
export default defineConfig({
  reporter: [['html']]
});
```

## CI-Auswertung

In automatisierten Pipelines sollten gespeichert werden:

- HTML Reports
- Screenshots
- Videos
- Trace-Dateien

## Empfehlung

Ein fehlgeschlagener Test muss auch nach Ende der CI-Ausführung nachvollziehbar sein.
