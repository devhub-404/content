# Middleware

Middleware se ejecuta alrededor del route handling y puede leer request, añadir `locals`, redirect, short-circuit o modificar response. Sirve para request correlation, auth gates, locale y headers transversales.

```astro
import { defineMiddleware } from "astro:middleware";

export const onRequest = defineMiddleware(async (context, next) => {
  context.locals.requestId = crypto.randomUUID();
  const response = await next();
  response.headers.set("x-request-id", context.locals.requestId);
  return response;
});
```

Mantén middleware enfocado porque toda request paga el coste y hidden control flow complica debugging. Auth middleware puede establecer identity, pero authorization pertenece cerca de operaciones/data protegidos. Tipa `locals` con garantías claras.
