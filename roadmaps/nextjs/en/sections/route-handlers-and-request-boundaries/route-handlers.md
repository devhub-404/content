# Route Handlers

A `route.ts` file defines HTTP handlers using Web `Request` and `Response` APIs for methods such as GET and POST. Route Handlers are appropriate for public APIs, webhooks, file responses, callbacks, and client-side requests that need an HTTP boundary.

```tsx
// app/api/health/route.ts
export async function GET() {
  return Response.json({ ok: true });
}

export async function POST(request: Request) {
  const body = await request.json();
  return Response.json({ received: body }, { status: 201 });
}
```

Do not call your own Route Handler from a Server Component just to reach local backend logic; call the underlying server function or database directly. Route Handlers should validate input, authentication, content type, size, and method like any public network endpoint.
