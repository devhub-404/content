# Authentication, Sessions y Authorization

Authentication demuestra identity, session mantiene identity entre requests y authorization decide acceso. Next puede alojar todas las layers, pero recomienda auth libraries establecidas cuando satisfacen el producto.

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

Centraliza session verification y mantén authorization cerca de la data operation, no solo navigation guard/Proxy. Un user sin link aún puede llamar endpoint/action. Cache keys/server-rendered data deben respetar las mismas reglas.
