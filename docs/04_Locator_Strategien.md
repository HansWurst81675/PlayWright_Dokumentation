# Locator Strategien

## Bevorzugte Reihenfolge

1. getByRole
2. getByLabel
3. getByPlaceholder
4. getByText
5. CSS-Selektoren

Beispiel:

```typescript
await page.getByRole('button', { name: /anmelden/i }).click();
```

## Regex verwenden

Bei dynamischen Texten können reguläre Ausdrücke eingesetzt werden:

```typescript
await expect(page.getByText(/Anke Mühlsam/)).toBeVisible();
```

Stabile Locator reduzieren Testfehler.
