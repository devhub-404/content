# DOM Refs y Acciones Imperativas

React normalmente gestiona la creación y update del DOM, pero una DOM ref da acceso imperativo controlado cuando la operación es naturalmente imperativa: focus, selection, measurement, scroll, media playback o un third-party widget.

```jsx
function Search() {
  const inputRef = useRef(null);

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current?.focus()}>
        Focus
      </button>
    </>
  );
}
```

Evita usar refs para cambiar manualmente DOM que React también controla, porque un render posterior puede sobrescribir o entrar en conflicto. En components reutilizables, expón métodos imperativos estrechos en vez de filtrar toda la estructura DOM interna.
