# Content Collections

Content collections give related content a named source, schema, and query API. A schema validates metadata at build or load time and gives TypeScript useful types, which is especially valuable for blogs, docs, products, authors, and other repeated content models.

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

Model fields according to the content domain rather than whatever frontmatter happened to exist historically. Validation should catch missing or malformed data early. Use references between collections when content has relationships instead of duplicating whole related records across files.
