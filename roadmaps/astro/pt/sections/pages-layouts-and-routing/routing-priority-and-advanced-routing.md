# Prioridade de Routing e Advanced Routing

Astro possui regras determinísticas quando static, dynamic e rest routes podem casar com a mesma URL. Astro 7 também introduz Advanced Routing para apps que precisam controle mais profundo do request pipeline além do file-based routing comum.

```astro
// Conventional routes live in src/pages/.
// Astro 7 also supports advanced request-pipeline routing
// for projects that deliberately need lower-level control.
```

Use `src/pages` normal salvo necessidade concreta. Routing low-level aumenta ownership de matching, middleware, cache e deployment. Route tree simples é mais fácil de debug, gerar e migrar entre hosts.
