# Next.js como Backend for Frontend

Next puede actuar como BFF: Server Components acceden al backend, Server Functions hacen mutations y Route Handlers exponen HTTP cuando client/external service lo necesita. Esto mantiene credentials fuera del browser y adapta responses para UI.

```tsx
// Server-side adapter around an external backend
export async function getAccount() {
  const session = await verifySession();
  return externalApi.get(`/accounts/${session.accountId}`);
}
```

No es automáticamente sustituto de un backend general. Long-running jobs, events, service APIs y workloads con scaling distinto pueden pertenecer a otro servicio. Mantén la boundary clara para que Next gestione web orchestration sin convertirse en monolith accidental.
