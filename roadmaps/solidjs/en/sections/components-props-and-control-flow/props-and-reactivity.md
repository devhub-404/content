# Props and Reactive Access

Solid props are read-only property accessors whose values can remain reactive. Reading `props.name` in a tracked JSX expression creates the expected dependency. Eager destructuring can lose that property-level reactivity unless you use a helper designed to preserve it.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Avoid eagerly copying a reactive prop into a plain local value.
```

Treat props as an interface from the parent, not state to mutate. Use `mergeProps` for defaults and `splitProps` when a component needs to separate its own options from attributes forwarded to another element. Keep reactive reads late, close to where they are used.
