# Components and JSX

A Solid component is usually a function that runs once to create reactive DOM structure. JSX expressions inside the returned tree remain reactive because the compiler wires them to the values they read. Components are therefore setup boundaries rather than repeated render functions.

```tsx
function Badge(props) {
  return <span class="badge">{props.label}</span>;
}

<Badge label="New" />
```

Keep setup work synchronous unless an API explicitly supports async behavior, and use reactive primitives for values that change. Ordinary local values are computed once when the component executes. That distinction is essential when translating code from rerender-based frameworks.
