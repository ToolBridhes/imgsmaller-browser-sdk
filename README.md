# ImgSmaller Browser SDK (Unofficial)

A tiny, dependency‑free browser SDK to compress images client‑side using Canvas. Great for demos, prototypes, and small tools.

Website: https://imgsmaller.com

## Quickstart

```html
<script src="/sdk/imgsmaller.js"></script>
<script>
(async () => {
  const file = document.querySelector('input[type=file]').files[0];
  const out = await ImgSmaller.SDK.compress(file, { targetKB: 100, mime: 'image/jpeg', auto: true });
  // Use out.objectUrl as a preview or download
  const a = document.createElement('a');
  a.href = out.objectUrl; a.download = 'compressed.jpg'; a.click();
})();
</script>
```

## API
- `compress(input, options)` → `{ blob, objectUrl, mime, bytes }`
  - `input`: File/Blob | HTMLImageElement | URL string
  - `options`:
    - `targetKB` (number, default 100)
    - `mime` (string: 'image/jpeg' | 'image/webp' | 'image/png')
    - `width`, `height` (optional resize)
    - `auto` (boolean) – prefers quality over exact size
    - `background` (hex or css color) – fill bg for JPEG

## Demo (CodePen)
Copy the HTML snippet above into a CodePen/JSFiddle and add a file input.

## License
MIT
