# `display` and Normal Flow

Normal flow lays out a useful document before you choose a specialized layout system. Block-level boxes generally stack in the block direction and use available inline space; inline content participates in line boxes with surrounding text. The `display` property controls outer participation and the inner formatting context.

```css
.badge { display: inline-block; }
.toolbar { display: flex; }
.gallery { display: grid; }
.wrapper { display: flow-root; }
```

`inline-block` is an inline-level atomic box with block-like internal sizing. `flex` and `grid` create flex and grid formatting contexts for direct children. `flow-root` creates an independent block formatting context. `display: none` removes a subtree from box generation, while `display: contents` removes the element's principal box but leaves descendant boxes; use `contents` cautiously because box removal can affect accessibility and other behavior.
