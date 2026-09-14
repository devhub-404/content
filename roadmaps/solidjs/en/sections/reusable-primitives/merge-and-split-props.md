# `mergeProps` and `splitProps`

`mergeProps` combines defaults with incoming props while preserving property access semantics, and `splitProps` separates selected reactive properties from the remaining props. They are especially useful in reusable wrapper components that forward ordinary DOM attributes.

```tsx
function Button(props) {
  const merged = mergeProps({ type: "button" }, props);
  const [local, rest] = splitProps(merged, ["variant", "children"]);

  return <button {...rest} class={`btn ${local.variant ?? "default"}`}>
    {local.children}
  </button>;
}
```

Prefer these helpers over eager object spread or destructuring when you need prop values to stay reactive. Forward only attributes appropriate for the target element, and keep component-specific configuration out of the DOM. TypeScript can help describe the combined component and native-element prop surface.
