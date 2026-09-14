# O que é SolidJS

SolidJS é uma library declarativa de UI baseada em fine-grained reactivity. Components executam como functions de setup, enquanto primitives reativas rastreiam exatamente quais computations e expressões DOM dependem de dados mutáveis. Updates podem atingir partes pequenas da UI sem rerenderizar toda a função do component.

```tsx
import { render } from "solid-js/web";

function App() {
  return <h1>Hello, Solid</h1>;
}

render(() => <App />, document.getElementById("app"));
```

Solid usa JSX, mas seu modelo mental difere do rerender model do React. Aprenda signals, computations, ownership e primitives de control flow primeiro. A linha estável de produção continua sendo Solid 1.x em setembro de 2026, enquanto Solid 2.0 está em release candidate e deve ser tratado como contexto de migração.
