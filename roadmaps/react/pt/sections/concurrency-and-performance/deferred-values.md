# Deferred Values

`useDeferredValue` fornece versão atrasada de um valor que pode atualizar em prioridade menor. É útil quando parent já possui state urgente, mas child lento deve manter resultado anterior enquanto novo render é preparado.

```jsx
function Results({ query }) {
  const deferredQuery = useDeferredValue(query);
  const stale = query !== deferredQuery;

  return <SearchResults query={deferredQuery} dimmed={stale} />;
}
```

Deferred value não atrasa request por si só nem fornece timeout fixo; ele adia rendering. Use quando preservar UI anterior é melhor que bloquear input ou trocar conteúdo útil por loading imediatamente.
