# Conditional Rendering y Lists

React usa control flow JavaScript normal para UI condicional y arrays para UI repetida. Early returns, `&&`, operador condicional y `map` son patrones comunes. Los elementos de una lista necesitan keys estables para que React relacione cada child con el mismo ítem lógico entre updates.

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

Una key debe venir de identidad persistente de los datos, no de un valor aleatorio o del índice cuando los ítems pueden reordenarse, insertarse o eliminarse. Las keys afectan identidad del component y preservación de state, por lo que una mala elección puede producir bugs sutiles.
