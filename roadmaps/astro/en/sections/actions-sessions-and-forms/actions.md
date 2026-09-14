# Astro Actions

Astro Actions define typed server operations that can validate input and be called from Astro forms or client code through framework-managed endpoints. They are useful when an application needs mutations without designing a separate handwritten API route for each internal operation.

```astro
// src/actions/index.ts
import { defineAction } from "astro:actions";
import { z } from "astro:schema";

export const server = {
  createTodo: defineAction({
    input: z.object({ title: z.string().min(1) }),
    handler: async ({ title }) => db.todos.create({ title })
  })
};
```

Actions are still server request handlers. Authenticate, authorize, validate, and handle duplicate submissions deliberately. Keep business logic in reusable functions so the action remains a boundary adapter. External clients that need a stable public HTTP API may still be better served by explicit endpoints.
