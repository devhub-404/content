# Custom Properties and `var()`

Custom properties store token sequences in the cascade and are read with `var()`. They normally inherit, so a value can change at the root, theme boundary, component, state, media query, or container query and descendants will resolve the nearest cascaded value.

```css
:root {
  --surface: white;
  --text: #161616;
  --space-card: 1rem;
}

.card {
  color: var(--text);
  background: var(--surface);
  padding: var(--space-card, 1rem);
}

[data-theme="dark"] {
  --surface: #161616;
  --text: white;
}
```

The second argument to `var()` is a fallback used when the referenced custom property is missing or invalid as a custom-property value; it is not a browser-support fallback. Custom properties are substituted late, so a variable can exist but still make the consuming declaration invalid. Prefer semantic names such as `--surface` or `--space-card` over names tied to one literal like `--blue-500-for-button` when the variable represents a design role.
