# Children y Helper `children`

`props.children` puede representar JSX con implicaciones de evaluation y ownership. El helper `children` resuelve y memoiza contenido de forma Solid-aware cuando un component necesita inspeccionar, reutilizar o transformar children en vez de simplemente renderizarlos una vez.

```tsx
import { children } from "solid-js";

function Card(props) {
  const content = children(() => props.children);
  return <section class="card">{content()}</section>;
}
```

Si el component solo coloca children en un lugar, `{props.children}` suele bastar. Usa el helper cuando necesites un accessor normalizado. Evita evaluar child getters demasiado pronto fuera del ownership context previsto, especialmente si crean computations reactivas.
