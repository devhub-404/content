# Reducers for Complex State Transitions

A reducer centralizes how state changes in response to named actions. It is useful when many handlers update related state, when transitions deserve explicit names, or when the update logic should be tested independently of the component.

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

Reducers must stay pure and return the next state instead of mutating the previous state. Action objects form a small protocol; give them meaningful domain names rather than mirroring setters mechanically. A reducer helps organize state logic, but it does not automatically make state global.
