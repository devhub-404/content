# Content Security Policy

Astro includes tooling for Content Security Policy in modern releases, helping applications constrain which scripts, styles, images, and other resources the browser may load or execute. Astro 7.1 adds finer control over script and style policy details.

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

CSP is strongest when it reflects the actual application instead of broadly allowing inline or third-party sources until warnings disappear. Inventory required origins, avoid unsafe HTML injection, and test third-party integrations under the production policy. CSP complements output escaping and server validation; it does not replace them.
