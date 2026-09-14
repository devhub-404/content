# Astro Actions

Astro Actions definen operaciones server tipadas que validan input y pueden llamarse desde forms/client code mediante endpoints gestionados. Son útiles para mutations internas sin escribir una API route manual por operación.

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

Las Actions siguen siendo request handlers. Autentica, autoriza, valida y maneja duplicate submissions. Mantén business logic en functions reutilizables. External clients que necesitan una HTTP API pública estable pueden usar endpoints explícitos.
