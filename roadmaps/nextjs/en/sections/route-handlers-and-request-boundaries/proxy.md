# Proxy

Next.js 16 renamed the `middleware` convention to `proxy` to emphasize that it runs at a network boundary before route rendering. Proxy can rewrite, redirect, modify headers or cookies, and sometimes return a response directly for matched requests.

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

Use Proxy as a last-resort request boundary, not a place for slow data fetching or complete authorization. The docs explicitly recommend verifying authorization inside Server Functions and protected data operations because Proxy matchers or route changes can bypass assumptions. Prefer config redirects for simple static redirects.
