# Font-, Viewport-, and Container-relative Units

Relative units encode a relationship instead of a fixed size. `em` follows a local font size, `rem` follows the root font size, `ch` and `lh` follow font metrics, and viewport units follow viewport dimensions. Modern `sv*`, `lv*`, and `dv*` variants distinguish small, large, and dynamic viewport states.

```css
.prose { max-inline-size: 68ch; }
.button { padding: .65em 1em; }
.hero { min-block-size: 100svh; }

.card-shell { container-type: inline-size; }
.card h2 { font-size: clamp(1.2rem, 5cqi, 2rem); }
```

Container units such as `cqi` and `cqb` follow an eligible query container and are useful for component-local scaling. Choose a unit from the design relationship you mean: typography-relative dimensions should use font-related units, viewport-wide geometry can use viewport units, and reusable components should not depend on the viewport when their actual constraint is their container.
