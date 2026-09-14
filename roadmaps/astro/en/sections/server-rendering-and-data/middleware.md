# Middleware

Middleware runs around route handling and can read the request, add values to `locals`, redirect, short-circuit, or modify the outgoing response. It is useful for request correlation, authentication gates, locale decisions, and cross-cutting headers.

```astro
import { defineMiddleware } from "astro:middleware";

export const onRequest = defineMiddleware(async (context, next) => {
  context.locals.requestId = crypto.randomUUID();
  const response = await next();
  response.headers.set("x-request-id", context.locals.requestId);
  return response;
});
```

Keep middleware focused because every matching request pays its cost and hidden control flow becomes difficult to debug. Authentication middleware can establish identity, but authorization still belongs near protected operations and data. Type `locals` so downstream routes know exactly what middleware guarantees.
