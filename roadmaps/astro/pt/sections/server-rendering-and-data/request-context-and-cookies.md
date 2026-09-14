# Request Context, Cookies e Redirects

Em on-demand rendering, global `Astro` expõe data da request como URL, cookies, params, redirects e response controls. Esses values pertencem a uma request e devem dirigir rendering específico diretamente.

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

Cookies/headers são security boundaries. Configure attributes adequados, valide session no server e não vaze secrets em HTML/hydrated props. Static prerender não possui visitor request live, então APIs dependentes exigem runtime mode correto.
