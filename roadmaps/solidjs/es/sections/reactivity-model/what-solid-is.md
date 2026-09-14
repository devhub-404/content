# Qué es SolidJS

SolidJS es una library declarativa de UI basada en fine-grained reactivity. Los components se ejecutan como functions de setup, mientras las primitives reactivas rastrean exactamente qué computations y expresiones DOM dependen de datos cambiantes. Los updates pueden afectar partes pequeñas de la UI sin rerenderizar toda la función del component.

```tsx
import { render } from "solid-js/web";

function App() {
  return <h1>Hello, Solid</h1>;
}

render(() => <App />, document.getElementById("app"));
```

Solid usa JSX, pero su modelo mental difiere del rerender model de React. Aprende primero signals, computations, ownership y primitives de control flow. La línea estable de producción sigue siendo Solid 1.x en septiembre de 2026, mientras Solid 2.0 está en release candidate y debe tratarse como contexto de migración.
