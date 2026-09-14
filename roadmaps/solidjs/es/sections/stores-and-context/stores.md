# State Anidado con `createStore`

Un store ofrece acceso reactivo fine-grained a objects/arrays anidados mediante proxies. `createStore` retorna un state proxy read-only y un setter capaz de actualizar paths seleccionados sin sustituir todo el tree.

```tsx
import { createStore } from "solid-js/store";

const [state, setState] = createStore({
  user: { name: "Mina", active: false },
  todos: []
});

setState("user", "active", true);
```

Usa stores cuando el structured state anidado se beneficie de tracking por propiedad. Signals siguen siendo más simples para valores independientes o whole-value replacement. No destructures store properties demasiado pronto si necesitas mantener reactividad.
