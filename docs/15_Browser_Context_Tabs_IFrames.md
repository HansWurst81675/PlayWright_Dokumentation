# Browser Context, Tabs und IFrames

## Browser Context

Ein Context isoliert Browserzustände wie Cookies und Local Storage.

```typescript
const context = await browser.newContext();
const page = await context.newPage();
```

## Neue Tabs

Bei Links mit neuem Fenster:

```typescript
const popup = await page.waitForEvent('popup');
```

## IFrames

Für eingebettete Inhalte:

```typescript
const frame = page.frameLocator('#iframe');
await frame.getByRole('button').click();
```

## Empfehlung

Jeder Test sollte einen klar definierten Browserzustand besitzen.
