# Boundaries entre Server e Client Components

A directive `'use client'` marca module cujos exports participam do client bundle. Parents server-rendered podem passar dados serializáveis e rendered children pela boundary, mantendo a maior parte da page no server e pequenas áreas interativas no browser.

```jsx
// Counter.jsx
'use client';

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(count + 1)}>{count}</button>;
}
```

Trate a boundary como decisão de bundle/serialization, não mera sintaxe. Mantenha client modules estreitos. Valores cruzando devem seguir modelo serializável e secrets server-only nunca devem ir em client props.
