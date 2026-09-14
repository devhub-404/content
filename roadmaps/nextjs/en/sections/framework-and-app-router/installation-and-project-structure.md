# Installation and Project Structure

`create-next-app` creates a project with TypeScript, linting, aliases, and App Router conventions according to selected options. The `app` directory contains the route tree, while ordinary components, server modules, utilities, and domain code can live anywhere outside or alongside it.

```tsx
app/
  layout.tsx
  page.tsx
  globals.css
public/
next.config.ts
package.json
tsconfig.json
```

Keep route files focused on routing, rendering, and request boundaries instead of placing every implementation detail inside `app`. Colocation is useful, but route ownership and domain ownership are not always identical. Files in `public` keep stable public paths; imported assets go through the build pipeline.
