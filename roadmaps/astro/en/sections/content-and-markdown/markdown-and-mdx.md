# Markdown and MDX

Astro can turn Markdown files into pages or import Markdown content into components. The MDX integration adds component expressions to Markdown when editorial content genuinely needs interactive or reusable UI elements inside the document.

```astro
---
title: "Learning Astro"
published: 2026-09-12
---

# {frontmatter.title}

Astro can render **Markdown** content.
```

Keep ordinary content in Markdown when HTML and Markdown semantics are enough. MDX adds power but also couples content to code and build-time dependencies. Decide where editorial data ends and application logic begins so content remains portable and easy to author.
