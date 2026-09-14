# Seguridad de Cache y Personalización

El bug de cache más peligroso es compartir output personalizado/authorization-sensitive bajo una key usada por otros users. Public catalog y account data tienen reglas de reuse fundamentalmente distintas aunque vengan de la misma DB.

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

Mantén auth/request identity fuera de caches amplias salvo que identity forme parte de una key segura y del modelo soportado. Revisa cached functions como security boundary: qué args afectan resultado, quién puede verlo y qué tan rápido debe verse una revocation.
