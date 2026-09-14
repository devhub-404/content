# Composition Across Server/Client Boundaries

A Client Component can receive already-rendered Server Component content through `children` or another React-node prop. This composition pattern lets an interactive client shell surround server-rendered content without importing that server component into the client module graph.

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

Think of the boundary in terms of imports and serialization. A server module may import a client component, but a client module cannot import arbitrary server-only code. Pass values that React can serialize and keep database handles, secrets, filesystem objects, and server functions behind server boundaries.
