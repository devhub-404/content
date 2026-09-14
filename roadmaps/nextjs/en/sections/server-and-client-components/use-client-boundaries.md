# `use client` Boundaries

A file marked `use client` defines a client-module boundary. Its exports and transitive client-side dependencies become part of the client bundle, enabling state, effects, event handlers, browser APIs, and other interactive React behavior.

```tsx
"use client";

import { useState } from "react";

export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount(c => c + 1)}>{count}</button>;
}
```

Push client boundaries down to the smallest useful interactive subtree. Marking a high-level layout as client can pull large dependency graphs into browser JavaScript. Server parents can still render Client Components and pass serializable props or server-rendered children into them.
