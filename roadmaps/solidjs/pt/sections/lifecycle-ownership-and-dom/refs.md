# DOM Refs

`ref` do Solid fornece acesso direto ao DOM element criado por JSX. Como component setup roda antes do mount completar, `onMount` é lugar natural para trabalho que exige element conectado, como focus, measurement ou third-party widget.

```tsx
function Search() {
  let input;

  onMount(() => input.focus());

  return <input ref={input} />;
}
```

Use DOM direto para operações realmente imperativas; deixe Solid controlar attributes e conteúdo reativo normais. Em component reutilizável, considere callback ref ou API imperativa pequena em vez de vazar DOM interno.
