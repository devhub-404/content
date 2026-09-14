# Design Tokens and Theme Architecture

A maintainable token system separates raw primitives from semantic roles. A palette token can describe a literal color, while `--color-action` or `--color-surface` describes how the value is used. Components should consume semantic tokens so themes can override meaning without rewriting component selectors.

```css
@layer tokens {
  :root {
    --color-blue-600: oklch(52% .2 255);
    --color-surface: white;
    --color-action: var(--color-blue-600);
    --space-card: 1rem;
  }

  [data-theme="dark"] {
    --color-surface: #151515;
  }
}
```

Cascade layers can give tokens, base rules, components, and utilities explicit precedence. Keep the public token surface intentionally small: every custom property that downstream code relies on becomes part of a styling API. Do not create hundreds of global variables simply because custom properties are easy to declare.
