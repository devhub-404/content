# Fronteras de confianza y seguridad web

Parámetros de URL, respuestas de red, storage, mensajes e input del usuario son datos de fronteras de confianza, no valores automáticamente válidos. Valida estructura y reglas de dominio antes de usarlos. En el DOM, inserta texto como texto y evita tratar strings no confiables como HTML.

```js
const item = document.createElement("li");
item.textContent = untrustedName;

const response = await fetch("/api/profile", {
  credentials: "same-origin",
});
```

Same-origin policy, CORS, CSP, cookies, credentials, sandboxing y Trusted Types condicionan lo que el JavaScript del navegador puede hacer con seguridad. Son mecanismos de plataforma, no sintaxis ECMAScript. No arregles un problema de CORS o CSP debilitando todo: concede solo la relación de confianza necesaria.
