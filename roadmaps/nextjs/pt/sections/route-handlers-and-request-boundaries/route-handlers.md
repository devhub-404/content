# Route Handlers

File `route.ts` define HTTP handlers com Web `Request`/`Response` para GET/POST etc. Serve a public APIs, webhooks, file responses, callbacks e client requests que precisam HTTP boundary.

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

Não chame seu próprio Route Handler de Server Component apenas para acessar backend local; chame server function/DB diretamente. Handlers devem validar input, auth, content type, size e method como qualquer endpoint público.
