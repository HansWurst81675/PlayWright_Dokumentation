# Page Object Model (POM)

## Ziel

Das Page Object Model trennt Seitenelemente und Aktionen von den eigentlichen Tests.

## Beispiel LoginPage

```typescript
export class LoginPage {
  constructor(private page) {}

  username = this.page.getByPlaceholder('Benutzername');
  loginButton = this.page.getByRole('button', { name: /anmelden/i });

  async login(user: string, password: string) {
    await this.username.fill(user);
    await this.loginButton.click();
  }
}
```

## Vorteile

- weniger doppelte Locators
- bessere Wartbarkeit
- Änderungen an der Oberfläche an einer Stelle
- Tests bleiben lesbar

## Empfehlung

Page Objects sollten keine Test-Assertions enthalten. Sie stellen Aktionen bereit; der Test prüft das Ergebnis.
