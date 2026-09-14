# Quotes and Preformatted Text

`blockquote` represents a quotation that forms its own block; `q` is for short quotations inside a line of text. If readers need the source, provide visible source information rather than relying only on metadata. A citation can be linked or named in nearby content.

```html
<blockquote>
  <p>The simplest solution was the most reliable.</p>
</blockquote>

<pre><code>function add(a, b) {
  return a + b;
}</code></pre>
```

`pre` preserves source whitespace and line breaks, so it is useful for code, ASCII diagrams, and other preformatted material. Code blocks commonly combine `pre` with `code`: `pre` preserves layout while `code` gives the text its code semantics. Because indentation inside `pre` becomes visible, format its source deliberately.
