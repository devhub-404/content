# Server-only Code and Environment Variables

The `server-only` marker can make accidental imports of sensitive server modules into client code fail during the build. Environment variables are server-only by default; variables intentionally exposed to browser code require the public prefix and become part of the client-facing configuration.

```tsx
import "server-only";

export async function getBillingData() {
  const secret = process.env.BILLING_SECRET;
  return billingClient(secret).read();
}
```

Treat build-time public values as public forever. Never put credentials behind a public prefix or assume obfuscation protects them. Separate data-access modules, secrets, and privileged SDKs from client code, then return narrow serializable view models rather than raw database objects.
