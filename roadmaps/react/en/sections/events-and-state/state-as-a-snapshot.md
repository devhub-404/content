# State as a Snapshot

State lets a component remember information between renders. Each render receives a snapshot of the state values for that render; calling a setter requests another render instead of changing the variable already captured by the current handler.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

This snapshot model explains why logging state immediately after a setter often shows the old value. Store only information that must persist across renders. Ordinary local variables are recreated on every render and are better for derived calculations that do not need independent memory.
