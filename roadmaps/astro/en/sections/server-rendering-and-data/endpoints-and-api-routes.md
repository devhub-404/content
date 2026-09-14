# Endpoints and API Routes

JavaScript and TypeScript files in the pages tree can return `Response` objects and act as endpoints. In server mode they can implement request-time API behavior; in static mode compatible GET endpoints can generate files during the build.

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

Use Web `Request` and `Response` semantics and treat endpoint inputs as untrusted. Validate payload size, authentication, authorization, and content type. Keep business logic in reusable server modules so endpoint files remain transport adapters rather than becoming the entire application architecture.
