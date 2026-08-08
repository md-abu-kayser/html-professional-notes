# Headings & Paragraphs

## Overview

`<h1>` through `<h6>` and `<p>` are the most common elements on the web, and also the most frequently misused — chosen for their default font size instead of their structural meaning.

## Why It Matters

Heading levels form a **document outline** that screen reader users navigate directly (many jump heading-to-heading rather than reading linearly). Skipping levels or choosing headings by size, not meaning, breaks that navigation invisibly for sighted users while being a real obstacle for others.

## Core Concepts

### Six levels, one meaning: hierarchy

```html
<h1>Page Title</h1>
<h2>Major Section</h2>
<h3>Subsection</h3>
<h2>Another Major Section</h2>
```

- Exactly one `<h1>` per page, describing the page's main content.
- Levels nest to reflect actual content hierarchy — don't skip from `<h2>` straight to `<h4>` just because `<h3>` "looks too big."

### Paragraphs

```html
<p>This is a paragraph. It can contain inline elements like <a href="#">links</a> and <strong>bold text</strong>, but not block-level elements like another paragraph or a heading.</p>
```

`<p>` represents a single block of related text — browsers add spacing above/below by default, but that's a *side effect*, not the reason to use it.

## Common Pitfalls

- Choosing a heading level because of its default size rather than its place in the outline — fix the size with CSS instead, e.g. `<h3>` styled larger if needed.
- Using multiple `<h1>` elements for stylistic "big text" throughout a page.
- Wrapping non-paragraph content (a single image, a button) in `<p>` just for the default spacing — use CSS margin instead.

## Key Takeaways

- Headings (`<h1>`–`<h6>`) describe document structure, not font size — style them with CSS, not by picking the "right-sized" level.
- Use exactly one `<h1>` per page and don't skip heading levels.
- `<p>` represents one block of related text and can hold inline elements but not other block elements.
- Document outline (covered in depth in [02-semantic-html/04](../02-semantic-html/04-headings-outline-and-accessibility.md)) is a real navigation tool for screen reader users, not just a visual convention.
