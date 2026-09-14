# Conditional Rendering and Lists

React uses ordinary JavaScript control flow for conditional UI and arrays for repeated UI. Early returns, `&&`, conditional operators, and `map` are common patterns. List items need stable keys so React can match one rendered child with the same logical item across updates.

```jsx
function TodoList({ todos }) {
  if (todos.length === 0) return <p>No tasks.</p>;

  return (
    <ul>
      {todos.map(todo => <li key={todo.id}>{todo.title}</li>)}
    </ul>
  );
}
```

A key should come from persistent data identity, not from a random value or an array index when items can be reordered, inserted, or removed. Keys affect component identity and state preservation, so choosing the wrong key can produce subtle state bugs as well as inefficient updates.
