# Código Server-only y Environment Variables

El marker `server-only` puede hacer fallar el build si un module sensible entra en el client graph. Las env vars son server-only por defecto; values expuestos al browser necesitan public prefix y se vuelven client-facing config.

```tsx
import "server-only";

export async function getBillingData() {
  const secret = process.env.BILLING_SECRET;
  return billingClient(secret).read();
}
```

Trata public build-time values como públicos para siempre. Nunca pongas credentials bajo public prefix. Separa data-access/secrets/SDKs privilegiados y retorna view models serializables estrechos, no raw DB objects.
