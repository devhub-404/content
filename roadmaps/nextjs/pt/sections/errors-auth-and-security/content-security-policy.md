# Content Security Policy

CSP limita de onde browser carrega/executa scripts, styles, frames e resources. Apps Next com framework scripts inline podem usar nonces/hashes conforme deployment/rendering.

```tsx
// Example response header
const nonce = createNonce();

return new NextResponse(response.body, {
  headers: {
    "Content-Security-Policy": `script-src 'self' 'nonce-${nonce}'`
  }
});
```

Construa policy a partir de resources realmente necessários em vez de liberar unsafe exceptions. CSP é defense in depth: mantenha React escaping, input validation, sanitization para raw HTML e governança de third-party scripts.
