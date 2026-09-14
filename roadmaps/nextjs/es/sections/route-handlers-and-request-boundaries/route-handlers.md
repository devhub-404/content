# Route Handlers

Un file `route.ts` define HTTP handlers con Web `Request`/`Response` para GET/POST etc. Sirve para public APIs, webhooks, file responses, callbacks y client requests que necesitan HTTP boundary.

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

No llames tu propio Route Handler desde un Server Component solo para acceder a backend local; llama server function/DB directamente. Los handlers deben validar input, auth, content type, size y method como cualquier endpoint público.
