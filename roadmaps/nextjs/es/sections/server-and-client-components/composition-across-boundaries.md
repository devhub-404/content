# Composition entre Server/Client Boundaries

Un Client Component puede recibir contenido de Server Component ya renderizado mediante `children` u otra React-node prop. Esto permite un shell interactivo client alrededor de contenido server sin importar el server component al client graph.

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

Piensa en imports/serialization. Un server module puede importar un client component, pero un client module no importa server-only code arbitrario. Pasa values serializables y mantén DB handles, secrets y filesystem detrás de la boundary server.
