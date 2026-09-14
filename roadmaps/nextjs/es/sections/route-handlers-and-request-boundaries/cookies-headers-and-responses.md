# Cookies, Headers y Responses

Las APIs server exponen incoming cookies/headers; Route Handlers/Server Functions pueden set cookies o responses según soporte. Son async en el App Router actual y representan request-time data.

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

Los cookie attributes forman parte de security: configura `HttpOnly`, `Secure`, `SameSite`, path/domain/expiration. No confíes ciegamente en forwarded headers. Evita private data en cookies client-readable salvo necesidad real.
