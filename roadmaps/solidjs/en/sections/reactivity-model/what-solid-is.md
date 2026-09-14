# What SolidJS Is

SolidJS is a declarative UI library built around fine-grained reactivity. Components run as setup functions, while reactive primitives track exactly which computations and DOM expressions depend on changing data. Updates can therefore target small parts of the UI without rerendering an entire component function.

```tsx
import { render } from "solid-js/web";

function App() {
  return <h1>Hello, Solid</h1>;
}

render(() => <App />, document.getElementById("app"));
```

Solid uses JSX, but its mental model is different from React's rerender model. Learn signals, computations, ownership, and control-flow primitives first. The stable production line remains Solid 1.x in September 2026, while Solid 2.0 is in release-candidate development and should be treated as migration context rather than the baseline.
