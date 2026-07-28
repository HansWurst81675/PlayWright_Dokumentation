# Locator Strategien

## Bedeutung von Locators

Ein Locator beschreibt, wie Playwright ein Element auf einer Webseite findet. Gute Locators sind der wichtigste Faktor für stabile Tests.

Ein Test sollte nicht die interne HTML-Struktur der Anwendung nachbauen, sondern die Sicht des Benutzers verwenden.

## Empfohlene Reihenfolge

1. `getByRole`
2. `getByLabel`
3. `getByPlaceholder`
4. `getByText`
5. eigene Test-IDs
6. CSS-Selektoren nur wenn notwendig

## getByRole

Die bevorzugte Methode für Benutzeroberflächen.

Beispiel Button:

```typescript
await page.getByRole('button', { name: /anmelden/i }).click();
```

Vorteile:

- orientiert sich an der Benutzeroberfläche
- funktioniert mit Accessibility-Struktur
- gut lesbar

Weitere Beispiele:

```typescript
await page.getByRole('textbox', { name: 'Benutzername' }).fill('tester');
await page.getByRole('heading', { name: /dashboard/i });
```

## getByLabel

Für Formulare mit korrekt gesetzten Labels:

```typescript
await page.getByLabel('Passwort').fill('secret');
```

Empfohlen für:

- Login-Formulare
- Eingabemasken
- Suchfelder

## getByPlaceholder

Wenn kein Label vorhanden ist:

```typescript
await page.getByPlaceholder('Benutzername').fill('tester');
```

Nachteil:

Der Placeholder kann sich bei UI-Änderungen ändern.

## getByText

Geeignet für sichtbare Texte:

```typescript
await expect(page.getByText(/Login war nicht erfolgreich/i)).toBeVisible();
```

Nicht verwenden, wenn der Text dynamisch oder mehrfach vorhanden ist.

## Reguläre Ausdrücke

Bei dynamischen Inhalten:

```typescript
await expect(page.getByText(/Anke Mühlsam/)).toBeVisible();
```

Beispiel Zeitstempel:

```typescript
expect(text).toMatch(/\d{2}\.\d{2}\.\d{4}/);
```

## Test IDs

Für komplexe Anwendungen können eigene IDs verwendet werden:

```typescript
await page.getByTestId('delete-user-button').click();
```

Beispiel HTML:

```html
<button data-testid="delete-user-button">Löschen</button>
```

## CSS-Selektoren

Nur verwenden, wenn keine bessere Möglichkeit existiert:

```typescript
await page.locator('input[name="username"]').fill('tester');
```

Problem:

CSS-Selektoren sind häufig abhängig von Implementierungsdetails.

## Typische Fehler

### Element nicht gefunden

Prüfen:

- ist das Element sichtbar?
- stimmt der Text exakt?
- gibt es mehrere gleiche Elemente?
- ist ein Frame beteiligt?

### Mehrere Treffer

Beispiel:

```typescript
await page.getByText('Löschen').first().click();
```

Besser:

```typescript
await page.getByRole('button', { name: 'Benutzer löschen' }).click();
```

## Empfehlung

Stabile Locators sind wichtiger als kurze Locators. Ein guter Locator beschreibt, was der Benutzer sieht und benutzt.
