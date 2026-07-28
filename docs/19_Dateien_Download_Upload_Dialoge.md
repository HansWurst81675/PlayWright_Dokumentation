# Dateien, Downloads, Uploads und Dialoge

## Datei-Upload

Playwright kann Dateien direkt setzen:

```typescript
await page.getByLabel('Datei').setInputFiles('test.pdf');
```

## Downloads

Downloads werden abgefangen:

```typescript
const download = await page.waitForEvent('download');
await page.getByText('Download').click();
await download.saveAs('result.pdf');
```

## Browser Dialoge

Beispiele:

- alert
- confirm
- prompt

```typescript
page.on('dialog', async dialog => {
  await dialog.accept();
});
```

## Empfehlung

Dateien sollten in Tests kontrolliert erzeugt und nach dem Test bereinigt werden.
