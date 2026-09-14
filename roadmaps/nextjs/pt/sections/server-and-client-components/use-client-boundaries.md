# Boundaries com `use client`

File marcado `use client` define client-module boundary. Seus exports e transitive dependencies passam ao client bundle, permitindo state, effects, event handlers e browser APIs.

```tsx
"use client";

import { useState } from "react";

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

Empurre boundaries para subtree interativa menor possível. Marcar layout alto como client pode puxar grande dependency graph ao browser. Server parents ainda podem renderizar Client Components e passar props serializáveis/children.
