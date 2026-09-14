# Writing Modes and Logical Properties

CSS describes layout in logical axes so it can support left-to-right, right-to-left, and vertical writing systems. The inline axis follows text progression; the block axis follows the stacking of lines and blocks. `writing-mode` can change those axes, while document direction should normally come from HTML's semantic direction information.

```css
.card {
  inline-size: min(100%, 40rem);
  padding-block: 1rem;
  padding-inline: 1.25rem;
}

.badge {
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

Logical properties express geometry relative to flow: `inline-size`/`block-size`, `margin-inline`, `padding-block`, and logical inset properties. They reduce duplicated direction-specific overrides and make components more portable. Use physical properties such as `top` or `left` when the relationship is genuinely physical, not merely because the initial design was left-to-right.
