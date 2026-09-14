# Cookies, Headers e Responses

APIs server expõem incoming cookies/headers; Route Handlers/Server Functions podem set cookies ou responses conforme suporte. São async no App Router atual e representam request-time data.

```tsx
import { cookies } from "next/headers";

export async function POST() {
  const store = await cookies();
  store.set("theme", "dark", {
    httpOnly: true,
    sameSite: "lax",
    secure: true
  });
  return new Response(null, { status: 204 });
}
```

Cookie attributes fazem parte da security: configure `HttpOnly`, `Secure`, `SameSite`, path/domain/expiration. Não confie em forwarded headers cegamente. Evite private data em cookies client-readable salvo necessidade real.
