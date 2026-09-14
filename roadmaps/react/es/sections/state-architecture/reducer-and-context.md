# Reducers con Context

Combinar reducer con context puede exponer state y dispatch a un subtree manteniendo transition logic centralizada. Separar context de lectura y de dispatch hace dependencies más claras y puede reducir updates en components que solo disparan actions.

```jsx
const TodosContext = createContext(null);
const TodosDispatchContext = createContext(null);

function TodosProvider({ children }) {
  const [todos, dispatch] = useReducer(todosReducer, []);
  return (
    <TodosContext value={todos}>
      <TodosDispatchContext value={dispatch}>{children}</TodosDispatchContext>
    </TodosContext>
  );
}
```

El patrón sirve a un dominio coherente dentro del subtree, no como regla para recrear un store global en toda app. Al crecer, evalúa routing state, server data cache, URL state y libraries especializadas por separado en vez de poner todo en el reducer.
