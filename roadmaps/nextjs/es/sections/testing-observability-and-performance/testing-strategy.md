# Estrategia de Testing

Las apps Next combinan React components, async Server Components, Server Actions, cache, routing y request behavior real. Usa unit tests para domain code, component tests donde el environment soporte y integration/E2E para route/server-client boundaries.

```tsx
await page.goto("/dashboard");
await expect(page.getByRole("heading", { name: "Dashboard" })).toBeVisible();
await page.getByRole("button", { name: "Create project" }).click();
```

Los docs recomiendan E2E para async Server Components cuando unit tools no los representan bien. Prueba mutations incluyendo authorization/invalidation, no solo DOM. Ejecuta production build en CI porque errores de build/route pueden escapar de tests aislados.
