# Teststruktur und Best Practices

## Empfohlene Struktur

```
tests/
  login.spec.ts
  dashboard.spec.ts
pages/
  LoginPage.ts
  DashboardPage.ts
```

## Regeln

- Jeder Test hat ein klares Ziel.
- Tests sollten unabhängig voneinander laufen.
- Wiederkehrende Abläufe werden gekapselt.
- Fehler werden mit aussagekräftigen Assertions erkannt.

## Page Object Model

Das Page Object Model trennt Testlogik von Seiteninteraktion und verbessert Wartbarkeit.
