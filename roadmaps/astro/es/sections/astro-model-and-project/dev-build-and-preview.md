# Development, Build y Preview

`astro dev` inicia el dev server, `astro build` crea el output de producción y `astro preview` sirve el build completo localmente. `astro check` ejecuta diagnostics Astro/TypeScript sin producir deployment.

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

Prueba el production build antes de publicar porque dev y production pueden diferir en routing, adapters, minification, asset paths y runtime. Astro 7 añade workflows estructurados/background, pero los comandos comunes siguen siendo el baseline más claro para humanos y CI.
