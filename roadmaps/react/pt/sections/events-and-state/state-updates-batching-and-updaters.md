# State Updates, Batching e Updater Functions

React agrupa state updates relacionados antes de renderizar para evitar renders intermediários desnecessários. Quando o próximo state depende do anterior, passe updater function; React enfileira essas functions e aplica em ordem sobre o último valor pendente.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  function addThree() {
    setCount(c => c + 1);
    setCount(c => c + 1);
    setCount(c => c + 1);
  }

  return <button onClick={addThree}>{count}</button>;
}
```

Não mute object ou array existente e depois passe a mesma referência. Crie o próximo valor a partir do anterior. Updaters são especialmente importantes quando vários updates podem ocorrer antes do próximo commit.
