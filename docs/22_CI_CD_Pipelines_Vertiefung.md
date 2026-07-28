# CI/CD Pipelines Vertiefung

## Ziel

Automatisierte Playwright-Tests sollen in jeder Pipeline reproduzierbar laufen.

## Typischer Ablauf

1. Repository auschecken
2. Node-Version setzen
3. Abhängigkeiten installieren
4. Browser installieren
5. Tests ausführen
6. Ergebnisse speichern

## Fehleranalyse in CI

Wichtige Artefakte:

- Trace-Dateien
- Screenshots
- Videos
- Reports

## Empfehlungen

- gleiche Node-Version lokal und CI verwenden
- Lock-Dateien verwenden
- Tests deterministisch halten
- Fehler immer mit Artefakten analysieren
