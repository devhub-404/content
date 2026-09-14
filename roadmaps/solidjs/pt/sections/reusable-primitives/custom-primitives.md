# Primitives Reativas Customizadas

Lógica reutilizável em Solid normalmente é function comum que cria/retorna signals, stores, resources, memos, effects ou callbacks. Como primitives usam ownership/tracking e não Hook rules exclusivas de component, helpers se compõem naturalmente.

```tsx
function createToggle(initial = false) {
  const [value, setValue] = createSignal(initial);
  const toggle = () => setValue(current => !current);
  return [value, toggle];
}

const [open, toggleOpen] = createToggle();
```

Projete primitive em torno de comportamento coerente e retorne a menor API útil. Preserve getter functions quando caller precisa reatividade em vez de snapshots. Se cria subscriptions/computations, registre cleanup para seguir lifetime do owner.
