# Elements, Tags & Attributes

## Overview

An HTML **element** is made of tags, optional attributes, and (usually) content. This lesson covers the exact vocabulary — tag, element, attribute, void element — that the rest of the curriculum assumes you know precisely.

## Why It Matters

"Tag" and "element" get used loosely in casual conversation, but knowing the precise difference matters once you're reading the HTML spec, debugging validator errors, or discussing markup with other developers.

## Core Concepts

### Tags vs. elements

```html
<p>Hello, world!</p>
```

- `<p>` is the **opening tag**; `</p>` is the **closing tag**.
- `<p>Hello, world!</p>` — tags plus content — is the **element**.

### Attributes

Attributes add extra information inside the opening tag, as `name="value"` pairs:

```html
<a href="https://example.com" target="_blank" rel="noopener">Visit</a>
```

Here `href`, `target`, and `rel` are attributes of the `<a>` element. Attribute values are almost always quoted (double quotes are the convention).

### Void elements — no closing tag, no content

Some elements are **self-closing by definition** because they never wrap content:

```html
<img src="photo.jpg" alt="A mountain at sunset">
<br>
<input type="text" name="username">
<hr>
```

Writing `<img ...></img>` is invalid — `<img>` (and `<br>`, `<input>`, `<hr>`, `<meta>`, `<link>`) are void elements.

### Nesting rules

Elements can contain other elements, but must **close in the reverse order they opened** (proper nesting):

```html
<!-- correct -->
<p>Some <strong>bold</strong> text.</p>

<!-- incorrect: tags cross each other -->
<p>Some <strong>bold</p></strong> text.
```

## Common Pitfalls

- Adding a closing tag to a void element (`<br></br>`) — unnecessary and invalid.
- Forgetting to quote attribute values with spaces in them (`class=nav item` breaks; `class="nav item"` works).
- Improper nesting ("tag soup") — browsers often recover gracefully, which hides the mistake instead of erroring loudly.

## Key Takeaways

- An element = opening tag + content + closing tag; a tag is just one half of that pair.
- Attributes live inside the opening tag as `name="value"` pairs.
- Void elements (`<img>`, `<br>`, `<input>`, `<hr>`, `<meta>`, `<link>`) never have a closing tag or content.
- Tags must close in the reverse order they opened — no crossing.
