# Reducers para Transições Complexas de State

Reducer centraliza como state muda em resposta a actions nomeadas. É útil quando muitos handlers atualizam state relacionado, quando transitions merecem nomes explícitos ou quando a lógica deve ser testada separadamente do component.

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

Reducers devem ser puros e retornar next state sem mutar o anterior. Action objects formam um pequeno protocolo; use nomes de domínio em vez de imitar setters mecanicamente. Reducer organiza lógica, mas não torna state global automaticamente.
