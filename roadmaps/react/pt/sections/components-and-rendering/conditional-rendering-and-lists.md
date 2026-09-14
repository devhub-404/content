# Conditional Rendering e Lists

React usa control flow JavaScript comum para UI condicional e arrays para UI repetida. Early returns, `&&`, operador condicional e `map` são padrões comuns. Itens de lista precisam de keys estáveis para React relacionar cada child ao mesmo item lógico entre updates.

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

A key deve vir de identidade persistente dos dados, não de valor aleatório ou índice quando itens podem reordenar, inserir ou remover. Keys afetam identidade do component e preservação de state, então uma escolha ruim pode produzir bugs sutis.
