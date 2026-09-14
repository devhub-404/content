# `:is()`, `:where()`, `:not()`, and `:has()`

Functional selectors reduce repetition and express richer conditions. `:is()` matches any argument and takes specificity from its most specific argument. `:where()` matches the same way but contributes zero specificity. `:not()` excludes matches. `:has()` lets the subject match because a relative selector succeeds, enabling parent- and sibling-aware styling.

```css
article :is(h2, h3, h4) { line-height: 1.2; }
:where(article, section) > p { max-inline-size: 68ch; }
button:not(:disabled) { cursor: pointer; }
.card:has(img) { grid-template-columns: 8rem 1fr; }
```

Choose `:is()` versus `:where()` based on cascade intent, not convenience alone. Use `:has()` for meaningful relationships that already exist in the DOM, such as styling a card differently when it contains media. Application state that is already known to JavaScript can still be clearer as an explicit class or data attribute than as a complicated relational selector.
