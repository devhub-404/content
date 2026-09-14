# Structural Pseudo-classes

Structural pseudo-classes match elements from sibling structure. `:first-child`, `:last-child`, `:only-child`, type-aware variants, and the `:nth-*()` family cover common positional relationships. `:nth-child()` accepts formulas such as `odd`, `2n`, or `3n + 1`, and modern syntax can count only siblings matching an `of` selector.

```css
li:first-child { margin-block-start: 0; }
tr:nth-child(even) { background: rgb(0 0 0 / .04); }
.card:nth-child(-n + 3 of .featured) { border-width: 2px; }
```

Use structural selectors when position is genuinely part of the presentation, such as striped table rows or spacing between siblings. Do not encode business state through position: if an item is featured regardless of where it appears, keep that state explicit in markup and use the structural selector only for the positional portion.
