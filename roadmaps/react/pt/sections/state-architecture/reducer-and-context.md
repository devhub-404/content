# Reducers com Context

Combinar reducer com context pode expor state e dispatch a uma subtree mantendo transition logic centralizada. Separar context de leitura e de dispatch deixa dependencies mais claras e pode reduzir updates em components que só disparam actions.

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

O padrão serve a um domínio coerente dentro da subtree, não como regra para recriar store global em todo app. Conforme cresce, avalie routing state, server data cache, URL state e libraries especializadas separadamente em vez de colocar tudo no reducer.
