# Estrutura de Projeto

A maior parte do source Astro vive em `src`, enquanto `src/pages` é a directory de routing com significado definido pelo framework. Components, layouts, styles e domain modules podem ser organizados conforme o projeto. Arquivos em `public` são copiados sem processamento do Astro.

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

Coloque assets em `src` quando quer processing, hash, optimization ou bundling; use `public` para paths exatos ou arquivos sem processamento. Organize por ownership/features em vez de tratar toda pasta convencional como obrigatória.
