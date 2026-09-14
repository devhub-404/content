# Optimistic State with `useOptimistic`

Optimistic UI immediately shows the expected result of an action before the authoritative operation finishes. `useOptimistic` creates a temporary optimistic view derived from the current confirmed value and an optimistic update function.

```jsx
const [optimisticTodos, addOptimisticTodo] = useOptimistic(
  todos,
  (current, title) => [...current, { id: 'pending', title }]
);

async function addTodo(formData) {
  const title = formData.get('title');
  addOptimisticTodo(title);
  await createTodo(title);
}
```

Use optimistic updates only when the likely result is predictable and the UI can recover from failure. Do not invent permanent identifiers or security-sensitive outcomes on the client. Keep the confirmed server result authoritative and show clear feedback when the optimistic assumption fails.
