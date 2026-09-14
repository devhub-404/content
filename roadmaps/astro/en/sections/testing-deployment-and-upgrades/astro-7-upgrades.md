# Astro 7.3 and Upgrades

Astro 7.3 is the current release in September 2026, following Astro 7's new Rust compiler, Vite 8 pipeline, advanced routing work, and route-caching improvements. Minor releases continue to add capabilities without requiring every project to adopt them.

```astro
# Recommended upgrade helper
npx @astrojs/upgrade

# Then verify
npm run build
npm run check
```

Use the official upgrade tool and migration guide for major changes, then run type checks, production builds, route tests, and adapter previews. Upgrade framework integrations together when compatibility requires it. Avoid basing core architecture on experimental flags unless the project accepts their migration cost.
