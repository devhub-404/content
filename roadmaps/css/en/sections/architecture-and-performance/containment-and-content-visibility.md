# Containment and `content-visibility`

Containment tells the browser that a subtree can be treated as independent in selected aspects such as size, inline-size, layout, style, or paint. That can reduce the scope of layout and painting work, but containment also changes behavior such as containing blocks, stacking, clipping, and intrinsic sizing.

```css
.widget {
  contain: layout paint;
}

.feed-item {
  content-visibility: auto;
  contain-intrinsic-size: auto 24rem;
}
```

`content-visibility: auto` lets the browser skip much of the rendering work for off-screen content while keeping it in the document. An intrinsic-size estimate can reduce scroll jumps before skipped content is rendered. Use these features for large independent regions after testing their layout consequences; containment is not a free performance flag.
