# Compiler and Fine-grained DOM Updates

Solid's compiler transforms JSX into efficient DOM creation and reactive update code. Static parts are created once, while dynamic expressions subscribe to the reactive values they read. A component function is normally not called again merely because one signal changes.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

This is why performance advice from virtual-DOM frameworks does not transfer mechanically. You usually do not need component-level memoization to avoid rerenders. Instead, understand which expression reads which signal and keep reactive work scoped to the smallest useful computation.
