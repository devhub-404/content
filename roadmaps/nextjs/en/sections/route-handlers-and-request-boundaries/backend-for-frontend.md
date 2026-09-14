# Next.js as a Backend for Frontend

Next.js can act as a Backend for Frontend: Server Components access backend data, Server Functions handle mutations, and Route Handlers expose HTTP where a client or external service needs it. This can keep browser bundles free of credentials and reshape backend responses for the UI.

```tsx
// Server-side adapter around an external backend
export async function getAccount() {
  const session = await verifySession();
  return externalApi.get(`/accounts/${session.accountId}`);
}
```

It is not automatically a replacement for a general-purpose backend. Long-running jobs, event processing, complex service-to-service APIs, and workloads with different scaling needs may belong elsewhere. Keep the boundary clear so Next owns web-facing orchestration instead of becoming an accidental monolith.
