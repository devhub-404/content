# Content Security Policy

Content Security Policy limits where the browser may load or execute scripts, styles, frames, and other resources. Next.js applications with inline framework scripts may use nonces or hashes depending on the deployment and rendering setup.

```tsx
// Example response header
const nonce = createNonce();

return new NextResponse(response.body, {
  headers: {
    "Content-Security-Policy": `script-src 'self' 'nonce-${nonce}'`
  }
});
```

Build the policy from the resources the application truly needs rather than adding broad unsafe exceptions until it works. CSP is defense in depth: keep React escaping, input validation, output sanitization where raw HTML is unavoidable, and secure third-party script governance in place.
