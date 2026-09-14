# Astro Actions

Astro Actions definem operações server tipadas que validam input e podem ser chamadas por forms/client code via endpoints gerenciados. São úteis para mutations internas sem escrever uma API route manual por operação.

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

Actions ainda são request handlers. Autentique, autorize, valide e trate duplicate submissions. Mantenha business logic em functions reutilizáveis. External clients que precisam HTTP API pública estável podem usar endpoints explícitos.
