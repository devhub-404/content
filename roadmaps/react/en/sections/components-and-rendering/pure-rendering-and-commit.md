# Pure Rendering and the Commit Phase

A render should be pure: the same props, state, and context should produce the same JSX without mutating external data. React can then call rendering logic whenever needed and only commit the chosen result to the DOM after rendering succeeds.

```jsx
function Price({ amount }) {
  const formatted = new Intl.NumberFormat('en', {
    style: 'currency',
    currency: 'USD'
  }).format(amount);

  return <span>{formatted}</span>;
}
```

Do not start network requests, mutate DOM, write storage, or change module-level state during render. Calculations are fine when they are deterministic. Work that synchronizes React with an external system belongs in events, effects, server data APIs, or another explicit boundary.
