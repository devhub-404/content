# State Otimista com `useOptimistic`

Optimistic UI mostra imediatamente resultado esperado de uma action antes da operação autoritativa terminar. `useOptimistic` cria uma view temporária derivada do valor confirmado atual e de uma optimistic update function.

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

Use quando resultado provável é previsível e a UI consegue recuperar de falha. Não invente identifiers permanentes ou resultados de segurança no client. Mantenha server result como autoridade e mostre feedback claro quando a suposição otimista falhar.
