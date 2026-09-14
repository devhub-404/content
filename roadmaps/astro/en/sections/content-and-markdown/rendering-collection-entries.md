# Rendering Collection Entries

Collection queries return typed entries that separate metadata from the content body. Rendering an entry produces a component-like `Content` value and related headings or plugin data according to the content format and configured pipeline.

```astro
---
import { getCollection, render } from "astro:content";

const posts = await getCollection("blog");
const post = posts[0];
const { Content } = await render(post);
---

<article>
  <h1>{post.data.title}</h1>
  <Content />
</article>
```

Keep querying, sorting, and filtering close to the page or domain service that owns those decisions. A collection is a content database, not automatically the final navigation order. Make publication status, dates, locale, and URL generation explicit instead of depending on filesystem order.
