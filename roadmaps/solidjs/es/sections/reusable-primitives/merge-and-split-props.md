# `mergeProps` y `splitProps`

`mergeProps` combina defaults con incoming props conservando semántica de property access, y `splitProps` separa properties seleccionadas de las restantes. Son útiles en wrappers reutilizables que reenvían attributes DOM.

```tsx
function Button(props) {
  const merged = mergeProps({ type: "button" }, props);
  const [local, rest] = splitProps(merged, ["variant", "children"]);

  return <button {...rest} class={`btn ${local.variant ?? "default"}`}>
    {local.children}
  </button>;
}
```

Prefiere estos helpers frente a object spread/destructuring eager cuando los values deban seguir reactivos. Reenvía solo attributes adecuados al target y evita que config propia llegue al DOM. TypeScript ayuda a describir la surface combinada.
