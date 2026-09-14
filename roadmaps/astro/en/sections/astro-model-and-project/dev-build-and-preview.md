# Development, Build, and Preview

`astro dev` runs the development server, `astro build` creates the production output, and `astro preview` serves a completed build locally for validation. `astro check` performs Astro and TypeScript diagnostics without producing a deployment build.

```astro
{
  "scripts": {
    "dev": "astro dev",
    "build": "astro build",
    "preview": "astro preview",
    "check": "astro check"
  }
}
```

Test the production build before shipping because dev and production pipelines can differ in routing, adapters, minification, asset paths, and runtime behavior. Astro 7 also supports more structured/background development workflows, but ordinary CLI commands remain the clearest baseline for humans and CI.
