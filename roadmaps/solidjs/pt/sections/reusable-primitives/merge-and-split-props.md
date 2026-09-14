# `mergeProps` e `splitProps`

`mergeProps` combina defaults com incoming props preservando semântica de property access, e `splitProps` separa properties selecionadas das restantes. São úteis em wrappers reutilizáveis que encaminham attributes DOM.

```tsx
function Button(props) {
  const merged = mergeProps({ type: "button" }, props);
  const [local, rest] = splitProps(merged, ["variant", "children"]);

  return <button {...rest} class={`btn ${local.variant ?? "default"}`}>
    {local.children}
  </button>;
}
```

Prefira helpers a object spread/destructuring eager quando values precisam continuar reativos. Encaminhe apenas attributes adequados ao target e não deixe config própria vazar no DOM. TypeScript ajuda a descrever surface combinada.
