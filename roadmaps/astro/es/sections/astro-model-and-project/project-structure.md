# Estructura de Proyecto

La mayor parte del source Astro vive en `src`, mientras `src/pages` es la directory de routing con significado definido por el framework. Components, layouts, styles y domain modules pueden organizarse según el proyecto. Los archivos en `public` se copian sin procesamiento de Astro.

```astro
src/
  components/
  layouts/
  pages/
  styles/
  content.config.ts
public/
astro.config.mjs
package.json
```

Pon assets en `src` cuando quieras processing, hash, optimization o bundling; usa `public` para paths exactos o archivos sin procesamiento. Organiza por ownership/features en vez de tratar cada carpeta convencional como obligatoria.
