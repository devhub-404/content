# Transitions com `useTransition`

Transition marca state updates non-urgent que podem demorar mais para renderizar. Interações urgentes como typing atualizam imediatamente enquanto React trabalha no transition em background, e `isPending` comunica progresso do trabalho de menor prioridade.

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

Transitions não tornam JavaScript lento mais rápido nem são debounce. Elas alteram prioridade e permitem rendering interrompível. Separe input imediato da UI derivada cara quando responsiveness importa e profile bottleneck real se continuar lento.
