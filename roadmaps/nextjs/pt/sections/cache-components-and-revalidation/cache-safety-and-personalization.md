# Segurança de Cache e Personalização

Bug mais perigoso de cache é compartilhar output personalizado/authorization-sensitive sob key de outros users. Public catalog e account data têm regras de reuse fundamentalmente diferentes mesmo vindo da mesma DB.

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

Mantenha auth/request identity fora de caches amplos salvo identity fizer parte de key segura e modelo suportado. Revise cached functions como security boundary: quais args afetam resultado, quem pode ver e quão rápido revocation precisa aparecer?
