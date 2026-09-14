# Primitives Reactivas Personalizadas

La lógica reutilizable en Solid suele expresarse como una function normal que crea/retorna signals, stores, resources, memos, effects o callbacks. Como las primitives usan ownership/tracking y no Hook rules exclusivas de components, estos helpers se componen naturalmente.

```tsx
function createToggle(initial = false) {
  const [value, setValue] = createSignal(initial);
  const toggle = () => setValue(current => !current);
  return [value, toggle];
}

const [open, toggleOpen] = createToggle();
```

Diseña una primitive alrededor de un comportamiento coherente y retorna la menor API útil. Conserva getter functions cuando el caller necesite reactividad en vez de snapshots. Si crea subscriptions/computations, registra cleanup para seguir el lifetime del owner.
