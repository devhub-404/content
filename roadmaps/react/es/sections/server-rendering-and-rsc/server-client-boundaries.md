# Boundaries entre Server y Client Components

La directive `'use client'` marca un module cuyos exports participan en el client bundle. Parents server-rendered pueden pasar datos serializables y rendered children por la boundary, manteniendo la mayor parte de la page en server y pequeñas áreas interactivas en browser.

```jsx
// Counter.jsx
'use client';

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

Trata la boundary como decisión de bundle/serialization, no mera sintaxis. Mantén client modules estrechos. Los valores que cruzan deben seguir el modelo serializable y los secrets server-only nunca deben ir en client props.
