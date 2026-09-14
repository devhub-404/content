# Markdown e MDX

Astro pode transformar Markdown em pages ou importar content em components. Integration MDX adiciona component expressions quando conteúdo editorial realmente precisa UI reutilizável/interativa dentro do documento.

```astro
---
title: "Learning Astro"
published: 2026-09-12
---

# {frontmatter.title}

Astro can render **Markdown** content.
```

Mantenha conteúdo comum em Markdown quando HTML/Markdown bastam. MDX adiciona poder, mas acopla content a code e dependencies. Defina boundary entre dados editoriais e application logic para manter autoria simples/portável.
