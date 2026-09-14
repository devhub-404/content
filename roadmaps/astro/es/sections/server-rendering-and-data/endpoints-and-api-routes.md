# Endpoints y API Routes

Los files JS/TS en el pages tree pueden retornar `Response` y actuar como endpoints. En server mode implementan APIs request-time; en static mode un GET compatible puede generar un archivo en build.

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

Usa semántica de Web `Request`/`Response` y trata inputs como no confiables. Valida payload, auth, authorization y content type. Mantén business logic en modules server reutilizables y endpoints como transport adapters.
