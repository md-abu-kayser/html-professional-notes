# Text Editors & Tools

## Overview

HTML needs nothing more than a plain text editor to write — but the right editor and extensions turn error-prone manual typing into fast, validated, auto-completed markup. This lesson sets up a productive editing environment.

## Why It Matters

Typos in HTML (an unclosed tag, a misspelled attribute) fail silently in the browser — there's no compiler stopping you. A good editor catches these mistakes as you type instead of during a confused debugging session later.

## Core Concepts

### Choosing an editor

- **VS Code** (free) — the most common choice; strong HTML/CSS support out of the box, huge extension ecosystem.
- **Sublime Text** — fast and lightweight, popular for quick edits.
- **WebStorm** (paid) — a full IDE with deep HTML/CSS/JS integration, common on larger teams.

### Essential VS Code extensions for HTML

| Extension | What it does |
|---|---|
| **Emmet** (built-in) | Expands shorthand like `nav>ul>li*3` into full markup — covered in [11-tools-and-workflow/01](../11-tools-and-workflow/01-emmet-and-snippets.md) |
| **Live Server** | Serves your HTML with auto-reload on save |
| **Prettier** | Auto-formats HTML/CSS/JS consistently on save |
| **HTMLHint** | Lints HTML for common mistakes — see [11-tools-and-workflow/03](../11-tools-and-workflow/03-linting-htmlhint.md) |

### A minimal productive setup

```json
{
  "editor.formatOnSave": true,
  "emmet.triggerExpansionOnTab": true,
  "html.autoClosingTags": true
}
```

## Common Pitfalls

- Writing HTML in a plain text app (Notepad, TextEdit) with no syntax highlighting — errors become far harder to spot visually.
- Skipping auto-close-tag features and then losing time to mismatched tags.
- Not using Live Server (or similar) and instead manually refreshing a browser after every change.

## Key Takeaways

- Any modern code editor works; VS Code is the most common free choice with strong out-of-box HTML support.
- Emmet, Live Server, Prettier, and a linter form a productive baseline toolkit.
- Syntax highlighting and auto-closing tags catch mistakes as you type, not after you run the page.
