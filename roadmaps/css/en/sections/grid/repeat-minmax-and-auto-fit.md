# `repeat()`, `minmax()`, and Auto-fit Grids

`repeat()` removes repeated track syntax, while `minmax()` gives a track lower and upper bounds. Combined with `auto-fit` or `auto-fill`, Grid can create as many tracks as fit in the available space. This often produces responsive card layouts without a viewport breakpoint.

```css
.cards {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(min(16rem, 100%), 1fr));
  gap: 1rem;
}
```

`auto-fit` collapses empty repeated tracks so existing tracks can expand; `auto-fill` keeps the repeated track slots. The `min(16rem, 100%)` minimum avoids forcing overflow when the entire container is narrower than the nominal card minimum. Use this intrinsic pattern when the requirement is simply “fit as many usable columns as space allows.”
