# Astro 7.3 e Upgrades

Astro 7.3 é a release atual em setembro de 2026, após Astro 7 trazer Rust compiler, Vite 8, advanced routing e route caching. Minor releases adicionam capabilities sem exigir adoção de tudo.

```astro
# Recommended upgrade helper
npx @astrojs/upgrade

# Then verify
npm run build
npm run check
```

Use upgrade tool/migration guide oficiais, depois rode type checks, production build, route tests e adapter preview. Atualize integrations compatíveis em conjunto. Evite basear arquitetura central em experimental flags sem aceitar migration cost.
