# CSRF y Seguridad de Requests

Las apps server-rendered deben defender state-changing requests contra CSRF/origin attacks. Astro ofrece security controls, mientras Actions/endpoints aún necesitan auth, authorization, input validation y cookies seguros.

```astro
export default defineConfig({
  security: {
    checkOrigin: true
  }
});
```

Security funciona por capas. Origin checks no sanitizan HTML, validan permissions ni sustituyen CSP. Combina framework controls con protecciones de la web platform y un threat model claro. Reverse proxies/adapters afectan qué headers son confiables.
