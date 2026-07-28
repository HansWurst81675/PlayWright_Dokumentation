# Referenz Projektstruktur

## Beispiel

```
project/
├── tests/
│   ├── login.spec.ts
│   └── dashboard.spec.ts
├── pages/
│   ├── LoginPage.ts
│   └── DashboardPage.ts
├── fixtures/
├── test-data/
├── playwright.config.ts
└── package.json
```

## tests

Enthält die eigentlichen Testszenarien.

## pages

Kapselt die Bedienung von Webseiten.

## fixtures

Stellt gemeinsame Testumgebungen bereit.

## test-data

Enthält wiederverwendbare Testdaten.

## Empfehlung

Die Struktur sollte mit der Größe des Projekts wachsen und nicht unnötig kompliziert sein.
