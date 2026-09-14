# Reducers para Transiciones Complejas de State

Un reducer centraliza cómo cambia el state en respuesta a actions con nombre. Es útil cuando muchos handlers actualizan state relacionado, cuando las transitions merecen nombres explícitos o cuando la lógica debe probarse separadamente del component.

```jsx
function reducer(state, action) {
  switch (action.type) {
    case 'added':
      return [...state, action.todo];
    case 'removed':
      return state.filter(todo => todo.id !== action.id);
    default:
      return state;
  }
}

const [todos, dispatch] = useReducer(reducer, []);
```

Los reducers deben ser puros y retornar el next state sin mutar el anterior. Los action objects forman un pequeño protocolo; usa nombres del dominio en vez de imitar setters mecánicamente. Un reducer organiza lógica, pero no vuelve global el state automáticamente.
