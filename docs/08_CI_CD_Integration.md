# CI/CD Integration

## Ziel

Automatisierte Tests sollten regelmäßig und reproduzierbar ausgeführt werden.

## Beispiel GitHub Actions

```yaml
name: Playwright Tests

on:
  push:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
      - run: npm ci
      - run: npx playwright install --with-deps
      - run: npx playwright test
```

## Artefakte

Bei Fehlern sollten gespeichert werden:

- Testberichte
- Screenshots
- Traces
- Videos

Damit können Fehler später nachvollzogen werden.
