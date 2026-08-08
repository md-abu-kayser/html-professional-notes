# Images & Figures

## Overview

`<img>` embeds an image; `<figure>`/`<figcaption>` groups an image (or other media) with a caption. This lesson covers both, with a strong focus on `alt` text — the single most consequential attribute in this module.

## Why It Matters

`alt` text is read aloud by screen readers, displayed if the image fails to load, and indexed by search engines — one attribute serving accessibility, resilience, and SEO simultaneously.

## Core Concepts

### The `<img>` element

```html
<img src="mountain.jpg" alt="Snow-capped mountain peak at sunrise" width="800" height="600">
```

- `src` — the image path (relative or absolute).
- `alt` — a text description. **Required for accessibility**, even if the string is empty.
- `width`/`height` — declaring the image's real dimensions lets the browser reserve space before the image loads, preventing layout shift.

### Writing good `alt` text

```html
<!-- Meaningful image: describe its content and purpose -->
<img src="chart-q3-sales.png" alt="Bar chart showing Q3 sales up 22% over Q2">

<!-- Purely decorative image: empty alt so screen readers skip it -->
<img src="divider-swirl.png" alt="">
```

Never leave `alt` off entirely — screen readers will often read the whole filename aloud instead, which is worse than either option above.

### `<figure>` and `<figcaption>`

```html
<figure>
  <img src="chart-q3-sales.png" alt="Bar chart showing Q3 sales up 22% over Q2">
  <figcaption>Figure 1: Q3 regional sales performance</figcaption>
</figure>
```

`<figure>` semantically groups media with its caption — and importantly, works for more than images (code blocks, quotes, diagrams).

## Common Pitfalls

- Omitting `alt` entirely instead of using `alt=""` for decorative images.
- Writing `alt="image"` or `alt="photo123.jpg"` — describes nothing useful.
- Skipping `width`/`height`, causing content to jump around as images load in (a major, measurable performance/UX issue — see [09-performance-optimization](../09-performance-optimization/README.md)).

## Key Takeaways

- Every `<img>` needs an `alt` attribute — a real description for meaningful images, an empty string for decorative ones.
- Declaring `width`/`height` prevents layout shift as images load.
- `<figure>`/`<figcaption>` semantically pairs media with a caption — useful beyond just images.
- `alt` text serves three audiences at once: screen reader users, anyone with a failed image load, and search engines.
