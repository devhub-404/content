# Const Type Parameters

A `const` type parameter asks inference to preserve more literal information for object, array, and primitive expressions supplied directly to a generic call. It can reduce the need for callers to write `as const` when an API is specifically designed around literal configuration.

```ts
function defineRoutes<const T extends readonly string[]>(routes: T) {
  return routes;
}

const routes = defineRoutes(["/", "/users"]);
// inferred as readonly ["/", "/users"]
```

This changes inference behavior, not runtime values and not the constraint itself. If the constraint requires a mutable array, readonly literal inference may fall back or behave differently than expected, so use readonly-compatible constraints when the API does not mutate. Const type parameters are best for builder/configuration APIs that genuinely benefit from literal preservation.
