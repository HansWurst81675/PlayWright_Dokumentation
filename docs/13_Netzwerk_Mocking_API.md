# Netzwerk, Mocking und API Tests

## API Tests

Playwright kann neben Browser-Tests auch API-Aufrufe testen.

Beispiel:

```typescript
const response = await request.get('/api/users');
expect(response.ok()).toBeTruthy();
```

## Mocking

Mit `route()` können Netzwerkantworten ersetzt werden.

```typescript
await page.route('**/api/user', route => {
  route.fulfill({ json: { name: 'Test' } });
});
```

## Einsatzbereiche

- langsame Backends simulieren
- Fehlerfälle testen
- unabhängige UI-Tests ermöglichen
