# Compiler e Updates Granulares do DOM

O compiler do Solid transforma JSX em criação DOM eficiente e update code reativo. Partes estáticas são criadas uma vez, enquanto expressões dinâmicas assinam os valores reativos que leem. A função do component normalmente não é chamada novamente só porque um signal mudou.

```tsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

Por isso, conselhos de performance de frameworks com virtual DOM não se transferem mecanicamente. Normalmente não é necessário memoizar component para evitar rerenders. Entenda quais expressões leem quais signals e mantenha reactive work no menor computation útil.
