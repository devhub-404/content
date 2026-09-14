# Request Context, Cookies y Redirects

En on-demand rendering, el global `Astro` expone data de la request como URL, cookies, params, redirects y response controls. Estos values pertenecen a una request y deben dirigir rendering específico directamente.

```astro
---
const session = Astro.cookies.get("session");

if (!session) {
  return Astro.redirect("/login");
}

const url = Astro.url;
---
<p>Path: {url.pathname}</p>
```

Cookies/headers son security boundaries. Configura attributes adecuados, valida session en server y no filtres secrets en HTML/hydrated props. Static prerender no tiene una visitor request live, por lo que APIs dependientes requieren el runtime mode correcto.
