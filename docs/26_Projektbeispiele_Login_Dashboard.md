# Projektbeispiele: Login und Dashboard

## Ziel

Dieses Kapitel beschreibt typische Muster aus realen Anwendungen.

## Login Test

Ein Login-Test sollte mindestens prüfen:

- Login-Seite erreichbar
- Eingabefelder vorhanden
- erfolgreiche Anmeldung
- Weiterleitung
- sichtbarer Zustand nach Login

Beispiel:

```typescript
await page.goto('/login');
await page.getByPlaceholder('Benutzername').fill('tester');
await page.getByRole('button', { name: /anmelden/i }).click();

await expect(page).toHaveURL(/dashboard/);
```

## Logout Redirect

Bei Anwendungen mit Parametern:

```typescript
await expect(page).toHaveURL(/login\?reason=logout/);
```

## Dashboard Prüfung

Nicht nur URL prüfen:

```typescript
await expect(page.getByRole('heading', { name: /dashboard/i })).toBeVisible();
```

## Empfehlung

Ein erfolgreicher Login ist erst erreicht, wenn die Anwendung den erwarteten Zustand zeigt.
