# Reducers with Context

Combining a reducer with context can expose state and dispatch to a subtree while keeping transition logic in one place. Separating read context from dispatch context can make dependencies clearer and can reduce updates for components that only dispatch actions.

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

This pattern is appropriate for one coherent domain within a subtree, not as a rule that every application must recreate a global store. As requirements grow, evaluate routing state, server data caches, URL state, and specialized state libraries separately instead of putting every kind of data into one reducer.
