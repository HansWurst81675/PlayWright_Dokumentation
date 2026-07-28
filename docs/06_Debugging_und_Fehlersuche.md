# Debugging und Fehlersuche

## Trace Viewer

Playwright kann Testabläufe aufzeichnen:

```bash
npx playwright test --trace on
```

Anschließend:

```bash
npx playwright show-trace trace.zip
```

## Debug Modus

```bash
npx playwright test --debug
```

## Screenshots und Videos

Bei Fehlern helfen:

- Screenshots
- Videos
- Trace-Dateien
- Browser-Konsole

## Typische Fehler

### Timeout bei URL-Prüfung

Ursachen:

- Weiterleitung dauert länger
- falscher Zeitpunkt der Prüfung
- Anwendung navigiert weiter

### Locator nicht gefunden

Prüfen:

- stimmt der sichtbare Text?
- ist das Element wirklich sichtbar?
- ist der Locator stabil?
