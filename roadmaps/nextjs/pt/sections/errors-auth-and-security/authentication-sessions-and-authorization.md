# Authentication, Sessions e Authorization

Authentication prova identity, session mantém identity entre requests e authorization decide acesso. Next pode hospedar todas as layers, mas recomenda auth libraries estabelecidas quando atendem produto.

```tsx
export async function verifySession() {
  const session = await readSessionCookie();
  if (!session) redirect("/login");
  return session;
}

export async function getProject(id: string) {
  const session = await verifySession();
  return db.project.findFirst({ where: { id, ownerId: session.userId } });
}
```

Centralize session verification e mantenha authorization perto da data operation, não apenas navigation guard/Proxy. User sem link ainda pode chamar endpoint/action. Cache keys/server-rendered data devem respeitar mesmas regras.
