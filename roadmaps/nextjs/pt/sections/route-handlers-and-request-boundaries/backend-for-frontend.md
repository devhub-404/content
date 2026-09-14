# Next.js como Backend for Frontend

Next pode atuar como BFF: Server Components acessam backend, Server Functions fazem mutations e Route Handlers expõem HTTP quando client/external service precisa. Isso mantém credentials fora do browser e adapta responses para UI.

```tsx
// Server-side adapter around an external backend
export async function getAccount() {
  const session = await verifySession();
  return externalApi.get(`/accounts/${session.accountId}`);
}
```

Não é automaticamente substituto de backend geral. Long-running jobs, events, service APIs e workloads com scaling distinto podem pertencer a outro serviço. Mantenha boundary clara para Next cuidar web orchestration sem virar monolith acidental.
