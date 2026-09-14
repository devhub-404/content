# CSRF and Request Security

Server-rendered applications must defend state-changing requests against cross-site request forgery and related origin attacks. Astro provides request-security controls, while Actions and ordinary endpoints still need application-level authentication, authorization, input validation, and safe cookie settings.

```astro
export default defineConfig({
  security: {
    checkOrigin: true
  }
});
```

Security is layered. Origin checks do not sanitize HTML, validate database permissions, or replace Content Security Policy. Use framework controls together with web-platform protections and a clear threat model. Reverse proxies and deployment adapters can affect which request headers are trustworthy.
