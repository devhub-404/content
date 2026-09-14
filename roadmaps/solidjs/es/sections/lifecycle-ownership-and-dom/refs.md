# DOM Refs

Una `ref` de Solid da acceso directo al DOM element creado por JSX. Como el setup del component se ejecuta antes de completar mount, `onMount` es el lugar natural para trabajo que exige element conectado, como focus, measurement o un third-party widget.

```tsx
function Search() {
  let input;

  onMount(() => input.focus());

  return <input ref={input} />;
}
```

Usa DOM directo para operaciones realmente imperativas; deja que Solid controle attributes y contenido reactivo normal. En un component reutilizable, considera callback ref o una API imperativa pequeña en vez de filtrar el DOM interno.
