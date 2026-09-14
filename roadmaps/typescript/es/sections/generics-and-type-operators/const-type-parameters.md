# Const type parameters

Un type parameter `const` pide a la inferencia que conserve mejor literals suministrados directamente a una llamada genérica. Puede reducir la necesidad de que el caller escriba `as const` en builders y APIs de configuración.

```ts
function defineRoutes<const T extends readonly string[]>(routes: T) {
  return routes;
}

const routes = defineRoutes(["/", "/users"]);
// inferred as readonly ["/", "/users"]
```

Solo cambia la inferencia, no el valor de runtime ni el constraint. Si el constraint exige una colección mutable, la inferencia literal readonly puede no comportarse como esperas. Úsalo cuando la API realmente dependa de conservar los literals.
