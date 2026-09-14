# Pseudo-elements and Generated Content

Pseudo-elements style generated or abstract parts of an element. `::before` and `::after` can generate presentation with `content`; `::marker` targets list markers; `::selection` targets selected text; `::first-line` and `::first-letter` target typographic fragments where applicable.

```css
.tag::before {
  content: "#";
  opacity: .6;
}

li::marker { font-weight: 700; }

::selection {
  background: Highlight;
  color: HighlightText;
}
```

Generated content is presentation, so do not put essential instructions or labels only in `content`. Pseudo-elements can form real visual boxes and participate in positioning, stacking, and overflow. Treat them with the same layout discipline as ordinary boxes even though they do not appear as normal element nodes in the HTML.
