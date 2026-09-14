# Content Collections

Las content collections dan a contenido relacionado una source con nombre, schema y query API. Un schema valida metadata en build/load y proporciona TypeScript types, útil para blogs, docs, products, authors y otros modelos repetidos.

```astro
// src/content.config.ts
import { defineCollection, z } from "astro:content";

const blog = defineCollection({
  schema: z.object({
    title: z.string(),
    published: z.date()
  })
});

export const collections = { blog };
```

Modela fields según el dominio, no según frontmatter histórico accidental. La validation debe detectar datos inválidos temprano. Usa references entre collections para relationships en vez de duplicar records relacionados.
