# Prioridad de Routing y Advanced Routing

Astro tiene reglas deterministas cuando static, dynamic y rest routes pueden coincidir con la misma URL. Astro 7 también introduce Advanced Routing para apps que necesitan control más profundo del request pipeline más allá del file-based routing normal.

```astro
// Conventional routes live in src/pages/.
// Astro 7 also supports advanced request-pipeline routing
// for projects that deliberately need lower-level control.
```

Usa `src/pages` normal salvo necesidad concreta. Routing low-level aumenta ownership de matching, middleware, cache y deployment. Un route tree simple es más fácil de debuggear, generar y migrar entre hosts.
