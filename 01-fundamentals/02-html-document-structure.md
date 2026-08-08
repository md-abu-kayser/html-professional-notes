# HTML Document Structure

## Overview

Every valid HTML document follows the same skeleton: a doctype declaration, an `<html>` root, a `<head>` for metadata, and a `<body>` for visible content. This lesson covers what each piece actually does.

## Why It Matters

Skipping or misordering these pieces doesn't always cause a visible error — but it can trigger "quirks mode" rendering, break character encoding, or confuse search engines and screen readers, all invisibly.

## Core Concepts

### The full skeleton

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>My Page</title>
</head>
<body>
  <p>Visible content goes here.</p>
</body>
</html>
```

### `<!DOCTYPE html>`

Tells the browser to render in **standards mode** using the modern HTML5 spec. Omitting it (or using an old doctype) can trigger "quirks mode," where the browser emulates decades-old rendering bugs for backward compatibility — almost never what you want.

### `<html lang="...">`

The `lang` attribute tells screen readers which pronunciation rules to use and helps browsers offer accurate translation — a small attribute with real accessibility impact.

### `<head>` — metadata, not visible content

Holds information *about* the page: `<meta charset>` (character encoding — always UTF-8 today), the viewport meta tag (needed for responsive design), `<title>`, and links to CSS/fonts. Nothing inside `<head>` renders directly on the page.

### `<body>` — everything the user sees

All visible content — text, images, forms, everything covered in the rest of this module — lives here, exactly once per document.

## Common Pitfalls

- Forgetting `<meta charset="UTF-8">` — can cause special characters (curly quotes, emoji, non-English text) to render as garbled symbols.
- Omitting the viewport meta tag — mobile browsers will render the page at desktop width and zoom out, breaking responsive layouts.
- Putting visible content in `<head>` or metadata in `<body>` — browsers often "fix" this silently, which hides the mistake instead of surfacing it.

## Key Takeaways

- Every HTML document needs `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`, in that order.
- `<!DOCTYPE html>` triggers standards-mode rendering — never omit it.
- `<head>` holds metadata (charset, viewport, title); `<body>` holds everything visible.
- `lang` and the viewport meta tag are small additions with outsized accessibility and responsiveness impact.
