# Código Server-only e Environment Variables

Marker `server-only` pode fazer build falhar se module sensível entrar no client graph. Env vars são server-only por default; values expostos ao browser precisam public prefix e viram client-facing config.

```tsx
import "server-only";

export async function getBillingData() {
  const secret = process.env.BILLING_SECRET;
  return billingClient(secret).read();
}
```

Trate public build-time values como públicos para sempre. Nunca coloque credentials em public prefix. Separe data-access/secrets/SDKs privilegiados e retorne view models serializáveis estreitos, não raw DB objects.
