# `will-change` and Rendering Performance

CSS changes can trigger style recalculation, layout, paint, and compositing work depending on the property and context. Transform and opacity animations often avoid repeated layout, but actual cost depends on surface size, effects, device, and browser. Use performance tools to identify the bottleneck before changing architecture.

```css
.dragging {
  will-change: transform;
}

/* Remove the hint when the interaction ends. */
```

`will-change` is a hint that an element is likely to change soon. Browsers may allocate extra resources or layers in preparation, which means overuse can consume memory and make performance worse. Apply it shortly before a demanding interaction when measurement supports it, then remove it afterward. Do not place `will-change` on every animated element by default.
