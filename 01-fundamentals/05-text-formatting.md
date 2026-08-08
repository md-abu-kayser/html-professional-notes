# Text Formatting

## Overview

HTML has several inline elements for formatting text — but unlike `<b>` (bold) or `<i>` (italic) which are purely visual, most modern formatting elements carry **semantic meaning** that CSS-only styling can't express.

## Why It Matters

`<strong>` and `<b>` can look identical by default, but a screen reader announces `<strong>` with added emphasis and skips straight past `<b>` — the visual result is the same, the meaning conveyed to assistive technology is not.

## Core Concepts

### Semantic vs. purely presentational

| Element | Meaning | Default look |
|---|---|---|
| `<strong>` | Strong importance/urgency | bold |
| `<em>` | Stress emphasis (changes sentence meaning) | italic |
| `<b>` | Stylistically offset text, no extra importance | bold |
| `<i>` | Stylistically offset text (e.g. a term, a name), no emphasis | italic |
| `<mark>` | Highlighted/relevant text (e.g. a search match) | yellow highlight |
| `<small>` | Side comments, fine print | smaller text |
| `<del>` / `<ins>` | Deleted / inserted content (e.g. tracked changes) | strikethrough / underline |
| `<sub>` / `<sup>` | Subscript / superscript | lowered / raised text |

### Choosing between them

```html
<p><strong>Warning:</strong> this action cannot be undone.</p>
<p>The word <em>not</em> changes this sentence's meaning entirely.</p>
<p>The <i>Titanic</i> sank in 1912.</p>
<p>Search results for <mark>accessibility</mark>.</p>
```

The rule of thumb: **if removing the tag would change what the sentence means, use `<strong>`/`<em>`; if it's purely a stylistic convention (book titles, technical terms), `<b>`/`<i>` are still valid.**

## Common Pitfalls

- Reaching for `<b>`/`<i>` by habit for anything that should be `<strong>`/`<em>` — loses meaning for assistive technology.
- Using `<strong>` or `<em>` purely for visual bold/italic styling with no actual emphasis intended — style with CSS (`font-weight`, `font-style`) instead when there's no semantic reason.
- Nesting multiple `<strong>`/`<em>` for "extra" emphasis — doesn't reliably convey more importance and isn't standard practice.

## Key Takeaways

- `<strong>`/`<em>` carry meaning that assistive technology announces differently than `<b>`/`<i>`.
- Ask "does removing this tag change the sentence's meaning?" to choose between the semantic and purely stylistic options.
- `<mark>`, `<small>`, `<del>`/`<ins>`, and `<sub>`/`<sup>` each have a specific, narrow meaning — don't repurpose them for their default look alone.
- If there's no semantic reason at all, style with CSS rather than reaching for a formatting tag.
