# Strings and Template Literals

Strings are immutable sequences of UTF-16 code units. They can be written with single quotes, double quotes, or template literals. Template literals use backticks, can span lines, and interpolate expressions with `${...}`. String methods return new values rather than changing the original string.

```js
const first = "Ada";
const last = "Lovelace";
const label = `${first} ${last}`;

const message = `Hello,
${label}!`;
```

Indexing and `.length` work in UTF-16 code units, so some Unicode characters occupy more than one unit. `for...of` handles ordinary Unicode code points better than indexing, but a visible grapheme may still contain several code points. Use `Intl` for locale-sensitive comparison, sorting, segmentation, and formatting instead of assuming ASCII-like text.
