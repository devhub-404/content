# Transitions con `useTransition`

Una Transition marca state updates non-urgent que pueden tardar más en renderizar. Interacciones urgentes como typing actualizan inmediatamente mientras React trabaja en la transition en background, y `isPending` comunica progreso del trabajo de menor prioridad.

```jsx
function SearchPage() {
  const [query, setQuery] = useState('');
  const [filter, setFilter] = useState('');
  const [isPending, startTransition] = useTransition();

  function update(value) {
    setQuery(value);
    startTransition(() => setFilter(value));
  }
}
```

Las transitions no hacen más rápido JavaScript lento ni son debounce. Cambian prioridad y permiten rendering interrumpible. Separa input inmediato de UI derivada costosa cuando importe responsiveness y perfila el bottleneck real si sigue lento.
