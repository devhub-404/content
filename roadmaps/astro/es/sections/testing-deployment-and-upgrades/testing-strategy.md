# Estrategia de Testing

Las apps Astro tienen varias layers: templates server-rendered, browser scripts, hydrated islands, endpoints y routes. Prueba cada layer al nivel más barato que dé confianza y cubre critical user journeys con integration/E2E en browser.

```astro
// End-to-end example
await page.goto("/docs");
await expect(page.getByRole("heading", { name: "Docs" })).toBeVisible();
await page.getByRole("link", { name: "Getting started" }).click();
```

Un component estático que solo renderiza HTML puede necesitar poco unit test aparte de domain functions. Las islands usan tools de su framework; route rendering, redirects, middleware e hydration merecen integration contra un build parecido a producción.
