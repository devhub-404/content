# Stacking Contexts and `z-index`

`z-index` does not create one global page-wide number line. Elements are grouped into stacking contexts, and children are ordered inside their own context. A child with `z-index: 9999` cannot escape an ancestor stacking context that is painted below a sibling context.

```css
:root {
  --z-sticky: 10;
  --z-overlay: 100;
  --z-modal: 110;
}

.site-header {
  position: sticky;
  z-index: var(--z-sticky);
}
```

Positioned elements with non-auto `z-index`, transforms, opacity below 1, filters, isolation, and some containment features can create stacking contexts. When overlap is wrong, inspect context boundaries instead of increasing numbers indefinitely. A small documented scale for intentional layers such as sticky UI, overlays, modals, and toasts is easier to maintain than arbitrary values.
