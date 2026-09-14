# Proxy

Next 16 renombró `middleware` a `proxy` para enfatizar la network boundary antes del route rendering. Proxy puede rewrite, redirect, modificar headers/cookies o retornar response en requests matched.

```tsx
// proxy.ts
import { NextResponse } from "next/server";

export function proxy(request: Request) {
  const url = new URL(request.url);
  if (url.pathname === "/old") {
    return NextResponse.redirect(new URL("/new", request.url));
  }
  return NextResponse.next();
}
```

Úsalo como last-resort boundary, no para slow fetching ni authorization completa. Verifica authorization dentro de Server Functions/data operations porque matcher/route changes pueden romper assumptions. Para redirects simples, prefiere config.
