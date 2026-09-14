# Composition entre Server/Client Boundaries

Client Component pode receber conteúdo de Server Component já renderizado via `children` ou React-node prop. Isso permite shell interativo client ao redor de conteúdo server sem importar server component no client graph.

```tsx
// Server Component
export default function Page() {
  return (
    <ClientModal>
      <ServerProductDetails />
    </ClientModal>
  );
}
```

Pense em imports/serialization. Server module pode importar client component, mas client module não importa server-only code arbitrário. Passe values serializáveis e mantenha DB handles, secrets e filesystem atrás da boundary server.
