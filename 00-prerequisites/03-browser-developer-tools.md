# Browser Developer Tools

## Overview

Every major browser ships a full inspection and debugging suite for free. This lesson covers the parts most relevant to HTML: the Elements panel, live DOM editing, and the Console — using Chrome DevTools as the reference (Firefox and Safari offer near-equivalents).

## Why It Matters

DevTools let you see the *actual* DOM the browser built — not just the HTML you wrote — and experiment with changes instantly, without editing files and reloading. It's the fastest feedback loop available while learning.

## Core Concepts

### Opening DevTools

`F12`, or right-click any element and choose **Inspect** — this opens directly to that element in the Elements panel.

### The Elements panel

- Shows the live DOM tree, which may differ from your source (JavaScript can have modified it).
- Click any node to see its computed styles, box model, and applied CSS rules on the right.
- **Double-click text or an attribute to edit it live** — changes apply instantly but aren't saved to your file; this is for experimentation, not persistence.

### The Console

- Logs errors and warnings — including HTML parsing issues in some browsers.
- Lets you run JavaScript against the live page, e.g. `document.querySelectorAll('img:not([alt])')` to find images missing `alt` text — a genuinely useful accessibility check.

### The device toolbar

Toggle a responsive/mobile view (`Ctrl+Shift+M` in Chrome) to preview how your markup and layout behave at different viewport widths without needing a physical device.

## Common Pitfalls

- Editing markup live in DevTools and expecting it to persist — it resets on refresh; always copy changes back to your source file.
- Ignoring Console warnings because "the page still looks fine" — many HTML/accessibility issues render without visibly breaking anything.
- Only testing at your own screen's default size and never opening the device toolbar.

## Key Takeaways

- The Elements panel shows the live DOM, not your raw source — useful for debugging JavaScript-driven changes too.
- Edits made directly in DevTools are temporary — always copy fixes back into your actual files.
- The Console can run one-off JavaScript queries against the page, useful for quick accessibility/quality checks.
- The device toolbar previews responsive behavior without needing a second physical device.
