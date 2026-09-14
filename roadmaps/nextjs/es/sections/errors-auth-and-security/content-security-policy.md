# Content Security Policy

CSP limita desde dónde el browser carga/ejecuta scripts, styles, frames y resources. Apps Next con framework scripts inline pueden usar nonces/hashes según deployment/rendering.

```tsx
// Example response header
const nonce = createNonce();

return new NextResponse(response.body, {
  headers: {
    "Content-Security-Policy": `script-src 'self' 'nonce-${nonce}'`
  }
});
```

Construye la policy a partir de resources realmente necesarios en vez de permitir unsafe exceptions. CSP es defense in depth: mantén React escaping, input validation, sanitization para raw HTML y gobernanza de third-party scripts.
