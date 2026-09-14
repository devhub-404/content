# Content Security Policy

Astro moderno incluye tooling de CSP para limitar scripts, styles, images y otros resources permitidos. Astro 7.1 añade control más fino sobre policies de script/style.

```astro
export default defineConfig({
  security: {
    csp: {
      directives: {
        "default-src": ["'self'"]
      }
    }
  }
});
```

CSP es más fuerte cuando refleja la app real en vez de permitir inline/third-party hasta que desaparezcan warnings. Inventaría origins necesarias, evita unsafe HTML y prueba integrations bajo la policy de producción. CSP complementa escaping/server validation, no los sustituye.
