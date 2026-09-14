# Attribute and State Selectors

Attribute selectors can test existence, exact values, token membership, prefixes, suffixes, and substrings. They are useful when the state is already represented in HTML. Pseudo-classes such as `:hover`, `:focus`, `:focus-visible`, `:checked`, `:disabled`, `:required`, and `:valid` match browser-known states without extra classes.

```css
input[required] { border-inline-start-width: 3px; }
input[type="email"] { inline-size: 24rem; }
a[href^="https:"] { text-decoration-style: dotted; }

button:hover { filter: brightness(1.05); }
button:focus-visible { outline: 3px solid currentColor; }
input:checked + label { font-weight: 700; }
```

Do not depend on hover for essential functionality because not every device has hover. Keep a visible keyboard focus indicator, typically with `:focus-visible`. Native form pseudo-classes stay synchronized with the control, so prefer them over duplicating the same state in application classes unless your product has a separate state concept.
