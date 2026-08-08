# Validating HTML

## Overview

HTML **validation** checks your markup against the official spec — catching unclosed tags, invalid nesting, duplicate IDs, and missing required attributes. This lesson covers why and how to validate.

## Why It Matters

Browsers are extremely forgiving — they'll silently "fix" broken HTML rather than refuse to render it, which means invalid markup often looks fine while quietly causing inconsistent behavior across browsers, broken accessibility, or unpredictable CSS/JS targeting.

## Core Concepts

### The official validator

The [W3C Markup Validator](https://validator.w3.org/) checks a URL, file upload, or pasted markup against the HTML5 spec and reports errors and warnings with line numbers.

### Validating locally with `tidy`

HTML Tidy is a command-line validator/formatter that doesn't require uploading anything:

```bash
tidy -q -e index.html
# -q: quiet (suppress the reformatted output)
# -e: only report errors/warnings, don't print the "tidied" HTML
```

Every code snippet in [15-code-snippets](../15-code-snippets/README.md) in this repo is validated with `tidy` before being committed.

### What validation catches that browsers hide

```html
<!-- duplicate IDs: invalid, but browsers won't warn you -->
<div id="header">...</div>
<div id="header">...</div>

<!-- unclosed tag: browsers auto-close it, often not where you'd expect -->
<p>Some text
<p>More text
```

### Validation is a floor, not a ceiling

Valid HTML isn't automatically *good* HTML — you can validate cleanly while still choosing a `<div>` where a `<section>` belongs, or writing inaccessible markup. Validation catches syntax errors; it doesn't judge semantic correctness (that's [02-semantic-html](../02-semantic-html/README.md)) or accessibility (that's [07-accessibility-a11y](../07-accessibility-a11y/README.md)).

## Common Pitfalls

- Assuming "it looks right in the browser" means the HTML is valid — browsers hide most structural errors from you.
- Treating a clean validator pass as proof the markup is accessible or semantically correct — it isn't; it only checks syntax.
- Never validating until a bug forces the investigation — cheaper to run it as a habit before every commit.

## Key Takeaways

- Browsers silently repair invalid HTML instead of erroring — which hides real bugs rather than fixing them.
- Validate with the [W3C Validator](https://validator.w3.org/) online or `tidy -e` locally/in CI.
- Valid HTML is a syntax floor, not a guarantee of good semantics or accessibility — both need separate attention.
- Make validation a routine habit, not a last resort when something's already broken.
