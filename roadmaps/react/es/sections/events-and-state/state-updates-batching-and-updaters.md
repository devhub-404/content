# State Updates, Batching y Updater Functions

React agrupa state updates relacionados antes de renderizar para evitar renders intermedios innecesarios. Cuando el próximo state depende del anterior, pasa una updater function; React encola esas functions y las aplica en orden sobre el último valor pendiente.

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

No mutes un object o array existente y luego pases la misma referencia. Crea el próximo valor a partir del anterior. Los updaters son especialmente importantes cuando varios updates pueden ocurrir antes del próximo commit.
