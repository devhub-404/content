# Cookies, Headers, and Responses

Next's server request APIs expose incoming cookies and headers, while Route Handlers and Server Functions can set cookies or construct responses where supported. These APIs are async in the current App Router model and represent request-time data.

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

Cookie attributes are part of security: set `HttpOnly`, `Secure`, `SameSite`, path, domain, and expiration according to purpose. Do not trust forwarded headers blindly behind proxies. Keep response headers explicit and avoid putting private data in client-readable cookies unless the browser truly needs it.
