# Routing Priority and Advanced Routing

Astro has deterministic route matching rules when static, dynamic, and rest routes could match the same URL. Astro 7 also introduces Advanced Routing for applications that need deeper control over the request pipeline beyond ordinary file-based page routing.

```astro
// Conventional routes live in src/pages/.
// Astro 7 also supports advanced request-pipeline routing
// for projects that deliberately need lower-level control.
```

Use ordinary `src/pages` routing unless the project has a concrete need that the standard model cannot express. Lower-level routing increases ownership of matching, middleware, caching, and deployment behavior. A simpler route tree is easier to debug, generate, and migrate across hosting environments.
