# How the Web Works

## Overview

Before writing HTML, it helps to know what actually happens between typing a URL and seeing a page. This lesson covers the request/response cycle, what a browser does with the HTML it receives, and where HTML fits in that pipeline.

## Why It Matters

HTML isn't just markup you write — it's a document a browser has to fetch, parse, and render under real constraints (network latency, parsing rules, security policies). Understanding that pipeline explains *why* certain HTML practices exist — like why script placement matters, or why the `<head>` loads before the visible page.

## Core Concepts

### The request/response cycle

1. You type a URL; the browser resolves the domain to an IP address via **DNS**.
2. The browser opens a connection and sends an **HTTP request** for that resource.
3. The server sends back an **HTTP response** — status code, headers, and (usually) an HTML document as the body.
4. The browser starts parsing the HTML **as it arrives**, not after the whole file downloads.

### What the browser does with HTML

- **Parsing** — the browser reads HTML top to bottom and builds the **DOM** (Document Object Model), a tree representation of every element.
- **Fetching sub-resources** — as the parser hits `<link>`, `<img>`, and `<script>` tags, it queues up additional requests for CSS, images, and JavaScript.
- **Rendering** — once enough of the DOM and CSS (the **CSSOM**) are ready, the browser computes layout and paints pixels to the screen.

```html
<!-- The parser hits this tag and immediately starts a request for style.css,
     without waiting for the rest of the document to load. -->
<link rel="stylesheet" href="style.css">
```

### Rendering engines

Different browsers use different rendering engines to turn HTML/CSS into pixels: **Blink** (Chrome, Edge, Opera), **WebKit** (Safari), and **Gecko** (Firefox). They agree on the HTML/CSS specifications closely enough that "write once, works everywhere" is realistic — but edge cases differ, which is why cross-browser testing (see [12-testing-and-debugging](../12-testing-and-debugging/README.md)) still matters.

## Common Pitfalls

- Assuming the whole page loads before anything renders — modern browsers render incrementally, which is exactly why blocking resources (unoptimized `<script>` tags) can freeze that process.
- Confusing the **DOM** (what the browser built from your HTML) with the **HTML source** (what you wrote) — JavaScript can change the DOM without changing the original source file.
- Not realizing DNS lookup, connection setup, and download are separate time costs — "the page is slow" can mean any one of them.

## Key Takeaways

- Loading a page is a request/response cycle: DNS resolution → HTTP request → HTTP response → parsing → rendering.
- The browser builds a DOM tree from your HTML as it parses — this tree, not your source file, is what JavaScript and CSS actually manipulate.
- Rendering starts before the full document finishes downloading — resource placement in your HTML affects perceived speed.
- Different browsers use different rendering engines; they converge on the same specs but can differ on edge cases.
