# Dynamische Tabellen und Listen

## Herausforderung

Viele Anwendungen zeigen Daten mit wechselnden IDs, Zeitstempeln oder Sortierungen.

## Problematischer Ansatz

Nicht auf vollständige dynamische Texte prüfen:

```typescript
expect(text).toBe('Anke Mühlsam 24.07.2026, 13:33');
```

## Besser

Relevante Teile prüfen:

```typescript
await expect(page.getByText('Anke Mühlsam')).toBeVisible();
```

## Löschen testen

Ablauf:

1. Datensatz finden
2. eindeutige Aktion ausführen
3. Verschwinden prüfen

Beispiel:

```typescript
await row.getByRole('button', {name:'Löschen'}).click();
await expect(row).not.toBeVisible();
```

## Empfehlung

Tests sollen Verhalten prüfen, nicht zufällige Darstellung.
