# Children e Helper `children`

`props.children` pode representar JSX com implicações de evaluation e ownership. O helper `children` resolve e memoiza conteúdo de forma Solid-aware quando component precisa inspecionar, reutilizar ou transformar children em vez de apenas renderizar uma vez.

```tsx
import { children } from "solid-js";

function Card(props) {
  const content = children(() => props.children);
  return <section class="card">{content()}</section>;
}
```

Se component só coloca children em um lugar, `{props.children}` normalmente basta. Use helper quando precisa accessor normalizado. Evite avaliar child getters cedo fora do ownership context pretendido, principalmente se criam computations reativas.
