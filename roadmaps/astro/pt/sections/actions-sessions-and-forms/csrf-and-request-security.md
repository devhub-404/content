# CSRF e Segurança de Requests

Apps server-rendered precisam defender state-changing requests contra CSRF/origin attacks. Astro fornece security controls, enquanto Actions/endpoints ainda precisam auth, authorization, input validation e cookies seguros.

```astro
export default defineConfig({
  security: {
    checkOrigin: true
  }
});
```

Security é em camadas. Origin checks não sanitizam HTML, validam permissions ou substituem CSP. Combine framework controls com proteções da web platform e threat model claro. Reverse proxies/adapters afetam quais headers são confiáveis.
