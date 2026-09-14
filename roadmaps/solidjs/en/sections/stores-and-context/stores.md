# Nested State with `createStore`

A store provides fine-grained reactive access to nested objects and arrays through proxies. `createStore` returns a read-only reactive state proxy plus a setter API that can update selected paths without replacing the entire object tree.

```tsx
import { createStore } from "solid-js/store";

const [state, setState] = createStore({
  user: { name: "Mina", active: false },
  todos: []
});

setState("user", "active", true);
```

Use stores when nested structured state benefits from property-level tracking. Signals remain simpler for independent scalar values or when whole-value replacement is natural. Do not destructure store properties eagerly if you need them to remain reactive; access them through the proxy or an appropriate helper.
