# Props and Component APIs

Props are the inputs to a component. They are read-only for that render and can contain strings, numbers, objects, functions, JSX, or other values. A good component API makes the important variations explicit instead of reading hidden global state.

```jsx
function Avatar({ name, size = 48 }) {
  return <img src={`/avatars/${name}.png`} alt={name} width={size} />;
}

<Avatar name="Mina" size={64} />
```

Default values are useful for optional props, while object or callback props should have clear ownership semantics. Do not mutate objects received through props. If the parent needs a change, call a callback or update shared state at the owner instead.
