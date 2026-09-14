# DOM Refs e Ações Imperativas

React normalmente gerencia criação e update do DOM, mas DOM ref fornece acesso imperativo controlado quando a operação é naturalmente imperativa: focus, selection, measurement, scroll, media playback ou third-party widget.

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

Evite usar refs para mudar manualmente DOM que React também controla, pois render posterior pode sobrescrever ou conflitar. Em components reutilizáveis, exponha métodos imperativos estreitos em vez de vazar toda estrutura DOM interna.
