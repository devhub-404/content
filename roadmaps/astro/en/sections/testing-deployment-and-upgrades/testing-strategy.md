# Testing Strategy

Astro applications contain several layers: server-rendered templates, plain browser scripts, hydrated framework islands, endpoints, and full routes. Test each layer at the cheapest level that gives confidence, then cover critical user journeys with browser-level integration or end-to-end tests.

```astro
// End-to-end example
await page.goto("/docs");
await expect(page.getByRole("heading", { name: "Docs" })).toBeVisible();
await page.getByRole("link", { name: "Getting started" }).click();
```

A static component that mostly renders HTML may need little unit testing beyond domain functions. Interactive islands can use their framework's component tools, while route rendering, redirects, middleware, and hydration deserve integration tests against a production-like build.
