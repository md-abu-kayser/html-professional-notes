# Lists: Ordered, Unordered, Definition

## Overview

HTML has three list types — unordered (`<ul>`), ordered (`<ol>`), and definition (`<dl>`) — each with a distinct meaning, plus the ability to nest lists inside each other.

## Why It Matters

Lists are one of the most common ways screen readers describe structure ("list of 5 items") — using an actual list element instead of manually formatted lines with line breaks makes that structure available to assistive technology automatically.

## Core Concepts

### Unordered lists — items with no inherent sequence

```html
<ul>
  <li>Milk</li>
  <li>Eggs</li>
  <li>Bread</li>
</ul>
```

### Ordered lists — sequence matters

```html
<ol>
  <li>Preheat the oven</li>
  <li>Mix the batter</li>
  <li>Bake for 25 minutes</li>
</ol>
```

Use `<ol>` whenever reordering the items would change their meaning (steps, rankings) — otherwise use `<ul>`.

### Definition lists — term/description pairs

```html
<dl>
  <dt>HTML</dt>
  <dd>The markup language that structures web content.</dd>
  <dt>CSS</dt>
  <dd>The language that styles HTML content.</dd>
</dl>
```

Useful for glossaries, metadata pairs, or FAQ-style term/answer content.

### Nesting lists

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>
  <li>Backend</li>
</ul>
```

A nested `<ul>`/`<ol>` goes *inside* the `<li>` of the parent item it belongs to.

## Common Pitfalls

- Faking a list with `<br>`-separated lines or `<p>` tags — loses the semantic "list of N items" structure entirely.
- Using `<ul>` for genuinely sequential steps (should be `<ol>`), or vice versa.
- Nesting a `<ul>` as a sibling of `<li>` instead of inside it, which produces invalid markup.

## Key Takeaways

- `<ul>` = order doesn't matter; `<ol>` = order matters; `<dl>` = term/description pairs.
- Nested lists live inside the `<li>` of their parent item, not alongside it.
- Real list elements give screen readers structural information ("list, 5 items") that visually-faked lists never do.
