# Estratégia de Testes

Apps Next combinam React components, async Server Components, Server Actions, cache, routing e request behavior real. Use unit tests para domain code, component tests onde environment suporta e integration/E2E para route/server-client boundaries.

```tsx
await page.goto("/dashboard");
await expect(page.getByRole("heading", { name: "Dashboard" })).toBeVisible();
await page.getByRole("button", { name: "Create project" }).click();
```

Docs recomendam E2E para async Server Components quando unit tools não representam bem. Teste mutations incluindo authorization/invalidation, não só DOM. Rode production build em CI porque errors de build/route podem escapar de tests isolados.
