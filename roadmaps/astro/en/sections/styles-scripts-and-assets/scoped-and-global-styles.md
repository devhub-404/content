# Scoped and Global Styles

Styles inside an Astro component are scoped to that component by default, so selectors do not normally leak to unrelated markup. Global styles can be imported or explicitly marked global for design tokens, resets, typography, and other site-wide rules.

```astro
<style>
  h2 { color: rebeccapurple; }
</style>

<style is:global>
  :root { font-family: system-ui, sans-serif; }
</style>

<h2>Scoped heading</h2>
```

Use normal CSS architecture rather than relying on scoping to compensate for unclear selectors. Put reusable tokens and global element rules in shared styles, while component-specific layout and presentation can stay close to the component. Understand specificity and cascade because Astro still produces ordinary CSS.
