# Endpoints e API Routes

Files JS/TS na pages tree podem retornar `Response` e agir como endpoints. Em server mode implementam APIs request-time; em static mode GET compatível pode gerar arquivo no build.

```astro
// src/pages/api/status.ts
export function GET() {
  return Response.json({ ok: true });
}

export async function POST({ request }) {
  const body = await request.json();
  return Response.json({ received: body });
}
```

Use semantics de Web `Request`/`Response` e trate inputs como não confiáveis. Valide payload, auth, authorization e content type. Mantenha business logic em modules server reutilizáveis e endpoints como transport adapters.
