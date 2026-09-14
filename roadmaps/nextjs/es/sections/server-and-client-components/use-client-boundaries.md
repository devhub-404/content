# Boundaries con `use client`

Un file marcado `use client` define una client-module boundary. Sus exports y transitive dependencies pasan al client bundle, permitiendo state, effects, event handlers y browser APIs.

```tsx
"use client";

import { useState } from "react";

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

Empuja boundaries al subtree interactivo más pequeño útil. Marcar un layout alto como client puede llevar un gran dependency graph al browser. Server parents aún pueden renderizar Client Components y pasar props serializables/children.
