# Transitions e Deferred Values

Transitions coordenam updates de menor prioridade que podem disparar async/expensive work, enquanto `createDeferred` cria valor que pode atrasar em relação a source rápida. Ajudam a preservar interação responsiva enquanto UI lenta atualiza.

```tsx
const [pending, start] = useTransition();

function selectTab(id) {
  start(() => setTab(id));
}

const deferredQuery = createDeferred(query);
```

Não tornam algorithms caros gratuitos. Use quando produto se beneficia de manter conteúdo antigo ou input responsivo, depois profile computation/request real. Feedback de loading/stale state deve continuar compreensível.
