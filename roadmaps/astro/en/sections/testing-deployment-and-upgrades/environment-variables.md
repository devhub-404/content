# Environment Variables and Secrets

Astro uses Vite-style environment variables for build and server code. Variables prefixed for public exposure can be included in client bundles, while private server values must remain in server-only execution paths and deployment secret stores.

```astro
const publicApi = import.meta.env.PUBLIC_API_BASE;
const privateKey = import.meta.env.SECRET_API_KEY;
```

A variable being present in `.env` does not make it secret if client code imports it or the build inlines it into shipped JavaScript. Separate public configuration from credentials explicitly, validate required values at startup/build time, and never commit real production secrets to source control.
