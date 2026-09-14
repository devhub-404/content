# Authentication, Sessions, and Authorization

Authentication proves identity, session management carries that identity across requests, and authorization decides which data or operations the identity may access. Next.js can host each layer, but the framework recommends established auth libraries when they meet the product's needs.

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

Centralize secure session verification and keep authorization near the data operation, not only in navigation guards or Proxy. A user who cannot see a link can still call an endpoint or action. Cache keys and server-rendered data must respect the same authorization rules.
