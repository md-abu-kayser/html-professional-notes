# What Is HTML?

## Overview

HTML (HyperText Markup Language) is the language that structures content on the web — every heading, paragraph, image, link, and form you've ever seen in a browser is described by it. It was created by Tim Berners-Lee in 1991 and is now maintained as a "living standard" by the WHATWG.

## Why It Matters

HTML is the only one of the three core web languages a browser *requires* — CSS and JavaScript are optional. Understanding what HTML's actual job is (structure and meaning) versus what CSS and JavaScript do prevents a huge category of bad habits later.

## Core Concepts

### HTML's job: structure and meaning, not appearance

```html
<h1>Page Title</h1>
<p>This is a paragraph of body text.</p>
```

This tells the browser "this text is the main heading" and "this text is a paragraph" — nothing about color, font, or spacing. That separation is intentional.

### The three-language division of labor

| Language | Responsibility |
|---|---|
| **HTML** | Structure and meaning ("this is a heading," "this is a list") |
| **CSS** | Presentation ("headings are blue and 32px") |
| **JavaScript** | Behavior ("open a menu when this button is clicked") |

### HTML is markup, not a programming language

HTML has no variables, loops, or logic — it's a **markup language**: plain text wrapped in tags that describe what that text *is*. This is why HTML "runs" instantly with no compilation step; the browser just parses and displays it.

### Where HTML comes from today

HTML5 (the current living standard) is developed collaboratively by browser vendors through the WHATWG, with the W3C also publishing a recommendation. In practice, "HTML5" is just referred to as "HTML" today — there's no HTML6 on a separate track; the spec evolves continuously.

## Common Pitfalls

- Using HTML elements for their visual default instead of their meaning — e.g. a `<div>` styled to look like a button instead of an actual `<button>`, which breaks keyboard and screen-reader access.
- Thinking HTML "does" anything — it describes; CSS styles that description; JavaScript makes it interactive.

## Key Takeaways

- HTML structures and gives meaning to content; it doesn't control appearance (CSS) or behavior (JavaScript).
- It's a markup language, not a programming language — no logic, just structure.
- "HTML5" and "HTML" are effectively the same thing today — a continuously evolving living standard.
- Choosing the right element for its *meaning* (not its default look) is the foundation everything else in this repo builds on.
