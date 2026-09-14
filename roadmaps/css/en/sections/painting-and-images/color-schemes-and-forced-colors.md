# Color Schemes and Forced Colors

`color-scheme` tells the browser which light/dark schemes the page can render, allowing compatible user-agent controls and system colors to adapt. Forced-colors environments can replace author colors to satisfy user contrast needs; system color keywords and structural cues are valuable there.

```css
:root {
  color-scheme: light dark;
}

.alert {
  border: 2px solid currentColor;
}

@media (forced-colors: active) {
  .alert {
    forced-color-adjust: auto;
  }
}
```

Do not encode state only by hue. Text, borders, icons, shapes, or other structure should preserve meaning when colors are remapped. `forced-color-adjust` can opt a narrow element out of some forced-color behavior, but doing so broadly defeats the user's chosen accessibility mode. Test dark mode, forced colors, and increased contrast as real presentation environments.
