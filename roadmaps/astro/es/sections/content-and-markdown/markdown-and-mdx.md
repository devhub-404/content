# Markdown y MDX

Astro puede convertir Markdown en pages o importar content en components. La integración MDX añade component expressions cuando el contenido editorial realmente necesita UI reutilizable/interactiva dentro del documento.

```astro
---
title: "Learning Astro"
published: 2026-09-12
---

# {frontmatter.title}

Astro can render **Markdown** content.
```

Mantén contenido normal en Markdown cuando HTML/Markdown basten. MDX añade poder, pero acopla content a code y dependencies. Define la boundary entre datos editoriales y application logic para mantener autoría simple/portable.
