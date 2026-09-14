# Source Order and Focus Order

Write HTML in the order a reader should encounter it. CSS Grid and Flexbox can change visual placement, but they do not normally change DOM reading order or sequential keyboard focus. A visually attractive reordering can therefore create a page whose keyboard or screen-reader sequence feels unrelated to what appears on screen.

```html
<main>
  <h1>Checkout</h1>

  <section>
    <h2>Contact details</h2>
    ...
  </section>

  <section>
    <h2>Payment</h2>
    ...
  </section>
</main>
```

Use the DOM as the canonical content and interaction order, then let CSS create columns, sidebars, and responsive arrangements that preserve that logic. Avoid positive tabindex as a repair for incorrect source order. If the visual design requires a dramatically different sequence, reconsider the markup or the design instead of maintaining two competing orders.
