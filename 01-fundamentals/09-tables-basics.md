# Tables Basics

## Overview

`<table>` exists for exactly one purpose: displaying **tabular data** — rows and columns of related values. This lesson covers the core building blocks; semantic/accessible table structure (`<thead>`, `<caption>`, `scope`) is covered in depth in [02-semantic-html/07](../02-semantic-html/07-semantic-tables-caption-thead-tbody-tfoot.md).

## Why It Matters

Tables were widely (mis)used for page layout in the early 2000s before CSS layout matured. That history is why "just use a table" still raises eyebrows — but for actual tabular data, `<table>` remains the correct, accessible choice.

## Core Concepts

### The basic structure

```html
<table>
  <tr>
    <th>Name</th>
    <th>Role</th>
  </tr>
  <tr>
    <td>Ada Lovelace</td>
    <td>Mathematician</td>
  </tr>
  <tr>
    <td>Grace Hopper</td>
    <td>Programmer</td>
  </tr>
</table>
```

- `<table>` — the container.
- `<tr>` — a table row.
- `<th>` — a header cell (bold, centered by default; also carries semantic meaning for screen readers).
- `<td>` — a standard data cell.

### When to use a table

Use `<table>` when data genuinely has rows *and* columns that relate to each other (a schedule, a price comparison, statistics). Don't use it to arrange unrelated page sections side-by-side — that's a CSS layout job (Flexbox/Grid, covered in [06-advanced-layout](../06-advanced-layout/README.md)).

## Common Pitfalls

- Using tables for visual page layout instead of actual tabular data — an accessibility and maintainability problem inherited from 1990s web design.
- Using `<td>` for header cells instead of `<th>` — loses the semantic distinction assistive technology relies on.
- Forgetting that basic tables like the one above aren't fully accessible on their own for complex data — see the semantic table lesson for `scope`, `<thead>`/`<tbody>`, and `<caption>`.

## Key Takeaways

- `<table>` is for tabular data only, never for page layout — that's what CSS Flexbox/Grid are for.
- `<th>` marks header cells with real semantic meaning; `<td>` marks standard data cells.
- A basic table (this lesson) works but isn't fully accessible — [02-semantic-html/07](../02-semantic-html/07-semantic-tables-caption-thead-tbody-tfoot.md) covers what a production-quality table needs.
