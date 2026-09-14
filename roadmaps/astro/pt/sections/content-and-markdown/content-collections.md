# Content Collections

Content collections dão a conteúdo relacionado source nomeada, schema e query API. Schema valida metadata em build/load e fornece TypeScript types, útil para blogs, docs, products, authors e outros modelos repetidos.

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

Modele fields pelo domínio, não pelo frontmatter histórico acidental. Validation deve capturar dados inválidos cedo. Use references entre collections para relationships em vez de duplicar records relacionados.
