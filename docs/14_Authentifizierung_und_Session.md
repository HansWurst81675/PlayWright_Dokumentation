# Authentifizierung und Sessionverwaltung

## Ziel

Viele Anwendungen benötigen einen Login. Tests sollten den Authentifizierungszustand effizient verwalten.

## Storage State

Ein einmal eingeloggter Zustand kann gespeichert werden:

```typescript
await page.context().storageState({ path: 'auth.json' });
```

Danach können Tests diesen Zustand wiederverwenden.

## Vorteile

- schnellere Testausführung
- weniger wiederholte Logins
- weniger Fehlerquellen

## Empfehlung

Login-Tests separat testen. Funktionstests sollten nicht immer erneut den kompletten Login durchlaufen.
