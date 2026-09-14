# Content Security Policy

Astro moderno inclui tooling de CSP para limitar scripts, styles, images e outros resources permitidos. Astro 7.1 adiciona controle mais fino sobre policies de script/style.

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

CSP é mais forte quando reflete app real em vez de liberar inline/third-party até warnings sumirem. Liste origins necessárias, evite unsafe HTML e teste integrations na policy de produção. CSP complementa escaping/server validation, não substitui.
