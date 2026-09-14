# Props e Acesso Reativo

Props do Solid são property accessors read-only cujos values podem permanecer reativos. Ler `props.name` em JSX tracked cria dependency esperada. Destructuring eager pode perder reatividade de propriedade salvo helper apropriado.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Avoid eagerly copying a reactive prop into a plain local value.
```

Trate props como interface do parent, não state para mutar. Use `mergeProps` para defaults e `splitProps` ao separar options próprias de attributes encaminhados. Mantenha reactive reads tardios, perto de onde são usados.
