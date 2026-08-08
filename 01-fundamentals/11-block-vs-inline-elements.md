# Block vs. Inline Elements

## Overview

Every HTML element has a default **display** behavior: block-level elements stack vertically and take the full available width; inline elements flow within a line of text. This lesson covers the distinction and why it constrains what can nest inside what.

## Why It Matters

Nesting a block element inside an inline one (or misunderstanding which is which) causes some of the most confusing "why won't this lay out right" bugs for beginners — and CSS's `display` property can change this default, which is worth knowing before it surprises you.

## Core Concepts

### Block-level elements

Start on a new line and stretch to fill their container's width by default: `<div>`, `<p>`, `<h1>`–`<h6>`, `<ul>`/`<ol>`, `<table>`, `<form>`, `<section>`, `<header>`, `<footer>`.

```html
<div>Block 1</div>
<div>Block 2</div>
<!-- These stack vertically, each on its own line -->
```

### Inline elements

Flow within a line of surrounding text and only take up as much width as their content needs: `<a>`, `<span>`, `<strong>`, `<em>`, `<img>`, `<label>`, `<input>`.

```html
<p>This is <strong>bold</strong> and <a href="#">linked</a> text in one line.</p>
```

### The nesting rule

Block-level elements can generally contain inline elements, but **inline elements should not contain block-level elements**:

```html
<!-- correct -->
<p>Some <strong>important</strong> text.</p>

<!-- invalid: a block element inside an inline one -->
<span><div>...</div></span>
```

### CSS can override the default

`display: inline`, `display: block`, `display: inline-block`, and `display: flex` all let CSS change an element's default behavior — the HTML tag you choose should still reflect *meaning*, even if CSS later changes how it's displayed.

## Common Pitfalls

- Nesting a `<div>` inside a `<span>` or `<a>` (in older HTML) — modern HTML5 actually permits block content inside `<a>`, but it's still worth understanding the general rule for other inline elements.
- Assuming an element's tag name tells you nothing about its layout — the default `display` value is a real, specified part of each element's behavior.
- Forgetting that CSS can (and often does) change these defaults — "it's a `<span>` so it must be inline" isn't guaranteed once stylesheets are involved.

## Key Takeaways

- Block-level elements stack vertically and fill available width by default; inline elements flow within a line of text.
- Inline elements generally shouldn't contain block-level elements.
- CSS `display` can override any element's default — but choose the HTML tag for its meaning first.
- This default behavior is what makes Flexbox and Grid (covered in [06-advanced-layout](../06-advanced-layout/README.md)) necessary tools for real layout control.
