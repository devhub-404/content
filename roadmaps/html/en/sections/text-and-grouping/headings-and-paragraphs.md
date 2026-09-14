# Headings and Paragraphs

HTML provides six heading levels: `h1`, `h2`, `h3`, `h4`, `h5`, and `h6`. `h1` is the highest level and `h6` the lowest. The levels express hierarchy, not a preferred font size. A document commonly has a clear top-level `h1`, with lower levels used as the content becomes more deeply nested.

```html
<h1>Gardening guide</h1>
<p>This guide covers vegetables and herbs.</p>

<h2>Vegetables</h2>
<h3>Tomatoes</h3>
<h4>Feeding tomatoes</h4>

<h2>Herbs</h2>
<h3>Basil</h3>
```

`p` represents a paragraph of prose. Use headings to name sections and paragraphs for ordinary blocks of text. Keep heading levels logically ordered: an `h3` normally belongs under an `h2`, and an `h4` under an `h3`. CSS can make any heading larger or smaller, so never choose `h4` merely because its browser default happens to look right.
