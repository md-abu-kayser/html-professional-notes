# Links & Anchors

## Overview

The `<a>` (anchor) element with an `href` attribute is what makes the web *hyper*text — this lesson covers link types, targets, and the attributes that control how a link behaves.

## Why It Matters

Links are one of the most-used and most-misused elements: turning a `<div>` or `<span>` into a "fake link" with JavaScript breaks keyboard navigation, middle-click-to-open-in-new-tab, and screen reader link lists — all things a real `<a href>` gets for free.

## Core Concepts

### Basic syntax

```html
<a href="https://example.com">Visit Example</a>
<a href="/about">About page (relative to site root)</a>
<a href="contact.html">Contact page (relative to current page)</a>
<a href="#section-2">Jump to a section on this page</a>
```

### Absolute vs. relative URLs

- **Absolute**: `https://example.com/page` — the full address, works from anywhere.
- **Relative**: `about.html` or `/about` — resolved against the current page's location; makes a site portable across domains (dev, staging, production) without editing every link.

### Opening in a new tab, safely

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">External site</a>
```

`target="_blank"` opens a new tab. Without `rel="noopener"`, the new page gets partial access to the original tab's `window` object — a real (if narrow) security and performance issue. Always pair the two.

### Other useful link types

```html
<a href="mailto:hello@example.com">Email us</a>
<a href="tel:+15551234567">Call us</a>
<a href="report.pdf" download>Download the report</a>
```

## Common Pitfalls

- Using `target="_blank"` without `rel="noopener"`.
- Making a clickable "link" out of a styled `<div>` with a JavaScript click handler instead of a real `<a href>` — breaks keyboard access and right-click/middle-click behavior.
- Using `href="#"` or `href="javascript:void(0)"` for buttons that don't actually navigate — use a real `<button>` instead (see [11-block-vs-inline-elements](./11-block-vs-inline-elements.md) and forms basics).

## Key Takeaways

- `<a href="...">` is the only element that gives you real link behavior (keyboard access, new-tab, right-click menu) for free.
- Always pair `target="_blank"` with `rel="noopener noreferrer"`.
- Prefer relative URLs within your own site so it survives domain/environment changes.
- If it navigates, it's a link (`<a>`); if it performs an action without navigating, it's a `<button>` — never the reverse.
