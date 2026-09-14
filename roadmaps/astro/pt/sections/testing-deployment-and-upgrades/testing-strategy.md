# Estratégia de Testes

Apps Astro têm várias layers: templates server-rendered, browser scripts, hydrated islands, endpoints e routes. Teste cada layer no nível mais barato que gera confiança e cubra critical user journeys com integration/E2E no browser.

```astro
// End-to-end example
await page.goto("/docs");
await expect(page.getByRole("heading", { name: "Docs" })).toBeVisible();
await page.getByRole("link", { name: "Getting started" }).click();
```

Component static que só renderiza HTML pode precisar pouco unit test além de domain functions. Islands usam tools do framework; route rendering, redirects, middleware e hydration merecem integration contra build parecido com produção.
