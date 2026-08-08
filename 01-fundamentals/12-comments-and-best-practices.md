# Comments & Best Practices

## Overview

HTML comments (`<!-- -->`) are never rendered or read aloud, making them useful for leaving notes in markup. This lesson also covers baseline conventions — indentation, attribute ordering, naming — that keep HTML readable across a team.

## Why It Matters

HTML has no compiler enforcing style the way `gofmt` does for Go — consistency has to come from convention and discipline, which matters enormously once more than one person touches a codebase.

## Core Concepts

### Comments

```html
<!-- TODO: replace placeholder image before launch -->
<img src="placeholder.jpg" alt="Product photo">

<!-- Section: Newsletter signup -->
<section>
  ...
</section>
```

Comments are visible in "View Source" and browser DevTools, so never put sensitive information (API keys, internal notes) in them.

### Indentation and nesting

```html
<ul>
  <li>Item one</li>
  <li>Item two
    <ul>
      <li>Nested item</li>
    </ul>
  </li>
</ul>
```

Consistent 2-space (or 4-space — pick one) indentation that mirrors nesting depth makes structure scannable at a glance. Tools like Prettier ([11-tools-and-workflow/02](../11-tools-and-workflow/02-prettier-and-code-formatters.md)) automate this entirely.

### Naming conventions for `class`/`id`

```html
<!-- kebab-case is the near-universal convention -->
<div class="product-card product-card--featured" id="product-142">
```

- `class` — for styling hooks that can repeat across elements.
- `id` — for a single, unique element (also used as a link fragment target, `#product-142`).

### Lowercase tags and attributes

```html
<!-- conventional -->
<div class="wrapper">

<!-- valid but non-conventional -->
<DIV CLASS="wrapper">
```

HTML tag/attribute names are case-insensitive, but lowercase is the universal convention.

## Common Pitfalls

- Leaving sensitive notes or debug info in HTML comments that ship to production — anyone can view them via "View Source."
- Mixing tabs and spaces, or inconsistent indent width, across a file.
- Using `id` for styling that's meant to repeat — `id` must be unique per page; use `class` instead.

## Key Takeaways

- Comments (`<!-- -->`) are visible in page source — never put secrets or sensitive notes in them.
- Consistent indentation mirroring nesting depth is a readability, not aesthetics, issue — automate it with a formatter.
- `class` is for repeatable styling hooks; `id` must be unique per page.
- Lowercase tags/attributes is the universal (if not strictly required) convention.
