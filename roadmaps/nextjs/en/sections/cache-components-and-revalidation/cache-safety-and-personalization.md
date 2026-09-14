# Cache Safety and Personalization

The most dangerous cache bug is sharing personalized or authorization-sensitive output under a key used by other users. Public catalog data and per-user account data have fundamentally different reuse rules even if both come from the same database.

```tsx
async function getPublicCatalog() {
  "use cache";
  return db.product.findMany({ where: { public: true } });
}

async function getCurrentUser() {
  const session = await verifySession();
  return db.user.findUnique({ where: { id: session.userId } });
}
```

Keep authentication and request-specific identity outside broad caches unless identity is explicitly part of a safe key and the framework supports the intended model. Review cached functions as security boundaries: what arguments affect the result, who may see it, and how quickly must revocation become visible?
