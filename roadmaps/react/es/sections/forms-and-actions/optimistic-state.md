# State Optimista con `useOptimistic`

La optimistic UI muestra inmediatamente el resultado esperado de una action antes de que termine la operación autoritativa. `useOptimistic` crea una view temporal derivada del valor confirmado actual y de una optimistic update function.

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

Úsalo cuando el resultado probable sea predecible y la UI pueda recuperarse de un fallo. No inventes identifiers permanentes ni resultados de seguridad en el client. Mantén el server result como autoridad y muestra feedback claro cuando falle la suposición optimista.
