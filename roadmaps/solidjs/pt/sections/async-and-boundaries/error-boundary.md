# Error Boundaries

`ErrorBoundary` captura errors lançados ao criar/atualizar reactive subtree abaixo e renderiza fallback. Fallback pode receber reset para tentar novamente após condição subjacente mudar.

```tsx
<ErrorBoundary fallback={(error, reset) => (
  <div>
    <p>{error.message}</p>
    <button onClick={reset}>Try again</button>
  </div>
)}>
  <Dashboard />
</ErrorBoundary>
```

Use boundaries em regiões significativas e reporte errors ao monitoring em vez de só esconder. Não substituem expected-error states normais de data APIs; validation failures e not-found normalmente são domain values, não exceptions para derrubar subtree.
