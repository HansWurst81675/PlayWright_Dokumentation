# Playwright FAQ

## Warum nicht waitForTimeout verwenden?

Feste Wartezeiten machen Tests langsam und instabil. Playwright wartet automatisch auf viele Zustände.

## Warum schlägt ein Test nur manchmal fehl?

Typische Ursachen:

- Race Conditions
- gemeinsame Testdaten
- instabile Locators
- externe Abhängigkeiten

## Sollte jeder Test neu einloggen?

Nein. Funktionstests können häufig einen gespeicherten Authentifizierungszustand verwenden.

## Sind viele UI Tests immer besser?

Nein. Eine Mischung aus Unit-, API- und UI-Tests ist meist effektiver.

## Was macht einen guten Test aus?

Ein guter Test ist:

- verständlich
- reproduzierbar
- unabhängig
- wartbar
