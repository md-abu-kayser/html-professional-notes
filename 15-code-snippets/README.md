# 15 — Code Snippets

> ✅ **Status:** Complete — 6/6 snippets

Standalone, validated `.html` files with scoped CSS — open any one directly in a browser and it renders correctly, not just markup you have to imagine. Each demonstrates one production pattern with inline comments explaining the *why*, not just the *what*.

| File | Pattern | Notable techniques |
|---|---|---|
| [`semantic-page-template.html`](./semantic-page-template.html) | Full semantic page skeleton | `header`/`nav`/`main`/`aside`/`footer`, skip link |
| [`accessible-form.html`](./accessible-form.html) | Accessible form markup | `fieldset`/`legend`, `aria-describedby`, `role="alert"` |
| [`responsive-navbar.html`](./responsive-navbar.html) | No-JS responsive nav toggle | keyboard-operable checkbox hack, `visually-hidden` utility |
| [`hero-section.html`](./hero-section.html) | Responsive hero with art direction | `<picture>`/`<source media>`, `clamp()` type scale |
| [`data-table.html`](./data-table.html) | Accessible data table | `caption`, `scope`, `thead`/`tbody`/`tfoot` |
| [`email-boilerplate.html`](./email-boilerplate.html) | Cross-client HTML email | table-based layout, MSO conditional comments, preheader text |

## Using a snippet

Open the file directly in a browser — every snippet is self-contained (styles included) except `email-boilerplate.html`, which references a placeholder `logo.png` you'd replace with a hosted image URL.

## Validating

Every snippet in this folder is checked with [HTML Tidy](https://www.html-tidy.org/) before being committed:

```bash
tidy -q -e semantic-page-template.html
```
