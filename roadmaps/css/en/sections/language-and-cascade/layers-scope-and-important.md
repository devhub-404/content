# Layers, Scope, and `!important`

Cascade layers create explicit precedence groups inside an origin. For normal author declarations, later layers outrank earlier layers regardless of selector specificity. Important declarations reverse layer priority. This makes layers a better architecture tool than increasing selector weight until a rule wins.

```css
@layer reset, base, components, utilities;

@layer components {
  .button { padding: .6rem 1rem; }
}

@layer utilities {
  .p-0 { padding: 0; }
}

@scope (.article) {
  a { color: #2457d6; }
}
```

`@scope` limits rules to a DOM region and adds scoping proximity as a late cascade tie-breaker. `!important` changes origin/layer precedence; it is not “maximum specificity.” Reserve it for deliberate contracts, because routine use makes author styles difficult to override and can interfere with user customization. Unlayered normal author CSS outranks layered normal author CSS, so mix them intentionally.
