# Project Structure

Most Astro source lives under `src`, while `src/pages` is the one routing directory with framework-defined meaning. Components, layouts, styles, and domain modules can be organized however the project needs. Files in `public` are copied without Astro processing.

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

Put assets in `src` when you want Astro or Vite to process, hash, optimize, or bundle them; use `public` for files that must keep an exact path or need no processing. Keep project organization driven by ownership and features rather than treating every conventional folder as mandatory.
