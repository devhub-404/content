# Children and the `children` Helper

`props.children` can represent JSX whose evaluation has reactive and ownership implications. The `children` helper resolves and memoizes child content in a Solid-aware way when a component needs to inspect, reuse, or transform children rather than simply render them once.

```tsx
import { children } from "solid-js";

function Card(props) {
  const content = children(() => props.children);
  return <section class="card">{content()}</section>;
}
```

If a component only needs to place children in one location, `{props.children}` is usually enough. Use the helper when you genuinely need a normalized child accessor. Avoid eagerly evaluating child getters outside the intended ownership context, especially when they create reactive computations.
