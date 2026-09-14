# Testing Strategy

Next.js applications combine React components, async Server Components, Server Actions, caching, routing, and real server request behavior. Use unit tests for pure domain code, component tests where the environment supports the component type, and integration/end-to-end tests for route and server/client boundaries.

```tsx
await page.goto("/dashboard");
await expect(page.getByRole("heading", { name: "Dashboard" })).toBeVisible();
await page.getByRole("button", { name: "Create project" }).click();
```

The Next.js docs recommend E2E coverage for async Server Components when unit tools cannot faithfully support them. Test important mutations against authorization and invalidation behavior, not just visible DOM. Run production builds in CI because type, route, and build-time errors may not appear in isolated tests.
