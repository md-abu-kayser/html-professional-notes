# Forms Basics

## Overview

`<form>` collects user input and submits it — this lesson covers the essential elements (`<input>`, `<button>`) and attributes needed for a working form; the full input-type reference, validation, and accessibility live in [03-forms-and-input](../03-forms-and-input/README.md).

## Why It Matters

Forms are how the web collects information — logins, checkouts, search, signups. Getting the basic structure right (correct `<label>` association, correct `type`, a real `<button>`) is the difference between a form that works for everyone and one that quietly excludes keyboard and screen-reader users.

## Core Concepts

### A minimal, correct form

```html
<form action="/submit" method="post">
  <label for="email">Email address</label>
  <input type="email" id="email" name="email" required>

  <button type="submit">Subscribe</button>
</form>
```

### Key attributes

- **`action`** — the URL the form data is sent to.
- **`method`** — `get` (data in the URL, for searches/filters) or `post` (data in the request body, for anything that changes server state).
- **`<input type="...">`** — controls both behavior and the on-screen keyboard shown on mobile (`email`, `tel`, `number` all differ).
- **`name`** — the key the value is submitted under; without it, the field's value is not sent at all.

### Labels are not optional

```html
<label for="email">Email address</label>
<input type="email" id="email" name="email">
```

The `for`/`id` pair links a label to its input — clicking the label focuses the input, and screen readers announce the label when the input receives focus. A placeholder is not a substitute for a label (it disappears on typing and isn't reliably announced).

### Buttons: know the three types

```html
<button type="submit">Submits the form</button>
<button type="reset">Clears the form</button>
<button type="button">Does nothing by default — for JS-driven actions</button>
```

Inside a `<form>`, a `<button>` with no explicit `type` defaults to `"submit"` — a common source of accidental form submissions.

## Common Pitfalls

- Using `placeholder` instead of a real `<label>`.
- Forgetting `name` on an input — the field silently isn't included in the submitted data.
- Leaving `type` off a `<button>` inside a form, causing unintended submits.
- Using `<div>`/`<span>` with click handlers instead of real form elements — breaks native validation, autofill, and keyboard behavior.

## Key Takeaways

- Every input needs an associated `<label>` via matching `for`/`id` — not just a placeholder.
- `name` determines whether (and under what key) a field's value is actually submitted.
- `<button>` defaults to `type="submit"` inside a form — set `type="button"` explicitly for non-submitting buttons.
- The full input-type reference, validation attributes, and accessibility patterns are covered in [03-forms-and-input](../03-forms-and-input/README.md).
