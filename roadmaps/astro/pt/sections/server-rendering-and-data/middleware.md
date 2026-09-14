# Middleware

Middleware roda ao redor do route handling e pode ler request, adicionar `locals`, redirect, short-circuit ou alterar response. Serve a request correlation, auth gates, locale e headers transversais.

```astro
import { defineMiddleware } from "astro:middleware";

export const onRequest = defineMiddleware(async (context, next) => {
  context.locals.requestId = crypto.randomUUID();
  const response = await next();
  response.headers.set("x-request-id", context.locals.requestId);
  return response;
});
```

Mantenha middleware focado porque toda request paga o custo e hidden control flow complica debugging. Auth middleware pode estabelecer identity, mas authorization pertence perto de operações/data protegidos. Type `locals` com guarantees claras.
