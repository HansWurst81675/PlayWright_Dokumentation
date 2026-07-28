# Rollen, Rechte und Berechtigungen testen

## Ziel

Viele Anwendungen unterscheiden Benutzerrollen. Tests müssen diese Unterschiede abdecken.

## Beispiele

- Administrator darf Benutzer löschen
- Benutzer darf nur eigene Daten sehen
- Gast hat eingeschränkte Funktionen

## Testaufbau

Für jede Rolle:

1. Benutzer vorbereiten
2. Login durchführen
3. erlaubte Aktionen prüfen
4. verbotene Aktionen prüfen

## Empfehlung

Berechtigungen nicht nur über sichtbare Buttons prüfen. Auch direkte Aufrufe und API-Antworten müssen berücksichtigt werden.
