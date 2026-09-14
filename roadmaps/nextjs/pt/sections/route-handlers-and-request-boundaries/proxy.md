# Proxy

Next 16 renomeou `middleware` para `proxy` para enfatizar network boundary antes do route rendering. Proxy pode rewrite, redirect, modificar headers/cookies ou retornar response em requests matched.

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

Use como last-resort boundary, não para slow fetching nem authorization completa. Verifique authorization dentro de Server Functions/data operations porque matcher/route changes podem quebrar assumptions. Para redirects simples, prefira config.
