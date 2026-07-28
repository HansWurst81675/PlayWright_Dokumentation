# Page Object Architektur Fortgeschritten

## Ziel

Bei größeren Projekten reicht ein einfaches Page Object oft nicht aus.

## Verantwortlichkeiten

Ein Page Object enthält:

- Locators
- Benutzeraktionen
- Seitenspezifische Funktionen

Ein Test enthält:

- Szenario
- Testdaten
- Assertions

## Beispiel

```typescript
class LoginPage {
  constructor(private page: Page) {}

  async login(user: string, password: string) {
    await this.page.getByPlaceholder('Benutzername').fill(user);
    await this.page.getByPlaceholder('Passwort').fill(password);
    await this.page.getByRole('button', {name: /anmelden/i}).click();
  }
}
```

## Vermeiden

Page Objects sollten keine komplexen Testentscheidungen enthalten.

## Empfehlung

Kleine, fokussierte Page Objects sind einfacher zu warten als große Sammelklassen.
